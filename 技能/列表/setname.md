技能: Set Name
--------------------------

设置技能目标（非玩家）的显示名.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| setname | 无 | 修改后的显示名 | 无 |

示例 (实体配置)
--------

```yaml
 Skills:
 - setname{name=<target.name>} @self ~onDamaged
```
受伤后将自身的显示名修改为 仇恨目标 的名称.

注意
----

当施法者已伪装, 且设 setDynamic 为 true时  
使用 ~onTimer 激活该技能将导致如下报错:

```yaml
[SCHEDULER] Exception thrown whilst executing task  
java.lang.IllegalStateException: Cannot modify disguises on an async thread
```

额外信息
-------

**支持** [占位符](/技能/占位符)（≥4.9）