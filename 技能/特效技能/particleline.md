特效技能: Particle Line
--------------------------

生成连接施法者与技能目标的粒子线段.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| distanceBetween | db       | 粒子线上各粒子点的间隔 | 0.25          |
| startYOffset    | syo, ys  | 粒子线起始点垂直偏移量(格方块) | 0             |
| targetYOffset   | tyo, yt  | 粒子线终点垂直偏移量(格方块) | 0             |
| fromOrigin      | fo       | 粒子线起始点是否位于施法者/抛射物坐标原点  | false         |
| zigzag          | zz       | 粒子线是否为"Z"形而不是直线形 | false         |
| zigzags         | zzs      | "Z"形粒子线的折点数, 为偶数时粒子线才可以视觉上命中技能目标 | 10            |
| zigzagOffset    | zzo      | "Z"形粒子线朝向的偏差弧度范围 | 0.2  |
| maxdistance（5.1） | md | 粒子线段最大长（单位: 格方块） | 256 |

Z形粒子线类似于锯齿、心电图  
0 < 实际朝向偏差弧度 ≤ (粒子线距离*偏差弧度范围)/(粒子间隔*(折点数+1))

示例
--------

```yaml
 Skills:
 - effect:particleline{particle=flame;amount=1;fromOrigin=true} @target
```

额外信息
---

- 别称: e:particleline, particleline, e:pl, pl