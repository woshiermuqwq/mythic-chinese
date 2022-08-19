技能: Sudo Skill
--------------------------

令技能目标作为施法者激活技能.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| skill | s | 所激活的技能组 | 无 |
| setcasterastrigger | cat | 触发者是否作为所激活技能组的触发者 | false |

示例
-------

实体配置:

```yml
某村民:
  Type: villager
  Display: '我不是村民'
  Skills:
  - sudoskill{s=其它技能组;cat=true} @trigger ~onDamaged
```

技能组配置:

```yml
其它技能组:
  Skills:
  - arrowvolley{a=20;s=25;v=10;f=50;rd=200} @EIR{r=30}
  - message{msg="触发者名<&co> <trigger.name>"} @self
```

关于 SetCasterAsTrigger
----------------------

  一般地，若触发器为 **~onDamaged** 
  且不使用 **SudoSkill** 直接使用 **Message** 技能  
  向全服玩家发送包含 <triggee.name>（触发者名）的文本（即攻击者名称） 
  Message所发送的文本将包含 攻击施法者的实体  
 
  若使用 **Sudoskill** 且未开启**setCasterastrigger**  
  并将 Message 写入 Sudoskill所调用的技能组里  
  Message的文本保持不变 
  
  Message若仍使用\@World且攻击者是一名玩家  
  攻击者将收不到信息, 因为\@World会过滤施法者自身（即 攻击者）  

  Message若使用了\@Self, \@Self将选取 被SudoSkill的实体（即 攻击者)  
  Message所发送的文本将包含 SudoSkill的技能目标名称（即 攻击者名称）  

  若开启 **setCasterastrigger**  
  Message所发送的文本则包含 SudoSkill的施法者名（即施法者名称：某村民）  

  目标选择器: \@Trigger、占位符<trigger.var.> 同理

  该选项为false时, 被sudoskill的实体所执行的技能的触发者将与施法者执行sudoskill时的触发者一致  
  这意味着可以让实体选取它的父系实体的主人

上述内容同理示例
---

```yaml
大:
 Type: husk
 Display: '大'
 Options:
  NoAI: true
  AlwaysShowName: true
 Skills:
 - summon{t=AA;os=true;r=5} @self ~onspawn
中:
 Type: husk
 Display: '中'
 AIGoalSelectors:
 - clear
 - gotoparent
 Options:
  AlwaysShowName: true
 Skills:
 - summon{t=A;os=true;r=5} @self ~onspawn
小:
 Type: husk
 Display: '小'
 AIGoalSelectors:
 - clear
 - gotoparent
 Options:
  AlwaysShowName: true
 Skills:
 - sudoskill{cat=true;s=[
   - sudoskill{s=[
     - sudoskill{s=[
       - d{a=999} @trigger
       ];cat=true} @trigger
     ]} @parent
  ]} @parent ~oninteract
```
`大`为`中`的主人, `中`为`小`的主人  
右键`小`将杀死主人（`中`）的主人（`大`）  
非主人（同为`中`）则不会受影响

右键对主人: `中` 激活sudoskill, 同时设其触发者为`小`  
`中`被激活sudoskill后, 对主人`大` 激活sudoskill  
`大`被激活sudoskill后, 对触发者激活sudoskill  
 
`大`被激活sudoskill时`cat`不为`true`  
`cat`不为`true`, 意味着`大`通过被sudoskill所激活的技能的触发者    
仍继承对其激活sudoskill的子系实体: `中`, 激活sudoskill时的触发者  
而`中` 被激活sudoskill时, sudoskill的`cat`为`true`  
所以`中`的sudoskill的触发者是`小`  
所以`大`的sudoskill的触发者是 `中`的sudoskill的触发者: `小`  
最后, `大` 对 触发者: `小` 激活 sudoskill, 且设触发者为`大`（`cat=true`）  
`小`对触发者`大`造成伤害