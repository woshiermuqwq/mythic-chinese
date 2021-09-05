技能: Raytrace
---------------------

向目标位置发射射线. [付费版技能][施法者为非玩家实体时需sync=true]
 
Attributes
----------

| 修改项       | 别称 | 描述                                                                                        | 默认值 |
|---------------------|------------------------|-------------------------------------------------------|------|
| entityskill         | eskill, es             | 击中实体后所激活的技能组  |      |
| locationskill       | lskill, ls             | 击中固体方块后所激活的技能组  |      |
| maxdistance         | distance, md, d        | 射线最大移动距离 | 50   |
| raywidth | rw, w     | 射线宽度 | 0.2                                                   |      |
| ignorepassableblocks| ignorepassable, ip     | 是否无视可通过的方块  | true |
| fluidcollisionmode  | fcm                    | 是否无视流体方块  | NEVER|
| accuracy            | ac, a                  | 射线碰撞箱的扩散范围? |1     |
| verticalnoise       | vn                     | 射线碰撞箱的垂直扩散(格方块) | 0    |
| horizontalnoise     | hn                     | 射线碰撞箱的水平扩散(格方块) | 0    |
| raytraceConditions  | rc, rcon, rconditions  | 射线命中实体/方块后,所命中事物所需符合的条件 | NONE |

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