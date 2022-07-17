特效技能: Block Wave
--------------------------

视觉上地放出方块扩散波,该场地内の玩家无法正常移动.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| ignoreair | ia | 是否无视空气扩散 | true |
| radius    | r      | 扩散波的半径(格)范围 | 0(无限制)  |
| duration  | d      | 扩散波最大扩散时间（单位: 刻） | 15 |
| shape     | s      | 范围形状,sphere(球)或cube(方体) | sphere        |
| velocity | v | 扩散波水平扩散速度 | 0.2 |
| velocityh | vh     | 扩散波垂直扩散速度 | 0 |
| velocityx | vx     | 扩散波X轴速度 | 0       |
| velocityy | vy     | 扩散波Y轴速度 | 0       |
| velocityz | vz     | 扩散波Z轴速度 | 0       |
| noise     | n      | 扩散波的随机性,值越大越完整 | 0       |
| hidesourceblock | hidesourceblock, hsb, hs | 若技能目标位置是一个方块 是否隐藏这个方块 | true  |  

示例
--------

```yaml
 Skills:
 - particlewave{duration=100;particle=frame;radius=5;radiusY=5;velocity=10;shape=sphere} @selflocation
```

额外信息
-----

- 别称: effect:particlewave, e:particlewave
- **支持** [占位符](/技能/占位符)（除修改项: hildesourceblock、ignoreair）