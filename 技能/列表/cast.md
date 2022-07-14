技能: Cast
--------------------------

Cast是[光环](技能/列表/Aura)的一种.  
一个相当于 蓄力 的光环.

修改项
----------

*适用于[Aura](技能/列表/Aura)*

*也能使用[Aura](技能/列表/Aura)的修改项*

*Duration就是蓄力时间(蓄力结束相当于光环结束)*

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| onCast        | oc      | 光环结束后所激活的技能组 | 无 |
| onInterrupted | oi      | 光环中断后所激活的技能组  | 无 |
| onNoTarget    | ont     | 光环的技能目标为空时所激活的额外技能组 | 无 |
| skillname     | sn      | 光环的名称 | 无 |
| showCastBar   | cb      | 是否生成悬浮字以显示Cast光环的名称 | true    |
| cancelOnMove  | com     | 光环是否在移动后消失 | false   |

示例
--------

```yaml
# 实体配置
 冰霜:
 Skills:
 - cast{i=2;skillName="&a冰霜";duration=40;onCast=激活冰霜;onTick=冰霜-Tick;onInterrupted=冰霜-End;onNoTargets=冰霜-无目标;cancelOnMove=true;showCastBar=true} @target ~onTimer:100

# 技能组配置
冰霜-Tick:
 Skills:
 - message{m="<mob.name>蓄力中.."} @EIR{r=16}
 - effect:particlering{particle=flame;r=0.7;y=0.05;points=32;repeat=2;repeatInterval=20;d=true} @origin
激活冰霜:
 Skills:
 - message{m="<mob.name>蓄力完成.."} @EIR{r=16}
冰霜-无目标:
 Skills:
 - message{m="<mob.name>未察觉到威胁.."} @EIR{r=16}
冰霜-End:
 Skills:
 - message{m="<mob.name>未察觉到威胁..w"} @EIR{r=16}
```
每5秒对仇恨目标激活该光环, 光环名为冰霜, 蓄力2秒  
若蓄力完成技能目标仍存在则激活技能组: `激活冰霜`  
蓄力期间每2刻激活一次技能组: `冰霜-Tick`  
若中途移动则激活技能组: `冰霜-End`  
若蓄力完成后技能目标消失则激活技能组: `冰霜-无目标`