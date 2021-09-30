技能: Command
--------------------------

执行命令.

支持[变量](/技能/变量)与[颜色代码](/杂项/颜色代码).

命令必须被""所包裹,有关命令技能的教学请见[命令技能教学](/教学/命令技能).

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| command       | c       | 所执行的命令                                                   |         | 无 |
| asCaster      | ac      | 是否由施法者执行命令而不是控制台 | false   |
| asOp          | op      | 施法者是否无视权限需求执行                      | false   |
| asTarget      | at      | 是否由技能目标执行命令                                 | false   |
| requireTarget | rt      | 是否要求此技能拥有技能目标                                  | false   |


示例
--------

### 实体配置

    Skills:
    - command{c="give <target.name> gold_ingot 20"} @trigger ~onInteract
    - command{c="minecraft:tp <target.name> <mob.uuid>"} @self ~onDamaged
    - command{c="minecraft:summon Zombie ~ ~ ~ <&lc>NoAI:true,CustomName:<&dq>Summoned Zombie<&dq><&rc>"}
    - command{c="minecraft:summon Zombie ~ ~ ~ {NoAI:true,CustomName:<&dq>Summoned Zombie<&dq>}"}

### 错误语法

    Skills:
    - command{c="minecraft:summon Zombie ~ ~ ~ {NoAI:true,CustomName:"Summoned Zombie"}"}

教学
---------

-   [来自Krowerom的村民交易命令技能教学](https://www.youtube.com/watch?v=p71bl_W3a4I&feature=youtu.be)


额外信息
-------

- **支持** [占位符](/技能/占位符)与[变量](/技能/变量)（修改项: Command）
- 缩写: cmd