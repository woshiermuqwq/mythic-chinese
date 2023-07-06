技能: Projectile
--------------------------

从施法者位置向技能目标发射抛射物.  

当使用MM 4.12或以上时, Minecraft版本必须在1.12.2以上.

当使用 MM 4.13 及以上时, 服务端必须为 Paper 或其分支.

抛射类技能修改项
---

下列修改项作用于:
  * [Projectile](/技能/列表/projectile)
  * [Missile](/技能/列表/Missile)
  * [Orbital](/技能/列表/Orbital)
  * [Totem](/技能/列表/totem)  
修改项的描述可能有所不同(如 `onTickSkill` 对Projectile而言是以抛射物为施法对象, 而对Orbital而言则为环绕整体)  
具有不同描述的修改项会加入其它技能的页面中


| 修改项名 | 别称    | 描述        | 默认值 |
|-----------|------------|------------------|---------------|
| Accuracy | ac, a | 抛射物发射方向的偏差程度, 1为无偏差 | 1 |
| BulletType | bullet, b | 抛射物类型[[2]](#抛射物类型) | 无 |
| DrawHiitBox |  | 是否在抛射物移动时使用粒子绘制周围实体的碰撞箱 | false |
| EndOffset | esoffset, eo | 抛射物目标位置的双轴偏移<br>正数为向左 向下偏, 负数反之（格方块 支持[占位符](技能/占位符)) | 无 |
| HorizontalNoise | hn | 抛射物发射方向的水平偏差程度 | Accuracy的值 * 45 |
| VerticalNoise | vn | 抛射物发射方向的垂直偏差程度 | Accuracy的值 * 4.5 |
| HorizontalRadius     | hRadius, hr, r | 抛射物碰撞箱水平总长度 | 1.25 |
| VerticalRadius       | vRadius, vR | 抛射物碰撞箱垂直总长度 | 等值于Horizontal Radius |
| HitSelf |  | 抛射物是否可命中施法者 | false |
| HitPlayers | hp | 抛射物是否可命中玩家 | true |
| HitNonPlayers | hnp | 抛射物是否可命中非玩家实体 | **false** |
| HitTarget | ht | 抛射物是否可命中技能目标 | true |
| HitTargetOnly | hto | 抛射物是否仅可命中技能目标 | false |
| HitArmorStands | ha | 抛射物是否可命中盔甲架 | false |
| HitConditions | conditions, cond, c | 若所命中的目标不符合条件, 则不会判定命中该实体 | 无 |
| Interval             | int, i | onTick的激活间隔（游戏刻 ）<br>不影响抛射物速度 影响抛射物碰撞判定 | 1(4.13以下为4)  |
| ImmuneDelay | immune, id | 所命中实体可再次被该抛射物所命中的所需时间（单位: 刻） | 2000 |
| Maxduration          | md, duration, d           | 抛射物最大持续时间(刻 支持[占位符](技能/占位符)） | 100               |
| MaxRange             | mr          | 抛射物最大移动距离(格方块 支持[占位符](技能/占位符)） | 40                |
| onTickSkill | onTick, ot, skill, s, meta, m          | 抛射物飞行期间不断激活的技能组 | 无 |
| onHitSkill | onHit, oh         | 抛射物命中实体后所激活的技能组 | 无 |
| onEndSkill  | onEnd, oe          | 抛射物消失后所激活的技能组 | 无 |
| onStartSkill  | onStart, os          | 抛射物被发射后所激活的技能组 | 无 |
| onHitBlockSkill | onHitBlock, ohb | 抛射物命中方块后所激活的技能组 | 无 |
| PowerAffectsRange | par | [技能威力](/实体/威力)是否影响抛射物最大移动距离 | true |
| PowerAffectsVelocity | pav | [技能威力](/实体/威力)是否影响抛射物移动速度 | true |
| ReqiureLineOfSight | rlos, los | 于抛射物发射时立刻判断[坐标原点](/目标选择器/坐标原点)与起始点之间是否存在该事物<br> 若有则调用相关技能<br>为`true`时判断一切可命中事物, 为`false`时禁用该功能 | PLAYER_ONLY（仅限玩家） |
| StartYOffset | syo | 抛射物发射点垂直偏移量（格方块, 正上负下 支持[占位符](技能/占位符)） | 1.0 |
| StartFOffset | sfo | 抛射物发射点前后偏移量（格方块, 正前负后 支持[占位符](技能/占位符)) | 1.0 |
| StartSOffset | sso | 抛射物发射点左右偏移量（格方块 正右负左 支持[占位符](技能/占位符)） | 0.0 |
| StopAtEntity | se | 抛射物是否在命中任意实体后消失 | true |
| StopAtBlock | sb | 抛射物是否在命中固体方块后消失 | true |
| TargetYOffset | targetty, tyo | 抛射物目标位置垂直偏移量(格方块 正上负下 支持[占位符](技能/占位符)） | 1.0 |
| Tickinterpolation | interpolation, ti | 抛射物每俩次刷新之间会弥补多少个点<br>值越大, 抛射物越精确（5.3.2） | 0 |
| Velocity             | v  | 抛射物1秒（默认20游戏刻）内所能经过的方块（重力为0的情况下 支持[占位符](技能/占位符)）| 5

* 修改项: `DrawHitBox` 新增于 MM 5.3.0
* 修改项: `RequireLineOfSight` 新增于 MM 5.3.0
* 修改项: `OnHitBlockSkill` 新增于 MM 5.3.0
* 修改项: `FromOrigin` 新增于 MM 4.11.0  
* 修改项: `EndOffset` 新增于 MM 4.14.0  
* 修改项: `BulletColor` 新增于 MM 4.14.0  
* 修改项: `ImmuneDelay` 新增于 MM 5.2.6

独立修改项
----------

下列修改项仅作用于Projectile本身

| 修改项名 | 别称    | 描述        | 默认值 |
|-----------|------------|------------------|---------------|
| BulletForwardOffset | bulletfo, bulletoffset | 抛射物碰撞箱的前后偏移, 正数为前（5.3.3 格方块） | 1.8 |
| HighAccuracyMode | ham | 对什么事物启用高精度, 启用后将解决速度过快会穿过该事物的漏洞<br>为`true`时判断一切可命中事物, 为`false`时禁用该功能 | PLAYER_ONLY（仅限玩家） |
| HugSurface | hs | 抛射物是否在落到方块上方后继续移动 | false |
| HugLiquid | hl | 抛射物是否在落到流体上方后继续移动 | false |
| HeightFromSurface | hfs | 当抛射物类型为 Meteor 时, 抛射物离技能目标位置多高（格方块 支持[占位符](技能/占位符)) | 0.5 |
| HorizontalOffset     | hO          | 抛射物发射方向水平旋转角度(角度制 正右负左 支持[占位符](技能/占位符)) | 0                 |
| VerticalOffset       | vO          | 抛射物发射方向垂直旋转角度角度制）<br>角度制简单理解就是发射距离越大<br>与预期轨迹的夹角就越大<br>实际值应 x  0.0174532925199544<br>支持[占位符](技能/占位符) | 0    |
| Gravity              | g           | 抛射物重力 | 0                 |
| MaxClimbHeight | mch | 抛射物在终止前尝试增高Y轴位置的次数 | 3 |
| MaxDropHeight | mdh | 抛射物在终止前尝试拉低Y轴位置的次数 | 10 |
| onBounceSkill | onBounce | 抛射物反射开始后所激活的技能组 | 无 |
| Bounce               | bounces, b | 抛射物是否在命中方块后进行弹射 | false |
| Bouncevelocity       | bv | 抛射物弹射后速度会被乘以多少 | 0.9 |
| StartingDirection | startingdir, startdir, sdir | 抛射物起始朝向 | 无 |
| Type                 | 无 | [抛射物种类](#抛射物种类)  | NORMAL   |
| TargetYOffset | targetty, tyo | 抛射物目标位置垂直偏移量(格方块 正上负下 支持[占位符](技能/占位符)） | 1.0 |

* 修改项: `HighAccuracyMode` 新增于 MM 5.3.0
* 修改项: `StartingDirection` 新增于 MM 4.14.0  
* 修改项: `OnBounce` 新增于 MM 4.14.0 （付费版内容）
* 修改项: `Bounce` 新增于 MM 4.14.0 （付费版内容）
* 修改项: `HugLiquid` 新增于 MM 4.14.0

抛射物类型
---

可用类型:
* Arrow: 箭矢
* Block: 方块
* Mob: 实体
* Item: 原版物品
* MythicItem: Mythic物品
* Rstand: 非发包盔甲架
* Tracking: 纯发包盔甲架
* Display: NMS发包（1.19.4+）
* TextDisplay（Text）: 文本（1.19.4+）

下列修改项作用于特定类型

| 类型名称 | 描述 | 修改项 | 别称 | 描述 | 默认值 |
| - | - | - | - | - | - |
| Arrow | 箭矢 | arrowType | 无 | 箭矢类型（可为Normal(普通箭)/Special(药水箭)/Trident(三叉戟)) | Normal（普通） |
| Block | 方块 | bulletmaterial |  material, mat | 所调用的原版方块ID | Stone（石头） |
| Block | 方块 | bulletsmall | 无 | 所调用的方块是否为小方块(方块戴在盔甲架头上) | 否 |
| Block | 方块 | audience | 无 | 方块仅显示于给定事物（可用事物见[Audience](/技能/特效技能列表#特效技能)） | world |
| Block | 方块 | bulletspin | bspin | 方块的水平旋转速度 | 0 |
| MythicItem/Item  | Mythic/原版物品 | bulletmaterial |  material, mat | 所调用的原版或Mythic物品ID | Stone（石头） |
| MythicItem/Item  | Mythic/原版物品 | bulletenchanted | enchanteds | 所调用的原版	或Mythic物品是否附魔发光 | false |
| MythicItem/Item  | Mythic/原版物品 | bulletcolor | 无 | 所调用的原版或Mythic物品的颜色（R,G,B格式） | 无 |
| MythicItem/Item  | Mythic/原版物品 | bulletmodel | m | 所调用的原版或Mythic物品的 **CustomModelData** 标签值 | 0 |
| MythicItem/Item  | Mythic/原版物品 | audience | 无 | 物品仅显示于特定事物（可用事物见[Audience](/技能/特效技能列表#特效技能)） | world |
| Tracking | 盔甲架 | bulletmaterial |  material, mat | 位于盔甲架头部的原版或Mythic物品ID | Stone（石头） |
| Tracking | 盔甲架 | audience | 无 | 盔甲架仅显示于给定事物（可用事物见[Audience](/技能/特效技能列表#特效技能)） | world |
| Tracking | 盔甲架 | yaw | 无 | 盔甲架朝向的水平旋转角度（X轴旋转） | 0 |
| Tracking | 盔甲架 | pitch | 无 | 盔甲架朝向的视角俯仰角度（Y轴旋转） | 0 |
| Tracking | 盔甲架 | roll | 无 | 盔甲架朝向的左右歪头角度（Z轴旋转） | 0 |
| Tracking | 盔甲架 | yawspeed | ys | 抛射物每次刷新时为盔甲架的水平旋转角度加上的值（X轴旋转速度） | 0 |
| Tracking | 盔甲架 | pitchspeed | ps | 抛射物每次刷新时为盔甲架的视角俯仰角度加上的值（Y轴旋转速度） | 0 |
| Tracking | 盔甲架 | rollspeed | rs | 抛射物每次刷新时为盔甲架的左右歪头角度加上的值（Z轴旋转速度） | 0 |
| Tracking | 盔甲架 | rotation | rot | 盔甲架朝向的三轴旋转（格式: `rot=x,y,z`） | 0,0,0 |
| Mob | 实体 | mob | mobtype, mm | 所调用的实体内部名(不支持原版实体) | 无 |
| Mob | 实体 | bulletskillable | bk | 所调用的实体是否执行自带技能 | true |
| Mob | 实体 | bulletspin | bspin | 所调用的实体的水平旋转速度 | 0 |
| Mob | 实体 | bulletmathdirection | bmd | 所调用的实体朝向是否与抛射物朝向保持同步 | false |
| Mob | 实体 | BulletOffet（5.3.2） | bforward | 抛射物所调用**生物**的上下偏移, 正数为上（5.3.3 格方块） | 1.35 |
| Text | 文本 | backgroundcolor | color | 文本的背景色（格式: `color=R,G,B`) | 1073741824 |
| Text | 文本 | bullettext | text | 文本的内容 | * |
| Text | 文本 | bulletbillboard | billboard | 文本的聚焦方式 | Center（居中） |
| Text | 文本 | bulletscale | scale | 文本三轴缩放（格式: `scale=数值,数值,数值`） | 0.5,0.5,0.5 |
| Display | NMS发包 | 上述所有修改项 | | | |



子技能组
---

onStartSkill的[坐标原点](/目标选择器/origin)为抛射物出现时的位置  
onTickSkill的[坐标原点](/目标选择器/origin)为激活该技能组时时抛射物所处的位置  
onHitSkill的[坐标原点](/目标选择器/origin)为命中实体时抛射物所处位置  
onEndSkill的[坐标原点](/目标选择器/origin)为抛射物消失时所处的位置  
onBounceSkill的[坐标原点](/目标选择器/origin)为命中实体时抛射物所处位置  
onHitBlockSkill的[坐标原点](/目标选择器/origin)为命中方块时抛射物所处位置  
**强烈建议阅读[坐标原点](/目标选择器/origin), 因其通常用于制作范围伤害**  
(出于篇幅已过长 本页不介绍坐标原点具体功能)

若技能组目标选择器为空则选取坐标原点  

Projectile的施法者死亡后Projectile将消失, 但不激活onEndSkill  


抛射物种类
---------

- 抛射物种类决定抛射物的发射位置与移动方式

| 种类 | 发射位置 | 移动方式 |
| ---- | -------- | ------- |
| NORMAL | 施法者位置 | 从施法者位置发射（Fromorigin为true时从坐标原点发射） |
| METEOR | 技能目标位置 | 从技能目标位置发射并垂直下坠（重力为其速度） |

示例
--------

```yaml
测试:
 Skills:
 - projectile{hnp=true;ontick=[  - e:particles{p=flame;a=20;s=0;hS=0.2;vS=0.2} @origin ];oh=[  - damage{a=10} - potion{t=SLOW;d=100;l=2} ];v=8;i=1;hR=1;vR=1}

另一种写法:
 Skills:
 - projectile{
   velocity=3;
   interval=1;
   hitnonplayers=true;
   onTick=[
   - e:p{p=flame;fromOrigin=true} @origin
   ];oh=[
   - damage{a=10}
   - potion{t=SLOW;d=100;l=2}
   ]} @target ~onTimer:20
```

旧写法:

```yaml
测试:
 Skills:
 - p{ot=测试-Tick;oh=测试-Hit;v=8;i=1;hr=1;vr=1;hnp=true}

测试-Tick:
 Skills:
 - e:p{p=flame;a=20;s=0;hS=0.2;vS=0.2} @origin
测试-Hit:
 Skills:
 - d{a=10}
 - potion{t=SLOW;d=100;l=2}
```

提示
------

- onTick最后一次激活 优先于 onHit 优先于 onEnd
- 偏差都是基于施法者的, 让抛射物从别的地方发射会给人一种 没有偏差 的错觉  
  解决方法就是使用@RLNT+@Origin目标选择器制作随机

额外信息
-------

- [x] 缩写: p

使用技巧
-----

由于命中方块不会激活onend, 那如果你想要做到类似于  
抛射物不会激活特效, 除非命中方块与实体 的效果的话  

```yaml
 Skills:
 - projectile{
  ontick=[
    - effect:particles{particle=flame}
    ];
  onhit=[
    - message{m="中嘞实体, 哥"} @self
    - aura{duration=100;auraname=命中实体} @self
    ];
  onend=[
    - message{m="中嘞方块, 哥"} @self ?!hasaura{aura=命中实体}
    ]} @forward{f=9999}
```
目前如果这个抛射物没有命中任何事物, 照样会发送 `中嘞方块, 哥`, 所以:```yaml
```yaml
 Skills:
 - projectile{maxduration=120;
  ontick=[
    - effect:particles{particle=flame}
    ];
  onhit=[
    - message{m="中嘞实体, 哥"} @self
    - aura{duration=100;auraname=命中实体} @self
    ];
  onend=[
    - message{m="中嘞方块, 哥"} @self ?!hasaura{aura=命中实体} ?!hasaura{aura=未命中}
    ]} @forward{f=9999}
 - projectile{maxduration=119;onend=[  - aura{duration=100;auraname=未命中} @self ]} @forward{f=9999}
```
多写一条projectile, 同时由于第二条projectile的最大持续时间比第一条少1tick  
会比第一条projectile早1tick结束, 这意味着光环"未命中"会在第一条projectile  
结束之前给予给施法者, 然后由于条件限制, 第一条的onendskill就不会被激活

关于低版本的视角影响偏移的解决方法
---

低版本目标选择器: [@forward](/技能/目标选择器) 无选项: `lockpitch`  
以将projectile发射时的pitch锁定为0  
以至于低版本最简单的方法是在发射projectile前  
通过修改nbt的方式以将pitch设为0  
随后激活速度为0的[Spin](/技能/特效技能/spin)锁定视角  
这时任何在[Spin](/技能/特效技能/spin)技能期间激活的projectile  
其偏移都不会被实体的pitch影响  
如, `sso`正常情况下实体抬头的实际偏移量远小于正常偏移量  
但现在不论实体的头是抬着的还是低着的, 都不会影响偏移量
```yaml
 - skill{s=[
  - setvar{var=skill.1;t=float;v=<caster.l.yaw>-1}
  - delay 1
  - cmdc="entitydata @s {Rotation:[<caster.var.1>f]}";astarget=true;asop=true}
  - spin{d=22;v=0}
  - delay 20
  - projectile{ot=[  - e:p ];se=false;sb=false;i=1;sso=3} @forward{f=999}
  ]} @self ~oninteract
```

关于 MM 5.3.0 的纯发包改动
---

- **抛射物现为纯发包（除非种类为实体(`bullet=MOB`, 包括箭矢)）**
- 这意味着当种类为方块(`bullet=block`)时且命中方块会停止时, 命中方块**不再生成一个真正的方块**
- 这还意味着该技能支持特效技能的 **Audience**, 令抛射物仅渲染于某些玩家