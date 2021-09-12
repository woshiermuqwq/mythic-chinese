技能: Aura
--------------------------

光环对目标起一个类似状态的作用,并能在光环持续期间激活技能.  
可用光环创造增益或减益效果.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| auraName            | name, n | 光环名称 | 无          |
| onStart             | os      | 光环激活后所激活的技能 | 无          |
| onTick              | ot      | 光环刷新后所激活的技能 | 无          |
| onEnd               | oe      | 光环结束后所释放的技能 | 无          |
| Charges             | c       | 光环最大可命中次数               | 0             |
| Duration            | d       | 光环最大持续时间(刻) | 200           |
| Interval            | i       | 光环刷新间隔(刻) | 1             |
| maxStacks           |         | 光环最大层数 | 无          |
| refreshDuration     |         | 光环叠加后是否刷新持续时间 | false         |
| mergeSameCaster     |         | 光环是否无法被施法者叠加| false         |
| mergeAll            |         | 光环是否无法被叠加 | false         |
| showbartimer | bartimer, bt | 是否使用Boss血条显示光环剩余时间 | false |
| CancelOnGiveDamage  | cogd    | 光环是否在施法者造成伤害后消失 | false         |
| CancelOnTakeDamage  | cotd    | 光环是否在施法者受到伤害后消失 | false         |
| CancelOnDeath       | cod     | 光环是否在施法者死亡后消失 | true         |
| CancelOnTeleport    | cot     | 光环是否在施法者传送后消失 | false         |
| CancelOnChangeWorld | cocw    | 光环是否在施法者改变世界后消失 | false         |
| CancelOnSkillUse    | cosu    | 光环是否在施法者激活技能后消失 | true         |
| CancelOnQuit        | coq     | 光环是否在施法者离线后消失 | true         |

  
特殊修改项
----------

光环: **[onAttack](技能/列表/onattack)**拥有以下特定修改项:

-   所有修改项都能作用于[Aura](技能/列表/Aura)

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| onAttack | oA | 施法者造成伤害后所激活的技能 | 无 |
| cancle | cE | 施法者造成伤害后是否取消造成伤害事件 | 无 |
| damageAdd | add, a | 施法者所造成伤害的数值所被加上的具体数值 | 0 |
| damageMultiplier | multiplier, m | 施法者所造成伤害的数值所被乘以的百分比 | 1 |

光环: **[onDamaged](技能/列表/ondamaged)**拥有以下特定修改项:

-   所有修改项都能作用于[Aura](技能/列表/Aura)

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| onHit | oH | 施法者受到伤害后所激活的技能 | 无 |
| cancle | cE | 施法者受到伤害后是否取消受到伤害事件 | 无 |
| damageSubtract | sub, s | 施法者所受到伤害的数值所被减去的具体数值 | 0 |
| damageMultiplier | multiplier, m | 施法者所受到伤害的数值所被乘以的百分比 | 1 |

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

