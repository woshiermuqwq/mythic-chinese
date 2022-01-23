技能: Aura
--------------------------

给予技能目标光环.  
光环对目标起一个类似状态的作用,并能在光环持续期间激活技能.  
可用光环创造增益或减益效果.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| auraName            | buffname, debuffname | 光环名称（支持[占位符](/技能/占位符)与[变量](/技能/变量)） | 无          |
| onStartSkill             | onstart, os      | 光环激活后施法者所激活的技能（光环给予者为技能施法者） | 无          |
| onTickSkill              | ontick, ot      | 光环刷新后施法者所激活的技能（光环给予者为技能施法者） | 无          |
| onEndSkill               | onend, oe      | 光环结束后施法者所激活的技能（光环给予者为技能施法者） | 无          |
| Charges             | c       | 光环最大可命中次数（支持[占位符](/技能/占位符)与[变量](/技能/变量)）               | 0             |
| Duration            | ticks, t, d, time, t       | 光环最大持续时间(刻 支持[占位符](/技能/占位符)与[变量](/技能/变量)) | 200           |
| Interval            | i       | 光环刷新间隔(刻) | 1             |
| maxStacks           | ms | 光环最大层数（支持[占位符](/技能/占位符)与[变量](/技能/变量)） | 无          |
| refreshDuration     | rd | 光环叠加后是否刷新持续时间 | false         |
| mergeSameCaster     | msc, mc | 光环是否无法被施法者叠加| false         |
| mergeAll            | ma | 光环是否叠加所有相同的官宦 | false         |
| showbartimer | bartimer, bt | 是否以Boss血条的形式向施法者显示光环剩余时间 | false |
| bartimerdisplay | bartimertext | 所显示的Boss血条文本 | <skill.var.aura-name> |
| bartimercolor | | 所显示的Boss血条颜色 | Red |
| bartimerstyle | | 所显示的Boss血条样式 | SOLID |
| CancelOnGiveDamage  | cogd    | 光环是否在光环持有者造成伤害后消失 | false         |
| CancelOnTakeDamage  | cotd    | 光环是否在光环持有者受到伤害后消失 | false         |
| CancelOnDeath       | cod     | 光环是否在光环持有者死亡后消失 | true         |
| CancelOnTeleport    | cot     | 光环是否在光环持有者传送后消失 | false         |
| CancelOnChangeWorld | cocw    | 光环是否在光环持有者改变世界后消失 | false         |
| CancelOnSkillUse    | cosu    | 光环是否在光环持有者激活技能后消失 | true         |
| CancelOnQuit        | coq     | 光环是否在光环持有者离线后消失 | true         |

  
特殊修改项
----------

光环: **[On Attack](技能/列表/onattack)** 拥有以下特定修改项:

-   所有修改项都能作用于[Aura](技能/列表/Aura)

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| onAttackSkill | onattack, oa, onmelee, onhit, oh | 光环持有者造成伤害后所激活的技能（光环施加者为技能施法者） | 无 |
| cancleevent | cancel, cE, canceldamage, cd | 光环持有者造成伤害后是否取消造成伤害事件 | 无 |
| damageAdd | add, a | 施法者所造成伤害的数值所被加上的具体数值 | 0 |
| damageMultiplier | multiplier, m | 施法者所造成伤害的数值所被乘以的百分比 | 1 |

光环: **[On Damaged](技能/列表/ondamaged)** 拥有以下特定修改项:

-   所有修改项都能作用于[Aura](技能/列表/Aura)

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| ondamagedskill | ondamaged, od, onhitskill, onhit, oh | 光环持有者受到伤害后所激活的技能（光环施加者为技能施法者） | 无 |
| cancleevent | cancel, cE, canceldamage, cd | 光环持有者受到伤害后是否取消受到伤害事件 | false |
| damageSubtract | sub, s | 光环持有者所受到伤害的数值所被减去的具体数值（支持[占位符](/技能/占位符)/[变量](/技能/变量)） | 0 |
| damageMultiplier | multiplier, m | 光环持有者所受到伤害的数值所被乘以的百分比（支持[占位符](/技能/占位符)/[变量](/技能/变量)） | 1 |
| damageModifiers | damageMods | 伤害数值计算后<br>根据该修改项内所写的配置来调整伤害, 类似于[伤害调整](/实体/伤害调整)<br>多个之间用","隔开 | 无 |

示例
--------

      Skills:
      - Aura{auraName=雷电;onTick=雷击;interval=10;duration=240} @self

给予自身持续12秒的光环: 雷电,每0.5秒(10刻)会激活技能: 雷击

     Skills:
      - onDamaged{auraName=火焰防御;onHit=减伤效果;duration=200;charges=5;multiplier=0.5} @self

持续10秒的光环: 火焰防御 将令施法者接下来5次受伤数值都减少一半(*50%),且受伤后激活技能: 减伤效果

      Skills:
      - onAttack{auraName=火焰攻击;onHit=增伤效果;duration=200;charges=5;multiplier=2} @self

持续10秒的光环: 火焰防御 将令施法者接下来5次对其它实体所造成伤害数值都将翻倍(*2),这包括技能伤害  
且受伤后激活技能: 增伤效果.

额外信息
--------

- 别称: buff, debuff