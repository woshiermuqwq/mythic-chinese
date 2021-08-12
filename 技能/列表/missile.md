技能: Missile
--------------------------

向目标发射追踪抛射物.

抛射物会在命中目标位置后消失.

修改项
----------

| 修改项名 | 别称      | 描述                      | 默认值 |
|--------- |-----------|---------------------------|--------|
| Inertia  | in        | 抛射物惯性,值越大越难转向  | 1.5   |
| onTick   | oT        | 抛射物刷新后所激活的技能组 | 无    |
| onHit    | oH        | 抛射物命中后所激活的技能组 | 无    |
| onEnd    | oE        | 抛射物消失后所激活的技能组 | 无    |
| onStart  | oS        | 抛射物发射后所激活的技能组 | 无    |
| internal | i, int    | 抛射物刷新间隔(刻)         | 4     |
| HorizontalRadius | hRadius, hR, r | 抛射物碰撞箱垂直半径(格方块) | 1.25 |
| VerticalRadius | vRadius, vR, r | 抛射物碰撞箱水平半径(格方块) | 等值于HorizontalRadius |
| MaxDuration | md | 抛射物最大持续时间(刻) | 100 |
| MaxRadius | mr | 抛射物最大移动距离(格方块) | 40 |
| Vlocity | v | 抛射物移动速度 | 5 |
| StartYOffset | syo | 抛射物发射点垂直偏移量(格方块) | 1.0 |
| StartFOffset | sfo | 抛射物发射点前后偏移量(格方块) | 1.0 |
| TargetYOffset | syo | 抛射物目标位置垂直偏移量(格方块) | 1.0 |
| HitPlayers | hp | 抛射物是否可命中玩家 | true |
| HitNonPlayers | hnp | 抛射物是否可命中非玩家实体 | false |

示例
--------

