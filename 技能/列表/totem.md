技能: Totem
--------------------------

Totem是[Projectile](技能/列表/projectile)的一种.

生成一个不可见的虚拟图腾并可设置刷新/命中/消失后  
所激活的技能组.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| MaxCharges          | charges, ch, c       | 图腾最大可命中次数(支持[占位符](/技能/占位符)与[变量](/技能/变量)) | 0                 |
| onTickSkill           | ontick, ot          | 图腾刷新后所激活的技能组 | 无 |
| onHitSkill           | onhit, oh          | 图腾命中后所激活的技能组 | 无 |
| onEndSkill           | onend, oe          | 图腾消失后所激活的技能组 | 无 ||
| onStartSkill           | onstart, os          | 图腾刷新后所激活的技能组 | 无 |
| Interval         | i, int      | 图腾刷新间隔(刻) | 4                 |
| HorizontalRadius | hRadius, hR | 图腾碰撞箱水平半径(格方块) | 1.25              |
| VerticalRadius   | vRadius, vR | 图腾碰撞箱水平半径(格方块) | 等值于Horizontal Radius |
| Duration         | md          | 图腾最大持续时间 | 200               |
| YOffset          | yo          | 图腾相对施法者位置的垂直偏移量(格方块) | +1                |
| HitPlayers       | hp          | 是否可命中玩家 | false             |
| HitNonPlayers    | hnp         | 是否可命中非玩家 | false             |
| HitTarget        | ht          | 是否可命中技能目标 | true              |
| HitTargetOnly    |             | 是否仅可命中技能 | false             |

尚无示例
----------