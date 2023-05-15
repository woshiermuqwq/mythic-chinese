技能: Polygon（5.3.0）
--------------------------

于技能目标位置绘制一条正方体, 正方体的每个点都能够调用技能组

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| Points | p | 正方体所拥有的点数 | 10 |
| DistanceBetween | distanceBetween, distance, density, db, d | 俩点之间的间隔 | 0.1 |
| Scale | size, s | 正方体的边长（格方块） | 1 |
| Skip | star, sv |  | 2 |
| Duration | d | 正方体的持续时间（单位: 刻） | 0 |
| XOffset | xo, x | 正方体中心的X轴偏移（格方块） | 0 |
| YOffset | yo, y | 正方体中心的Y轴偏移（格方块） | 0 |
| ZOffset | zo, z | 正方体中心的Z轴偏移（格方块） | 0 |
| ForwardOffset | foffset, fo | 正方体中心的前后偏移（格方块） | 0 |
| Pitch |  | 正方体的垂直旋转度数（Y轴旋转） | 0 |
| Yaw | |  正方体的水平旋转度数（Z轴旋转） | 0 |
| Roll |  | 正方体的翻滚旋转度数（Z轴旋转） | 0 |
| Radius |  | 正方体的命中判定范围半径（格方块） | 1 |
| onPointSkill | onpoint, op | 正方体的每个点所调用的技能组 |  |
| onHitEntitySkill | onhit, ohe, oh | 正方体的命中实体时所调用的技能组 |  |
| onEdgeSkill | onstart, os | 正方体边上的点所调用的技能组 |  |
| onStarSkill | onend, oe | 正方体的顶点所调用的技能组 |  |
| Motation | r | 立体空间旋转（格式 r=x,y,z） | 0,0,0 |
| MatchPlayerDirection | matchDirection, mpd, mcd | 正方体整体朝向是否与施法者一致 | false |
| FromOrigin |  | [坐标原点](/TranslatedByShark/Mythic-Manual-CN/-/wikis/%E6%8A%80%E8%83%BD/%E7%9B%AE%E6%A0%87%E9%80%89%E6%8B%A9%E5%99%A8/origin)是否为正方体中心 | false |
| HitConditions | conditions, cond, c, oc, hc | 实体符合给定条件才会触发OnHitEntitySkill | NONE |

示例
--------

激活生成点"测试"
```yaml
# 1
      - polygon{db=0.25;y=0.1;mpd=false;scale=6;
        oE=[ - e:p{p=FLAME} ];
        oP=[ - e:p{p=CRIT;a=1;repeat=20;repeati=1} ];
        oS=[ - e:p{p=SOUL_FIRE_FLAME} ]
        ;p=10;skip=6;duration=20} @Origin

# 2
    - setVar{var=global.a;v=0}
    - skill{s=[
      - addVar{var=global.a;a=1}
      - polygon{db=0.25;y=0.1;mpd=false;radius=1;scale=6;yaw=<global.var.a>;
        oE=[ - e:p{p=FLAME} ];
        oP=[ - e:p{p=CRIT;a=1} ];
        oS=[ - e:p{p=SOUL_FIRE_FLAME} ]
        ;p=10;skip=2} @Origin
      ];repeat=180;repeati=1}
```

* 修改项: `onHitEntitySkill` 仅会执行一次
* 调整修改项: \`points' 与 'skip' 以穿件多边形
* 定义修改项 `'`onPointSkill`, `onEdgeSkill`与`onStarSkill\` 以制作特效