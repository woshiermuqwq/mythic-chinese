技能: Sudo Skill
--------------------------

令目标作为施法者激活技能.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| skill | s | 所激活的技能组 | 无 |
| setcasterastrigger | cat | 施法者是否作为所激活技能组的触发者 | false |

示例
-------

实体配置:

    某村民:
      Type: villager
      Display: '我不是村民'
      Skills:
      - sudoskill{s=其它技能组;cat=true} @trigger ~onDamaged

技能组配置:

    其它技能组:
      Skills:
      - arrowvolley{a=20;s=25;v=10;f=50;rd=200} @EIR{r=30}
      - message{msg="触发者名: <trigger.name>"} @self

关于 SetCasterAsTrigger
----------------------

  一般地，若触发器为 **~onDamaged** 
  且不使用 **SudoSkill** 直接使用 **Message** 技能  
  向全服玩家发送包含 <triggee.name>（触发者名）的文本（即攻击者名称） 
  Message所发送的文本将包含 攻击施法者的实体  
 
  若使用 **Sudoskill** 且未开启**setCasterastrigger**  
  并将 Message 写入 Sudoskill所调用的技能组里  
  Message的文本保持不变 
  
  Message若仍使用@world且攻击者是一名玩家  
  攻击者将收不到信息, 因为@world会过滤施法者自身（即 攻击者）  

  Message若使用了@self, @self将选取 被SudoSkill的实体（即 攻击者)  
  Message所发送的文本将包含 SudoSkill的技能目标名称（即 攻击者名称）  

  若开启 **setCasterastrigger**  
  Message所发送的文本则包含 SudoSkill的施法者名（即施法者名称：某村民）  

  目标选择器: @Trigger、占位符<trigger.var.> 同理