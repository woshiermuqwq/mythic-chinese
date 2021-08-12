技能: Shoot
--------------------------

向目标发射弹射物.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| type                 | t          | 弹射物类型. | arrow   |
| damage               | d          | 弹射物命中所造成的伤害数值 | 5       |
| velocity             | v          | 弹射物移动速度| 1       |
| maxDistance          | md         | 弹射物最大持续时间 | 64      |
| hspread              | hs         | 弹射物碰撞箱水平半径   | 0       |
| vspread              | vs         | 弹射物碰撞箱垂直半径 | 0       |
| poweraffectsvelocity | pav        | [技能威力](实体/威力)是否影响移动速度 | true    |
| interval             | int, i     | 弹射物刷新间隔 | 4       |
| ontickskill          | ontick, ot | 弹射物刷新后所激活的技能组 | 无 |
| onhitskill           | onhit, oh  | 弹射物命中后所激活的技能组 | 无 |
| onendskill           | onend, oe  | 弹射物消失后所激活的技能组 | 无 |

可用弹射物类型
----------

| 类型名 | 描述 |
|--------|------|
| Arrow  | 箭矢 |
| SnowBall | 血球 |
| Egg | 鸡蛋 |
|enderpertal | 末影珍珠 |
| potion | 药水 |
| trident | 三叉戟 |
| lingering_potion | 滞留药水 |

示例
--------

      Skills:
      - shoot{type=ARROW;velocity=5;damage=10}
