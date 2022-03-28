技能: Totem
--------------------------

在技能目标位置形成虚体  
可理解为:
`Type`为 `Meteor`  
`StopAtBlock/Entity` 为 `Falce`
的技能: [Projectile](技能/列表/projectile)

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| MaxCharges          | charges, ch, c       | 图腾最大onHit可调用次数(支持[占位符](/技能/占位符)) | 0                 |
| onTickSkill           | ontick, ot          | 图腾刷新后所激活的技能组 | 无 |
| onHitSkill           | onhit, oh | 图腾命中/消失后所激活的技能组 | 无 |
| onEndSkill           | onend, oe  | 图腾消失后所激活的技能组 | 无 ||
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

示例
----------

```yaml
2:
 Skills:
 - totem{ontickskill=[
     - e:particles
   ];
   charges=1;
   hitnonplayers=true;
   onhitskill=[
   - damage
   ]} @self
```