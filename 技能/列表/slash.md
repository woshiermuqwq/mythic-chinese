技能: Slash（5.3.0）
--------------------------

于技能目标位置绘制一条弧线, 弧线的每个点都能够调用技能组

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| Points | p | 弧线所拥有的点数 | 10 |
| Duration | d | 弧线的持续时间（单位: 刻） | 0 |
| Width | w | 弧线宽度（格方块） | 1 |
| Height | h | 弧线高度（格方块） | 0 |
| Angle | arc, a | 弧线的圆心角度数 | 180.0 |
| XOffset | xo, x | 弧线中心的X轴偏移（格方块） | 0 |
| YOffset | yo, y | 弧线中心的Y轴偏移（格方块） | 0 |
| ZOffset | zo, z | 弧线中心的Z轴偏移（格方块） | 0 |
| ForwardOffset | foffset, fo | 弧线中心的前后偏移（格方块） | 0 |
| Pitch |  | 弧线的垂直旋转度数（Y轴旋转） | 0 |
| Yaw | |  弧线的水平旋转度数（Z轴旋转） | 0 |
| Roll |  | 弧线的翻滚旋转度数（Z轴旋转） | 0 |
| Radius |  | 弧线的命中判定范围半径（格方块） | 1 |
| onPointSkill | onpoint, op | 弧线的每个点所调用的技能组 |  |
| onHitEntitySkill | onhit, ohe, oh | 弧线的命中实体时所调用的技能组 |  |
| onStartSkill | onstart, os | 弧线的起始点所调用的技能组 |  |
| onEndSkill | onend, oe | 弧线的结束点所调用的技能组 |  |
| Motation | r | 立体空间旋转（格式 r=x,y,z） | 0,0,0 |
| MatchPlayerDirection | matchDirection, mpd, mcd | 弧线整体朝向是否与施法者一致 | false |
| FromOrigin |  | [坐标原点](/TranslatedByShark/Mythic-Manual-CN/-/wikis/%E6%8A%80%E8%83%BD/%E7%9B%AE%E6%A0%87%E9%80%89%E6%8B%A9%E5%99%A8/origin)是否为弧线中心 | false |
| HitConditions | conditions, cond, c, oc, hc | 实体符合给定条件才会触发OnHitEntitySkill | NONE |

示例
--------

激活生成点"测试"
```yaml
# 1
- slash{y=1.8;w=4;h=2;mpd=true;a=180;oP=[ e:p{p=CRIT} ];roll=<random.-45to45>}

# 2
测试:
  Id: NETHERITE_SWORD
  Skills:
  - slash{y=1.8;w=4;h=40;mpd=true;a=45;radius=2;
      oP=[ - e:p{p=SPARK} ];
      oH=[ - damage{a=2} ]
      ;roll=<random.-30to30>;fo=5;duration=5} @self ~onUse
# 3
- skill{s=[
  - slash{p=40;y=1.8;w=4;h=1;r=0,0,<random.-45to45>;ls=0;a=90;i=1;oP=[ - e:p{p=CRIT;a=1} ];repeat=4;repeati=2}
  - delay 10
  - slash{p=40;y=1.8;w=4;h=1;r=0,0,<random.-45to45>;ls=0;a=90;i=1;oP=[ - e:p{p=CRIT_MAGIC;a=30} ]}
  ]} @self ~onSwing

```