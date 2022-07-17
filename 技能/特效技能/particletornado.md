特效技能: Particle Tornado
--------------------------

于技能目标位置生成粒子龙卷风.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| maxradius        | mr    | 粒子龙卷风最大半径 | 5             |
| yoffset          | yo    | 粒子龙卷风起始点垂直偏移值(格方块)  | 0.8           |
| height           | h     | 粒子龙卷风最大垂直半径(格方块) | 4 |
| interval         | i     | 粒子龙卷风刷新间隔(刻. | 4 |
| duration         | d     | 粒子龙卷风持续时间 | 200           |
| rotationspeed    | rs    | 粒子龙卷风转向速度 | 0.04 |
| sliceheight      | sh    | 粒子龙卷风数值低于1会显示不完整的龙卷风, 高于10会使龙卷风出现不同的形状和显示规律,原理未知 | 1 |
| particlespeedramp | psr | 粒子龙卷风的斜率 | 0.0 |
| cloudparticle    | cp    | 所使用的粒子 | largeexplode |
| cloudsize        | cs    | 粒子龙卷风单个粒子的半径(格方块) | 5     |
| cloudamount      | ca    | 粒子龙卷风单个粒子点的粒子数量 | 1 |
| cloudhspread     | chs   | 粒子龙卷风单个粒子点的垂直扩散半径 | 1             |
| cloudvspread     | cvs   | 粒子龙卷风单个粒子点的水平扩散半径               | 1.8           |
| cloudpspeed      | cps   | 粒子龙卷风单个粒子点的粒子速度 | 2             |
| cloudyoffset     | cyo   | 粒子龙卷风单个粒子点的起始点垂直偏移值(格方块) | 2               |


示例（实体配置）
--------

```yaml
 - effect:particletornado{p=flame;cp=largeexplode;mr=1;h=3;i=4;d=100;rs=1;sh=1;cs=0;ca=0;chs=0.1;cvs=0.1;cps=1;cyo=2} @self ~onTimer:100
```

额外信息
---

- 别称: particletornado, e:pt
- 