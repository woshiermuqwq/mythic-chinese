技能: Stun
--------------------------

晕眩技能目标.

修改项
----------

| 修改项名 | 别称    | 描述          | 默认值 |
|-----------|------------|-------|---------------|
| duration            | d       | 晕眩持续时间(刻)   | 60  |
| noknockback | nokb, kb | 是否不会被击飞 | false |
| stopai              | ai      | 是否无法移动        | false         |
| gravity             | g       | 是否无重力(受到击退 throw影响后会有飞行的效果..)                    | false         |
| facing              | face, f | 是否允许转向           | false         |
| CancelOnGiveDamage  | cogd    | 是否在目标造成伤害后解除晕眩  false         |
| CancelOnTakeDamage  | cotd    | 是否在目标受到伤害后解除晕眩    | false         |
| CancelOnDeath       | cod     | 是否在目标死亡后解除晕眩         | true          |
| CancelOnTeleport    | cot     | 是否在目标传送后解除晕眩 | false         |
| CancelOnChangeWorld | cocw    | 是否在目标进入其它世界后解除晕眩                 | false         |
| CancelOnSkillUse    | cosu    | 是否在目标使用技能后解除晕眩                  | false         |
| CancelOnQuit        | coq     | 是否在目标离线后解除晕眩                      | true          |

示例
--------

```yaml
 Skills:
 - stun{d=60;f=true} @target
```
晕眩目标3秒,但可以转向.
