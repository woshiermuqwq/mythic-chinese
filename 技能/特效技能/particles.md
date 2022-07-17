特效技能: Particles
--------------------------

于技能目标位置播放粒子效果.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| particle  | p  | [粒子种类](/技能/粒子列表)（点击蓝字浏览可用粒子列表）  | reddust |
| material | m | 与方块有关的粒子所选取的原方块 | STONE |
| mob | 无 | 与实体有关的粒子（Mob）所选取的实体, 不可为原版实体 | null |
| amount | a | 粒子数量（支持 [占位符](/技能)） | 10 |
| hSpread | hs  | 粒子最大水平分散半径(格方块)范围 | 0     |
| vSpread | vs  | 粒子最大垂直分散半径(格方块)范围 | 0     |
| speed | s   | 粒子移动速度 | 0 |
| yOffset | y   | 粒子起始点垂直偏移量(格方块) | 0 |
| viewDistance | vd  | 粒子可被多少格方块以外的玩家所见（似乎无效） | 128   |
| color | c | 粒子颜色（如 #000000） | 无 |
| fromorigin | 无 | [坐标原点](/技能/目标选择器/坐标原点)是否作为粒子起点与偏移（sfo等）的中心 | false |
| directional | d | 粒子是否向向量方向移动 | false | 
| directionReversed | dr | 是否反转粒子向量 | false | 
| direction | dir | 决定粒子移动方向的向量坐标<br>（相对于坐标原点的X,Y,Z轴偏移） | 目标选择器所指定的位置 | 
| useEyeLocation | uel | 是否以施法者眼睛部位为起始点 | false |
| startForwardOffset | forwardOffset, sfo | 粒子起始点前后偏移量(格方块) | 0 |
| sideOffset | soffset, sso | 粒子起始点左右偏移量(格方块) | 0 |
| fixedyaw | yaw | 偏移方向视角水平角度 | -1111.0f |
| fixedypitch | pitch | 偏移方向视角俯仰视角度 | -1111.0f |

有关粒子颜色
-------

部分不支持颜色的粒子修改 **color** 后, 可能会发生奇特的事..  
如, endrod将会水平扩散, 且 **speed** 值越大, 其扩散程度、速度、范围也越大.  
原因未知..

有关粒子向量
--------

**并非** 仅技能支持粒子向量.  
**并非** 所有粒子都可以使用粒子向量, 不支持的粒子若强行启用向量则会不可见, 如:  
 
-   reddust
-   mob  

未启用粒子向量时, 粒子会随机扩散且短时间后消失  
启用粒子向量并定义向量坐标后, 粒子会向向量方向移动, 其速度受修改项: **speed** 影响.   
未定义向量但已将选项: `Directional` 设为true, 粒子会向目标选择器的方向移动, 支持任何目标选择器.  
若该向量为零向量, 则粒子会消失的很快, 这时通过增大选项: `amount` 的值可令其看起来更平滑  
在 MM 4.13 以下, 即使设选项: `FromOrigin` 为true, 粒子仍从施法者位置向向量方块移动

有关粒子类型: Mob（4.12）
------------------------

该粒子类型将用整个实体去替代粒子, 任何粒子技能都支持该粒子类型  
且所生成实体与正常实体一样, 可以激活技能..可以攻击、受击、死亡等   
且选项:  `Amount` 表示所生成实体数量  

不同于技能: [Summon](/技能/列表/summon) 所生成的实体  
该粒子种类所生成的实体与施法者没有任何关系  
施法者不会是被生成实体的主人、父系实体等

关于 FixedYaw/Pitch
--------

若不定义这俩修改项, sfo/sso/syo 等偏移 会基于施法者当前视角, 这意味着粒子有时会乱掉  
尤其是玩家俯仰视角度较大的时候  
解决办法就是设选项: `Pitch` 值为0

关于 修改项缩写
-----

若其它特效技能也有缩写为"p"的修改项, 如[Particle Ring](/技能/effects/particlering)的points  
Particles的修改项: particle 则会失效

示例
--------

```yaml
    Skills:
    - e:particles{p=flame;a=200;hS=1;vS=1;speed=5} @self
    - ...
```
1.12 block_crack
```yaml
    Skills:
    - e:particles{p=blockcrack_2_0;a=100;hS=1;vS=1} @self
```
1.13 block
```yaml
    Skills:
    - e:p{particle=block;m=dirt;a=100;hS=1;vS=1} @self
```

拓展信息
-------

- **支持** [占位符](/技能/占位符)（除 sfo, yaw, pitch 和值类型不为数值的修改项）
- 别称: effect:particles, e:particles, particles, particle, effect:particle, e:particle, particle, e:p