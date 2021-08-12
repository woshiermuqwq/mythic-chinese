技能: Projectile
--------------------------

向目标发射抛射物.

抛射物会在命中目标位置后消失.

当使用MM 4.12或以上时, Minecraft版本必须在1.12.2以上.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| onTick               | oT          | 抛射物刷新后所激活的技能组 | 无 |
| onHit               | oH          | 抛射物命中后所激活的技能组 | 无 |
| onEnd               | oE          | 抛射物消失后所激活的技能组 | 无 |
| Type                 | t           | 抛射物种类,METEOR将令抛射物从天而降而不是水平发射 | NORMAL   |
| Interval             | i           | 抛射物刷新间隔(刻) | 4                 |
| HorizontalRadius     | hRadius, hR | 抛射物碰撞箱水平半径 | 1.25              |
| VerticalRadius       | vRadius, vR | 抛射物碰撞箱垂直半径 | 等值于Horizontal Radius |
| Duration             | d           | 抛射物最大持续时间(刻) | 100               |
| MaxRange             | mr          | 抛射物最大移动距离(格方块) | 40                |
| Velocity             | v           | 抛射物移动速度 | 5                 |
| StartYOffset | syo | 抛射物发射点垂直偏移量(格方块) | 1.0 |
| StartFOffset | sfo | 抛射物发射点前后偏移量(格方块) | 1.0 |
| StartSOffset | sso | 抛射物发射点左右偏移量(格方块) | 1.0 |
| TargetYOffset | syo | 抛射物目标位置垂直偏移量(格方块) | 1.0 |
| HorizontalOffset     | hO          | 抛射物发射方向水平旋转角度(弧度角) | 0                 |
| VerticalOffset       | vO          | 抛射物发射方向垂直旋转角度(圆心角) | 0                 |
| HitPlayers | hp | 抛射物是否可命中玩家 | true |
| HitNonPlayers | hnp | 抛射物是否可命中非玩家实体 | false |
| HitTarget | ht | 抛射物是否可命中技能目标 | true |
| HitTargetOnly | 无 | 抛射物是否仅可命中技能目标 | false
| StopAtEntity | se | 抛射物是否在命中任意实体后消失 | true |
| StopAtBlock | sb | 抛射物是否在命中固体方块后消失 | true |
| HugSurface | hs | 抛射物是否在落到方块上方后继续移动 | false |
| PowerAffectsRange | par | [技能威力](/实体/威力)是否影响抛射物最大移动距离 | true |
| PowerAffectsVelocity | pav | [技能威力](/实体/威力)是否影响抛射物移动速度 | true |
| gravity              | g           | 抛射物重力 | 0                 |
| BulletType | 无 | 抛射物类型 | 无 |

  

注意
-------------

目标选择器: **@origin** 对于Orbital所调用的技能组(如onTick所激活的技能)而言  
选取的是抛射物为坐标原点,而不是施法者.

与origin有关的目标选择器(如@EntitiesNearOrigin),将选取抛射物作为半径范围的中心  
而不是施法者.

与origin无关的目标选择器(如@EIR),则仍选取施法者作为半径范围的中心,所以如果不给  
ntick所激活的技能组写上目标选择器 它会选取施法者作为技能目标).

抛射物类型
-------------

-  抛射物类型用于决定什么作为抛射物本身,而不在限于一个虚拟事物.

| 类型 | 描述 | 附带修改项 | 描述 | 写法 |
|-------|------------|------------|------------|------------|
| ARROW | 箭矢 | 无 | 无 | projectile{bulletType=ARROW;...} |
| BLOCK | 方块 | material | 所选取的方块 | projectile{bulletType=BLOCK;material=STONE;...} |
| ITEM | 物品 | material | 所选取的物品 | projectile{bulletType=ITEM;material=diamond;...} |
| MYTHICITEM | MythicMobs物品 | material | 所选取的MythicMobs物品 | projectile{bulletType=MYTHICITEM;material=Mythicdiamond;...} |
| MOB  | 实体(支持MythicMobs实体) | mob | 所选取的实体 | projectile{bulletType=MOB;mob=SkeletonKing;...} |

示例
--------

    IceBolt:
      Skills:
      - projectile{onTick=IceBolt-Tick;onHit=IceBolt-Hit;v=8;i=1;hR=1;vR=1}
    IceBolt-Tick:
      Skills:
      - effect:particles{p=snowballpoof;amount=20;speed=0;hS=0.2;vS=0.2} @origin
    IceBolt-Hit:
      Skills:
      - damage{a=10}
      - potion{type=SLOW;duration=100;lvl=2}
