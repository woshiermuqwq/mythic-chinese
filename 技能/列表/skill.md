技能: Skill
--------------------------

向目标激活指定技能组(位于Skills文件夹的文档内).

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| skill | s | 用于激活的指定技能组名 | 无 |
| forcesync | sync      | 是否强制激活 | false   |

示例
--------

      Skills:
      - skill{skill=技能组} @Target ~onAttack
      - skill{s=技能组} @Trigger ~onSpawn
      - skill:技能组 @Trigger ~onDeath
      - skill
          {
          skill=一个技能组;
          sync=true
          } @self ~onDamaged
