技能: On Break Block（4.13.0）
--------------------------

给予技能目标[光环](技能/列表/Aura)(光环持有者放置方块后激活技能组).  
该光环被锁定在主线程进行（即使Sync已为false）

可使用技能: [Aura](/技能/列表/aura) 的全部修改项（如onstartskill）

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| onplaceskill | onplace, ob | 光环持有者成功挖掘方块后所激活的技能（光环给予者为技能施法者） | 无 |
| cancleevent | cancel, cE | 光环持有者挖掘方块后是否取消挖掘方块事件 | false |
| drop | dropitem, allowdrop | 光环触发时（挖掘指定方块后）是否掉落方块 | true |
| blocktype | blocktypes, bt, t, material, materials, mat, m, blocks, block, b | 挖掘给定方块才能触发该光环（格式: `b=stone,dirt...`） | 无 |

新增于 MM 4.13.0

示例
--------

       Skills:
      - onbreakblock{ob=测试;cE=true;auraname=MyAura}

额外信息
--------

- [x] 别称: onblockbreak