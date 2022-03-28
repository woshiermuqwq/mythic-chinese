技能: Command
--------------------------

在控制台执行命令.

支持[占位符](/技能/占位符)（包括 [颜色代码](/杂项/颜色代码) ）.

命令必须被""所包裹,有关命令技能的教学请见[命令技能教学](/教学/命令技能).

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| command       | cmd, c | 所执行的命令                                                   |         | 无 |
| asCaster      | caster, ac, sudomob, sudo      | 是否由施法者执行命令而不是控制台 | false   |
| asOp          | op      | 施法者是否无视权限需求执行                      | false   |
| asTarget      | target, at, sudotarget      | 是否由技能目标执行命令                                 | false   |
| requireTarget | rt      | 是否要求此技能拥有技能目标                                  | false   |

当 `asTarget` 为true 时, requireTarget 也会自动变为 `true`

示例
--------

死亡后将半径16格方块, 球体范围内的所有玩家传送回主城 (/spawn 命令可用):
```yaml
测试实体:
 Type: husk
 Skills:
 - cmd{c="spawn";astarget=true;asop=true} @pir{r=16} ~ondeath
```

出生后将服务器内所有玩家传送到 "测试" 传送点 (/wrap 命令可用):
```yaml
测试实体:
 Type: husk
 Skills:
 - command{c="wrap 测试";astarget=true;asop=true} @server ~onspawn
```

受伤后给予攻击者sx物品: "测试" 传送点 (SX 已安装):
```yaml
测试实体:
 Type: husk
 Skills:
 - command{c="sx get 测试";astarget=true;asop=true} @trigger ~ondamaged
```

额外信息
-------

- **支持** [占位符](/技能/占位符)（修改项: Command）
- 缩写: cmd