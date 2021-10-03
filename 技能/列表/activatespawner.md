技能: Activate Spawner
--------------------------

激活指定生成点(组).

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| spawners | spawner,s | 要激活的生成点(组)（支持[占位符](/技能/占位符)与[变量](/技能/变量)） | 无 |

示例
--------

激活生成点"BossAdd"

    Skills:
    - activatespawner{spawner=BossAdd}

激活位于"Castle"组内的所有生成点

    Skills:
    - activatespawner{spawner=g:Castle}

激活所有以"DungeonBoss1Spawner"为前缀的生成点

    Skills:
    - activatespawner{spawner=DungeonBoss1Spawner*}
    - ...