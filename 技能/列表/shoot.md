技能: Shoot
--------------------------

向技能目标发射弹射物  
从 MM 5.3.0 起, 该技能所造成伤害的伤害来源为 `Skill` 而非 `Entity_Attack` 或 `Projectile`

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| type                 | t          | 弹射物类型（支持[占位符](/技能/占位符)） | arrow   |
| damage               | d, amount(5.3.0) | 弹射物命中所造成的伤害数值(支持[占位符](技能/占位符)与[计算](技能/计算)) | 5       |
| velocity             | v          | 弹射物移动速度(支持[占位符](技能/占位符)与[计算](技能/计算)) | 5 |
| maxDistance          | md         | 弹射物最大移动距离（格方块 支持[占位符](/技能/占位符)） | 64      |
| hspread              | hs         | 弹射物碰撞箱水平半径（格方块 支持[占位符](技能/占位符)与[计算](技能/计算)）   | 0       |
| vspread              | vs         | 弹射物碰撞箱垂直半径（格方块 支持[占位符](技能/占位符)与[计算](技能/计算)） | 0       |
| poweraffectsvelocity | pav        | [技能威力](实体/威力)是否影响移动速度 | true    |
| interval             | int, i     | 弹射物调用OntickSkill所需时长（单位: 刻） | 4       |
| Gravity              | g           | 弹射物是否拥有重力 | true                 |
| ontickskill          | ontick, ot | 弹射物刷新后所激活的技能组 | 无 |
| onhitskill           | onhit, oh  | 弹射物命中实体后所激活的技能组 | 无 |
| onendskill           | onend, oe  | 弹射物消失后所激活的技能组 | 无 |
| accuracy | ac, a | 弹射物扩散程度（1=百分百命中） | 1 |（格方块 支持[占位符](/技能/占位符)）
| horizontalnoise | hn | 弹射物水平扩散程度（支持[占位符](/技能/占位符） | accuracy的值*4.5|
| verticalnoise | vn | 弹射物垂直扩散程度（支持[占位符](/技能/占位符)） | accuracy的值*45 |
| HorizontalOffset     | hO          | 弹射物发射方向水平旋转角度(弧度角 支持[占位符](技能/占位符)与[计算](技能/计算)) | 0                 |
| VerticalOffset       | vO          | 弹射物发射方向垂直旋转角度(圆心角 支持[占位符](技能/占位符)与[计算](技能/计算)) | 0                 |
| onBounceSkill | onBounce | 弹射物反射开始后所激活的技能组 | 无 |
| bounce | b | 弹射物是否在命中方块后进行弹射 | false |
| bouncevelocity | bv | 弹射物弹射后速度会被乘以多少 | 0.9 |
| pickup | | 弹射物落地后是否可被拾取 | false |
| expiration | expire, e, duration | 弹射物落地后允许被拾取的时间（单位: 刻） | false |
| FromOrigin | fo | 发射点是否位于坐标原点 | false |
| KnockBack | kb |弹射物击中实体后的击退力度 | 0 |
| PieceLevel | pl | 无描述 | 0 | 
| adjustvelocity | av | 是否调整发射速度 | true |
| cauculatefiringangle | cfa | 是否计算发射角度并施加重力使其尽可能击中目标 | false |
| potiontype | ptype, effect, pt, pe | 当弹射物类型为药水时, 药水所拥有的[状态效果](/物品/状态效果) | SLOW(缓慢) |
| potionduration | pduration, pd | 当弹射物类型为药水时, 药水的[状态效果](/物品/状态效果)持续时间（单位: 刻） | 100(5秒) |
| potionlevel | plevel, lvl, pl | 当弹射物类型为药水时, 药水的[状态效果](/物品/状态效果)等级(支持[占位符](技能/占位符)与[计算](技能/计算)) | 1 |
| potioncolor | pc | 当弹射物类型为药水时, 药水外表的颜色（16进制 支持[占位符](技能/占位符)与[计算](技能/计算)） | #FFFFFF |
| ambientparticle**s** | ambient | 当弹射物类型为药水时, 药水飞行途中是否播放粒子效果(支持[占位符](技能/占位符)与[计算](技能/计算)) | false |
| hasparticle**s** | particle**s** | 所附加的状态效果期间是否播放粒子特效 | true |
| overwrite | ow, override, or, force | 是否强制覆盖所附加状态效果生物身上相对应的状态效果 | false |
| tridentitem | tiem, ti | 当弹射物类型为三叉戟时, 对应的物品 | 无 |

Fromorigin 新增于 MM 4.13.0  
OnBounce 新增于 MM 4.14.2  
Bounce 新增于 MM 4.14.2  

可用弹射物类型
----------

| 类型名 | 描述 |
|--------|------|
| Arrow  | 箭矢 |
| SnowBall | 雪球 |
| Egg | 鸡蛋 |
| Enderpearl | 末影珍珠 |
| Potion | 药水 (4.11) |
| Trident | 三叉戟 (MC 1.13 MM 4.11) |
| Block(Falling_Block) | 掉落沙 |
| Lingering_potion | 滞留药水 (4.11) |

提示
----

受伤事件（onHitSkill）受伤害间隔影响, 所以多发抛射物同时命中只能有一发成功触发 onHit

示例
--------

      Skills:
      - shoot{type=ARROW;velocity=5;damage=10}

额外信息
-------

- 别称: shootprojectile