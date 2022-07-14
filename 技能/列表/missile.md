技能: Missile
--------------------------

向技能目标发射追踪抛射物.

抛射物会在命中目标位置后消失.

修改项
----------

| 修改项名 | 别称      | 描述                      | 默认值 |
|--------- |-----------|---------------------------|--------|
| inertia  | in        | 抛射物惯性,值越大越难转向  | 1.5   |
| onTickSkill   | onTick, ot        | 抛射物刷新后所激活的技能组 | 无    |
| onHitSkill    | onhit, oh        | 抛射物命中后所激活的技能组 | 无    |
| onEndSkill    | onend, oe        | 抛射物消失后所激活的技能组 | 无    |
| onStartSkill  | onstart        | 抛射物发射后所激活的技能组 | 无    |
| internal | int, i    | 抛射物刷新间隔(刻)         | 4     |
| HorizontalRadius | hRadius, hR, r | 抛射物碰撞箱垂直半径(格方块) | 1.25 |
| VerticalRadius | vRadius, vR, r | 抛射物碰撞箱水平半径(格方块) | 等值于HorizontalRadius |
| MaxDuration | md | 抛射物最大持续时间(刻) | 100 |
| MaxRadius | mr | 抛射物最大移动距离(格方块) | 40 |
| Vlocity | v | 抛射物移动速度 | 5 |
| StartYOffset | syo | 抛射物发射点垂直偏移量(格方块) | 1.0 |
| StartFOffset | sfo | 抛射物发射点前后偏移量(格方块) | 1.0 |
| TargetYOffset | tyo | 抛射物目标位置垂直偏移量(格方块) | 1.0 |
| HitPlayers | hp | 抛射物是否可命中玩家 | true |
| HitNonPlayers | hnp | 抛射物是否可命中非玩家实体 | true |
| HitTarget | ht | 抛射物是否可命中技能目标 | true |
| HitTargetOnly | 无 | 抛射物是否仅可命中技能目标 | false
| StopAtEntity | se | 抛射物是否在命中任意实体后消失 | true |
| StopAtBlock | sb | 抛射物是否在命中固体方块后消失 | true |
| HugSurface | hs | 抛射物是否在落到方块上方后继续移动 | false |
| PowerAffectsRange | par | [技能威力](/实体/威力)是否影响抛射物最大移动距离 | true |
| PowerAffectsVelocity | pav | [技能威力](/实体/威力)是否影响抛射物移动速度 | true |
| fromOrigin | fo | 抛射物发射点是否为施法者的坐标原点 | false |

  
注意
-------------

目标选择器: **@origin** 对于Orbital所调用的技能组(如onTick所激活的技能)而言  
选取的是抛射物为坐标原点,而不是施法者.

与origin有关的目标选择器(如@EntitiesNearOrigin),将选取抛射物作为半径范围的中心  
而不是施法者.

与origin无关的目标选择器(如@EIR),则仍选取施法者作为半径范围的中心

在 MM 4.9 以下的版本, 若不给ontick/hit/end/start 所激活的技能组写上目标选择器 它会选取施法者作为技能目标).  

在 MM 4.9 及以上的版本, 即使不写目标选择器也会选取 抛射物位置、所命中的实体 为技能目标

示例
--------

此实体每5秒朝半径16格范围内的所有玩家各发射一发:  
飞行速度为4 惯性为0.75 碰撞箱体积为1方块 的追踪抛射物

```yaml
# 实体配置
追踪抛射物测试实体:
 Type: ZOMBIE
 Skills:
 - skill{s=[
  - missile{ot=[
    - e:particles{p=flame;a=1} @origin
    ];oh=[
    - e:p{p=lava;a=50;hS=1;vS=1}
    - sound{s=entity.generic.explode;v=1;p=0}
    - d{a=1337;i=false}
    ];v=4;i=1;hR=1;vR=1;in=0.75}
  ]} @pir{r=16} ~onTimer:100
```
旧版写法
```yaml
# 实体配置
追踪抛射物测试实体:
 Type: ZOMBIE
 Skills:
 - missile{ot=追踪Tick;oh=追踪Hit;v=4;i=1;hR=1;vR=1;in=0.75} @pir{r=16} ~onTimer:100

# 技能配置
追踪Tick:
 Skills:
 - effect:particles{p=flame} @origin
追踪Hit:
 Skills:
 - damage{a=10}
```

拓展信息:
---------

- [x] 别称: mi