特效技能: Particles
--------------------------

播放粒子效果.

修改项: audience=world(世界)或target(目标)或caster(施法者) 新增于 MM4.11.  
此修改项允许粒子效果仅对audience所写实体起作用.

粒子种类; Mob 以及它的修改项: mob=实体名 新增于 NN4.12.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| particle  | p  | 粒子种类  | reddust |
| material | m | 与方块有关的粒子所选取的原方块 |
| amount | a | 粒子数量 | 10    |
| hSpread | hs  | 粒子最大水平分散半径(格方块)范围 | 0     |
| vSpread | vs  | 粒子最大垂直分散半径(格方块)范围 | 0     |
| speed | s   | 粒子速度 | 0 |
| yOffset | y   | 粒子起始点垂直偏移量(格方块) | 0 |
| viewDistance | vd  | 粒子可被多少格方块以外的玩家所见 | 128   |
| Size | 无 | 粒子大小 | 1 |
| color | c | [ 粒子颜色(#000000之类的) | 我I |
| fromorigin | 无 | 是否起始于坐标原点 | false |
| directional | d | 粒子动量是否可被修改 | false | 
| directionReversed | | 是否反转粒子动量 | false | 
| direction | dir | 动量参数 | 与施法者朝向一致 | 
| useEyeLocation | uel | 是否以施法者眼睛部位为起始点 | false |
| forwardOffset   |  | 粒子起始点前后偏移量(格方块) | 0 |
| sideOffset | so | 粒子起始点左右偏移量(格方块) | 0 |

示例
--------

----
    Skills:
    - effect:particles{particle=flame;amount=200;hS=1;vS=1;speed=5} @self
    - ...
1.12 block_crack

    Skills:
    - effect:particles{particle=block_crack_dirt_0;amount=100;hS=1;vS=1} @self

1.13 block

    Skills:
    - effect:particles{particle=block;m=dirt;amount=100;hS=1;vS=1} @self