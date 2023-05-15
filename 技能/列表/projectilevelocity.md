技能: Projectile Velocity（5.3.0）
---

修改所对应抛射物的当前动量  
作用于技能: [Projectile](/技能/列表/projectile) 与 [Missle](/技能/列表/missile)

可用修改模式:

-   SET(设置)
-   ADD(加)
-   SUBTRACT(减)
-   MULTIPLY(乘以)
-   DIVIDE(除)
-   MOD(除以后取余)

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| mode      | m       | 修改模式 | SET  |
| velocityx | vx, x   | X轴速度（支持[占位符](/技能/占位符)与[计算](/技能/计算)）  | 1             |
| velocityy | vy, y   | Y轴(垂直)速度, 值为负数时, 值越小摔落后所受到的伤害越高（支持[占位符](/技能/占位符)与[计算](/技能/计算)）  | 1             |
| velocityz | vz, z   | Z轴速度（支持[占位符](/技能/占位符)与[计算](/技能/计算)）  | 1   |
| relative | r | 是否基于当前动量调整 | false |

示例（实体配置）
--------

```yaml
测试:
 Type: Zombie
 Options:
  NoAI: true
 Skills:
 - projectile{ontick=[  - e:p{p=flame} ];os=[  - pvelocity{y=-5} ]} @trigger ~ondamaged
```
施法者受伤后向攻击者发射抛射物, 若抛射物五秒内未消失则立刻落到地面

拓展信息
---

- 缩写: pvelocity