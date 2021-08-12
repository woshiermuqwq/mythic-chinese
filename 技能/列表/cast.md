技能: Cast
--------------------------

Cast是[光环](技能/列表/Aura)的一种.


修改项
----------

*适用于[Aura](技能/列表/Aura)*

*也能使用[Aura](技能/列表/Aura)的修改项*

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| onCast        | oc      | 技能组成功激活后所激活的额外技能组 | 无 |
| onInterrupted | oi      | Cast光环中断后所激活的额外技能组  | 无 |
| onNoTarget    | ont     | 若Cast的技能目标为空则激活额外技能组 | 无 |
| skillname     | sn      | Cast光环的名称 | 无 |
| showCastBar   | cb      | 是否生成悬浮字以显示Cast光环的名称 | true    |
| cancelOnMove  | com     | Cast光环是否在移动后消失 | false   |

示例
--------

    Skills:
    - cast{skillName="&a冰霜";duration=40;onCast=激活冰霜;onTick=冰霜-Tick;onInterrupted=冰霜-End;onNoTargets=冰霜-无目标;cancelOnMove=true;showCastBar=true} @target ~onTimer:100
