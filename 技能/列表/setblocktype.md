技能: Set Block Type
--------------------------

修改指定位置的方块种类.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| material  | mat, m, type, t | 方块种类 | DIRT          |
| materialdata      | md, data, dv      | 方块特殊值           | 0             |
| age | a | 若采用作物方块, 作物方块的成长进度（支持[占位符](/技能/占位符)） | 0             |
| waterlogged | wlogged | 若采用台阶/活板门/台阶/栅栏（墙）, 是否被水方块填充 | false  |
| blockface | bf | 若采用的方块拥有朝向, 放置后的朝向 | NORTH  |
| axis | y | "X"代表方块朝向东西, "Y "方块垂直摆放, 而 "Z"代表方块的南北方向, 就比如原木的摆向（支持[占位符](/技能/占位符)） | 无             |
| bisectedhalf | bhalf | 无描述 | TOP(上)  |
| slabtype | sb | 若采用台阶, 台阶的方位（上/下台阶） | Bottom(下)  |
| attachedFace | af | 若采用的方块（如按钮）可连接其它方块, 方块应依附于哪里 | Wall |
| stairshape | shape | 若采用的方块为楼梯, 楼梯的朝向（支持[占位符](/技能/占位符)） | STRAIGH |

可用朝向
-------

| 朝向名 | 描述 |
| - | - |
| DOWN | 下 |
| EAST| 正东 |
| EAST_NORTH_EAST | 东北偏东 |
| EAST_SOUTH_EAST| 东南偏东 |
| NORTH| 正北 |
| NORTH_EAST | 东北 |
| NORTH_NORTH_EAST | 东北偏北 |
| NORTH_NORTH_WEST | 西北偏北 |
| NORTH_WEST | 西北 |
| SELF | ？？？ |
| SOUTH | 正南 |
| SOUTH_EAST | 东南 |
| SOUTH_SOUTH_EAST | 东南偏南 |
| SOUTH_SOUTH_WEST | 西南偏南 |
| SOUTH_WEST | 西南 |
| UP | 上 |
| WEST | 正西 |
| WEST_NORTH_WEST| 西北偏西|
| WEST_SOUTH_WEST | 西北偏南|

依附面可用值
-----

| 值名 | 描述 |
| - | - |
| CEILING | 顶部 |
| FLOOR | 底部 |
| WALL | 墙壁 |

楼梯朝向可用值
-----

| 值名 | 描述 |
| - | - |
| INNER_LEFT | 朝内且偏左 |
| INNER_RIGHT | 朝内且偏右 |
| OUTER_LEFT | 朝外且偏左 |
| OUTER_RIGHT | 朝外且偏右 |
| STRAIGH | 普通楼梯 |

台阶种类可用值
-----

| 值名 | 描述 |
| - | - |
| BOTTOM | 下台阶 |
| DOUBLE | 双层台阶 |
| TOP | 上台阶 |

bisectedhalf可用值
-----

| 值名 | 描述 |
| - | - |
| BOTTOM | 下 |
| TOP | 上 |

示例
--------

```yaml
方块修改示例:
 Skills:
 - setblocktype{m=STONE;md=0} @selflocation
``````yaml
MMOItems方块修改示例:
 Skills:
 - setblocktype{m=mmoitems:50;md=0} @selflocation
``````yaml
5.0.3版本支持省略materialdata示例:
 Skills:
 - setblocktype{m=chest[waterlogged=true]}
```