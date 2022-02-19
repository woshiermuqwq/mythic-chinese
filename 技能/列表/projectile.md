技能: Projectile
--------------------------

从施法者位置向技能目标发射抛射物.

抛射物会在命中目标位置后消失.

当使用MM 4.12或以上时, Minecraft版本必须在1.12.2以上.

当使用 MM 4.13 及以上时, 服务端必须为 Paper 或其分支

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| onTickSkill | onTick, ot, skill, s, meta, m          | 抛射物刷新后所激活的技能组 | 无 |
| onHitSkill | onHit, oh         | 抛射物命中实体后所激活的技能组 | 无 |
| onEndSkill  | onEnd, oe          | 抛射物消失后所激活的技能组 | 无 |
| onStartSkill               | onStard, os          | 抛射物被发射后所激活的技能组 | 无 |
| onBounceSkill | onBounce | 抛射物反射开始后所激活的技能组 | 无 |
| bounce | b | 抛射物是否在命中方块后进行弹射 | false |
| bouncevelocity | bv | 抛射物弹射后速度会被乘以多少 | 0.9 |
| Type                 | 无           | 抛射物种类[[1]](#抛射物种类)  | NORMAL   |
| Interval             | int, i           | 抛射物刷新间隔(刻) | 4                 |
| HorizontalRadius     | hRadius, hR | 抛射物碰撞箱水平半径 | 1.25              |
| VerticalRadius       | vRadius, vR | 抛射物碰撞箱垂直半径 | 等值于Horizontal Radius |
| Duration             | d           | 抛射物最大持续时间(刻 支持[占位符](技能/占位符)与[变量](技能/变量)） | 100               |
| MaxRange             | mr          | 抛射物最大移动距离(格方块 支持[占位符](技能/占位符)与[变量](技能/变量)） | 40                |
| Velocity             | v           | 抛射物移动速度（支持[占位符](技能/占位符)与[变量](技能/变量)） | 5                 |
| Accuracy | ac, a | 抛射物发射方向的偏差程度, 1为无偏差 | 1 |
| HorizontalNoise | hn | 抛射物发射方向的水平偏差程度 | Accuracy的值 * 45 |
| VerticalNoise | vn | 抛射物发射方向的垂直偏差程度 | Accuracy的值 * 4.5 |
| StartingDirection | startingdir, startdir, sdir | 抛射物起始朝向 | 无 |
| EndOffset | esoffset, eo | 抛射物目标位置的双轴偏移<br>正数为向左 向下偏, 负数反之（支持[占位符](技能/占位符)与[变量](技能/变量)
| StartYOffset | syo | 抛射物发射点垂直偏移量（格方块 支持[占位符](技能/占位符)与[变量](技能/变量)） | 1.0 |
| StartFOffset | sfo | 抛射物发射点前后偏移量（格方块 支持[占位符](技能/占位符)与[变量](技能/变量)) | 1.0 |
| StartSOffset | sso | 抛射物发射点左右偏移量（格方块 支持[占位符](技能/占位符)与[变量](技能/变量)） | 1.0 |
| TargetYOffset | targetty, tyo | 抛射物目标位置垂直偏移量(格方块 支持[占位符](技能/占位符)与[变量](技能/变量)） | 1.0 |
| HorizontalOffset     | hO          | 抛射物发射方向水平旋转角度(弧度角 支持[占位符](技能/占位符)与[变量](技能/变量)) | 0                 |
| VerticalOffset       | vO          | 抛射物发射方向垂直旋转角度(圆心角 支持[占位符](技能/占位符)与[变量](技能/变量)) | 0                 |
| HitTarget | ht | 抛射物是否可命中施法者 | false |
| HitPlayers | hp | 抛射物是否可命中玩家 | true |
| HitNonPlayers | hnp | 抛射物是否可命中非玩家实体 | false |
| HitTarget | ht | 抛射物是否可命中技能目标 | true |
| HitTargetOnly | hto | 抛射物是否仅可命中技能目标 | false |
| HitArmorStands | ha | 抛射物是否可命中盔甲架 | false |
| StopAtEntity | se | 抛射物是否在命中任意实体后消失 | true |
| StopAtBlock | sb | 抛射物是否在命中固体方块后消失 | true |
| HugSurface | hs | 抛射物是否在落到方块上方后继续移动 | false |
| HugLiquid | hl | 抛射物是否在落到流体上方后继续移动 | false |
| HeightFromSurface | hfs | | 0.5 |
| PowerAffectsRange | par | [技能威力](/实体/威力)是否影响抛射物最大移动距离 | true |
| PowerAffectsVelocity | pav | [技能威力](/实体/威力)是否影响抛射物移动速度 | true |
| Gravity              | g           | 抛射物重力 | 0                 |
| BulletType | bullet, b | 抛射物类型[[2]](#抛射物类型) | 无 |
| BulletSpin | bspin | 抛射物类型为实体/物品时, 该物品/实体的视角旋转速度 | 0 |
| BulletColor | bcolor | 抛射物类型为物品且该物品可染色时, 该物品的颜色 | 无 |
| hitConditions | conditions, cond, c | 若所命中的目标不符合条件, 则不会判定命中该实体 | 无 |
| FromOrigin | fo | 发射点是否位于坐标原点 | false |

EndOffset 新增于 MM 4.14.0  
StartingDirection 新增于 MM 4.14.0  
FromOrigin 新增于 MM 4.14.0  
OnBounce 新增于 MM 4.14.0  
Bounce 新增于 MM 4.14.0  
BulletColor 新增于 MM 4.14.0  
HugLiquid 新增于 MM 4.14.0

注意
-------------

目标选择器: **@origin** 对于Orbital所调用的技能组(如onTick所激活的技能)而言  
选取的是抛射物为坐标原点,而不是施法者.

与origin有关的目标选择器(如@EntitiesNearOrigin),将选取抛射物作为半径范围的中心  
而不是施法者.

与origin无关的目标选择器(如@EIR),则仍选取施法者作为半径范围的中心

在 MM 4.9 以下的版本, 若不给ontick/hit/end/start 所激活的技能组写上目标选择器 它会选取施法者作为技能目标).  

在 MM 4.9 及以上的版本, 即使不写目标选择器也会选取 抛射物位置、所命中的实体 为技能目标

抛射物类型
-------------

-  抛射物类型用于决定什么作为抛射物本身,而不在限于一个虚拟事物.

| 类型 | 描述 | 附带修改项 | 描述 | 写法 |
|-------|------------|------------|------------|------------|
| ARROW | 箭矢 | 无 | 无 | projectile{bulletType=ARROW;...} |
| BLOCK | 方块 | material | 所选取的方块 | projectile{bulletType=BLOCK;material=STONE;...} |
| ITEM | 物品 | material | 所选取的物品 | projectile{bulletType=ITEM;material=diamond;...} |
| MYTHICITEM | MythicMobs物品 | material | 所选取的MythicMobs物品 | projectile{bulletType=MYTHICITEM;material=Mythicdiamond;...} |
| MOB（mm, mmobs）  | 实体(支持MythicMobs实体) | mob | 所选取的实体 | projectile{bulletType=MOB;mob=SkeletonKing;...} |
| TRACKING（4.14.0） | 头戴方块的盔甲架,方块的中心为抛射物的位置 | 无 | 无 | 无 |

抛射物种类
---------

- 抛射物种类决定抛射物的发射位置与移动方式

| 种类 | 发射位置 | 移动方式 |
| ---- | -------- | ------- |
| NORMAL | 施法者位置 | 水平 |
| METEOR | 技能目标位置 | 从上往下 |

示例
--------

    Test:
     Skills:
     - projectile{ontick=[  - e:particles{p=flame;a=20;s=0;hS=0.2;vS=0.2} @origin ];oh=[  - damage{a=10}  - potion{t=SLOW;d=100;l=2} ];v=8;i=1;hR=1;vR=1}

     Skills:
      - projectile{
          velocity=3;
          interval=1;
          onTick=[
            - e:p{p=flame;fromOrigin=true} @origin
          ];
        } @target ~onTimer:20

旧写法:

    测试:
     Skills:
     - p{ot=测试-Tick;oh=测试-Hit;v=8;i=1;hr=1;vr=1}

    测试-Tick:
     Skills:
     - e:p{p=flame;a=20;s=0;hS=0.2;vS=0.2} @origin
    测试-Hit:
     Skills:
     - d{a=10}
     - potion{t=SLOW;d=100;l=2}

提示
------

- onTick最后一次激活 优先于 onHit 优先于 onEnd
- 偏差都是基于施法者的, 让抛射物从别的地方发射会给人一种 没有偏差 的错觉  
  解决方法就是使用@RLNT+@Origin目标选择器制作随机

额外信息
-------

- [x] 缩写: p