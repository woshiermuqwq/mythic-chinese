技能: Aura
--------------------------

给予技能目标光环.  
光环对目标起一个类似状态的作用,并能在光环持续期间激活技能.  
可用光环创造增益或减益效果.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| auraName            | buffname, debuffname | 光环名称（支持[占位符](/技能/占位符)） | 无          |
| onStartSkill             | onstart, os      | 光环激活后施法者所激活的技能（光环给予者为技能组施法者） | 无          |
| onTickSkill              | ontick, ot      | 光环刷新后施法者所激活的技能（光环给予者为技能组施法者） | 无          |
| onEndSkill               | onend, oe      | 光环结束后施法者所激活的技能（光环给予者为技能组施法者） | 无          |
| Charges             | c       | 光环最大可命中次数（支持[占位符](/技能/占位符)）               | 0             |
| Duration            | ticks, t, d, time, t       | 光环最大持续时间(刻 支持[占位符](/技能/占位符)) | 200           |
| Interval            | i       | 光环刷新间隔(刻) | 1             |
| maxStacks           | ms | 光环最大层数（支持[占位符](/技能/占位符)） | 无          |
| refreshDuration     | rd | 光环叠加后是否刷新持续时间 | false         |
| mergeSameCaster     | msc, mc | 光环是否无法被施法者叠加 | false         |
| mergeAll            | ma | 光环是否叠加所有相同的光环 | false         |
| overWriteAll | oa | 光环是否替换已有的同名光环 | false |
| showbartimer | bartimer, bt | 是否以Boss血条的形式向施法者显示光环剩余时间 | false |
| bartimerdisplay | bartimertext | 所显示的Boss血条文本 | <skill.var.aura-name> |
| bartimercolor | | 所显示的[Boss血条颜色](/实体/Boss血条#血条样式列表), **必须全大写** | RED |
| bartimerstyle | | 所显示的[Boss血条样式](/实体/Boss血条#血条样式列表)  | SOLID |
| CancelOnGiveDamage  | cogd    | 光环是否在光环持有者造成伤害后消失 | false         |
| CancelOnTakeDamage  | cotd    | 光环是否在光环持有者受到伤害后消失 | false         |
| CancelOnDeath       | cod     | 光环是否在光环持有者死亡后消失 | true         |
| CancelOnTeleport    | cot     | 光环是否在光环持有者传送后消失 | false         |
| CancelOnChangeWorld | cocw    | 光环是否在光环持有者改变世界后消失 | false         |
| CancelOnSkillUse    | cosu    | 光环是否在光环持有者激活技能后消失 | true         |
| CancelOnQuit        | coq     | 光环是否在光环持有者离线后消失 | true         |
| doendskillonterminate | desot, alwaysrunendskill, ares | 光环被停止后是否激活 onEndSkill | true |

低版本漏洞
--

若光环持有者为光环施法者, 则当该光环可拥有多层数且开启修改项: `ShowBarTimer` 时  
若在光环期间施法者拥有技能: [Orbital](/技能/列表/orbital)或其它**不同名**光环  
则同名光环可能无法叠加, 也就是说一个Boss血条的标题可能在多个文本之间随机变换
```yaml
- aura{auraname=1;d=200} @self
- aura{repeat=2;repeati=20;delay=20;bartimer=true;auraname=测试;bartimertext=层数 <skill.var.aura-stacks>;maxstacks} @self
```
施法者（玩家）获得名为: `1` 的光环一秒后重复给予自身名为"测试"的光环, 重复3次  
也就是说施法者玩家的游戏内会看见一个标题数字不断变大的boss血条（因血条文本为当前光环层数）  
数字增加到3后不再变化  
但由于上述问题的存在, 实际标题文本将会在 1、2、3之间来回变动  
解决办法就是尽量避免玩家同一时间拥有多个不同名光环
  
特殊修改项
----------

光环: **[On Attack](技能/列表/onattack)** 拥有以下特定修改项:

-   所有修改项都能作用于[Aura](技能/列表/Aura)

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| onAttackSkill | onattack, oa, onmelee, onhit, oh | 光环持有者造成伤害后所激活的技能（光环施加者为技能施法者） | 无 |
| cancelevent | cancel, cE, canceldamage, cd | 光环持有者造成伤害后是否取消造成伤害事件 | 无 |
| damageAdd | add, a | 施法者所造成伤害的数值所被加上的具体数值 | 0 |
| damageMultiplier | multiplier, m | 施法者所造成伤害的数值所被乘以的百分比 | 1 |

光环: **[On Damaged](技能/列表/ondamaged)** 拥有以下特定修改项:

-   所有修改项都能作用于[Aura](技能/列表/Aura)

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| ondamagedskill | ondamaged, od, onhitskill, onhit, oh | 光环持有者受到伤害后所激活的技能（光环施加者为技能施法者） | 无 |
| cancelevent | cancel, cE, canceldamage, cd | 光环持有者受到伤害后是否取消受到伤害事件 | false |
| damageSubtract | sub, s | 光环持有者所受到伤害的数值所被减去的具体数值（支持[占位符](/技能/占位符)） | 0 |
| damageMultiplier | multiplier, m | 光环持有者所受到伤害的数值所被乘以的百分比（支持[占位符](/技能/占位符)） | 1 |
| damageModifiers | damageMods | 伤害数值计算后<br>根据该修改项内所写的配置来调整伤害, 类似于[伤害调整](/实体/伤害调整)<br>多个之间用","隔开 | 无 |

示例
--------

```yaml
 Skills:
 - Aura{auraName=雷电;onTick=雷击;interval=10;duration=240} @self
```
给予自身持续12秒的光环: 雷电,每0.5秒(10刻)会激活技能: 雷击
```yaml
 Skills:
 - onDamaged{auraName=火焰防御;onHit=减伤效果;duration=200;charges=5;multiplier=0.5} @self
```
持续10秒的光环: 火焰防御 将令施法者接下来5次受伤数值都减少一半(*50%),且受伤后激活技能: 减伤效果
```
 Skills:
 - onAttack{auraName=火焰攻击;onHit=增伤效果;duration=200;charges=5;multiplier=2} @self
```
持续10秒的光环: 火焰防御 将令施法者接下来5次对其它实体所造成伤害数值都将翻倍(*2),这包括技能伤害  
且受伤后激活技能: 增伤效果.

关于 合并（Merge）与替换（Over Write）
-

当设修改项: `OverWriteAll` 为 `true` 时, 该光环将在启动之前**直接移除**同名光环  
这意味着被移除光环（前者）的元技能（`OnStart/Tick等`）及修改项值（`refreshduration=true;showbartimer=true等`）  
将被后者所替代
```yaml
t:
 Skills:
 - aura{auraname=1;bartimer=true;bartimertext=1<skill.var.aura-stacks>;d=100;overwriteall=true;rd=true;
  ot=[  - m{m=1} ];
  os=[
  - aura{auraname=1;d=40;delay=50;ot=[  - m{m=2} ];overwriteall=true;msc=false;bartimer=true;bartimertext=1<skill.var.aura-stacks>}
  ]} @self
```
第一个光环激活后, 2.5秒内自身将收到"1"的聊天栏信息, 2.5秒后将收到"2"的聊天栏信息

`mergeall` 为 `true` 时, 不管 `mergesamecaster` 值为什么, 俩同名光环都将叠加  
`mergesamecaster` 为 `true` 时, 光环将不会叠加给予者为施法者的同名光环  
但当给予者不为施法者时, 不管 `mergeall` 值为什么, 俩同名光环都将叠加  
`mergesamecaster` 是为后者激活的光环所使用的修改项, 为前者使用没有任何效果
```yaml
t:
 Skills:
 - aura{auraname=1;bartimer=true;bartimertext=1<skill.var.aura-stacks>;d=100;maxstacks=2;mergesamecaster=false;
  os=[
  - aura{auraname=1;d=40;delay=50;mergeall=true;mergesamecaster=false}
  ]} @self
```
不管第一行aura的mergesamecaster值为什么, 该光环都只能有一层  
但若将第二行mergesamecaster改为true, 则会有俩层

额外信息
--------

- 别称: buff, debuff