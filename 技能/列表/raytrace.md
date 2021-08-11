技能: 
--------------------------

向目标发射射线.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|---------------------|------------------------|-------------------------------------------------------|------|
| entityskill         | eskill, es             | 命中实体后所释放的技能                   | 无   |
| locationskill       | lskill, ls             | 命中方块后所释放的技能                   | 无   |
| maxdistance         | distance, md, d        | 射线最大距离                                 | 50   |
| raywidth | rw, w     | 射线追踪的宽度(?) | 0.2                                                   |      |
| ignorepassableblocks| ignorepassable, ip     | 是否无视方块              | true |
| fluidcollisionmode  | fcm                    | 是否无视流体  | NEVER|
| accuracy            | ac, a                  | 精准度                              |1     |
| verticalnoise       | vn                     | 碰撞箱垂直扩散                            | 0    |
| horizontalnoise     | hn                     | 碰撞箱水平扩散                          | 0    |
| raytraceConditions  | rc, rcon, rconditions  | 命中条件 | 无 |

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