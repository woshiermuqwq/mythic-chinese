特效技能: Particle Orbital
--------------------------

于技能目标位置生成粒子环绕并跟随目标.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| radius | r  | 粒子环绕整体半径(格方块)  | 4 |
| points | p | 组成粒子环绕整体的粒子点数量 | 20 |
| ticks | t | 粒子环绕整体最大持续时间 | 100 |
| interval | in,i  | 粒子点移动速度(值越低越快) | 10     |
| rotationX | rotX,rX  | 粒子环绕整体X轴转向 | 0     |
| rotationY | rotY,rY  | 粒子环绕整体Y轴转向 | 0     |
| rotationZ | rotZ,rZ  | 粒子环绕整体Z轴转向 | 0     |
| offsetX | offx,ox   | 粒子环绕整体中心X轴偏移值(格方块) | 0 |
| offsetY | offy,oy   | 粒子环绕整体中心Y轴偏移值(格方块)  | 0 |
| offsetZ | offz,oz   | 粒子环绕整体中心Z轴偏移值(格方块) | 0 |
| angularVelocityX | avx,vx  | 粒子环绕整体X轴速度 | 0   |
| angularVelocityY | avy,vy  | 粒子环绕整体Y轴速度 | 0   |
| angularVelocityZ | avz,vz  | 粒子环绕整体Z轴速度 | 0   |
| reversed | reverse | 令粒子点反向移动 | false |

示例（实体配置）
--------

```yaml
 Skills:
 - effect:particleorbital{r=2;points=16;t=100;i=1;vy=20;particle=flame} @self ~onSpawn
```

额外信息
---

- 别称: e:particleorbital, particleorbital, effect:particlecircle, particlecircle, e:particlecircle