付费版技能: Raytrace To (MC ≥ 1.16)
--------------------------

向技能目标方向发射射线  
起始点为当前位置 (相较于 [Raytrace](/技能/列表/raytrace) 更低)  
施法者不为玩家时, 需在主线程执行(`sync=true`)

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|---------------------|------------------------|-------------------------------------------------------|------|
| entityskill         | eskill, es             | 命中实体后所释放的技能                   | 无   |
| locationskill       | lskill, ls             | 命中固体方块后所释放的技能                   | 无   |
| maxdistance         | distance, md, d        | 射线最大距离  | 50   |
| raywidth | rw, w     | 射线追踪的宽度(?) | 0.2                                                   |      |
| ignorepassableblocks| ignorepassable, ip     | 是否无视非完整方块 (如: 台阶 被吃了的蛋糕)  | true |
| fluidcollisionmode  | fcm                    | 是否无视流体  | NEVER|
| accuracy            | ac, a                  | 精准度 |1     |
| verticalnoise       | vn                     | 垂直偏差程度 | 10    |
| horizontalnoise     | hn                     | 水平偏差程度 | 5    |
| raytraceConditions  | rc, rcond, rconditions  | 忽视不满足条件及其条件活动的实体 (不检测方块) | 无 |
| startyoffset | syo, ystartoffset, ys | 起始点垂直偏移 (格方块) | 0 |
| targetyoffset | tyo, ytargetoffset, ts | 技能目标位置垂直偏移 (格方块 正上负下) | 0 |
| fromorigin | fo | 是否起始于坐标原点 | false |
| useeyedirection | uel | 是否从目光位置发射, 且以眼睛为偏移中心 | false |
| forwardoffset | startfoffset, sfo | 起始点前后偏移 (格方块 正前负后) | 0 |
| sideoffset | startsoffset, sso | 起始点左右偏移 (格方块 正左负右) | 0 |

示例
--------
```
  - raytrace{
      entitySkill=[
        - damage{amount=20}
      ];
      locationSkill=[
        - particles{p=flame;a=20;s=0.2;hS=0.1;vS=0.1}
      ];
      raytraceConditions=[
        - samefaction false
      ]} @targetlocation ~onUse
```