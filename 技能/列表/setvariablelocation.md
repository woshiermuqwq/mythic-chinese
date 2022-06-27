技能: Set Variable Location
--------------------------

为技能目标设置一个值类型为string, 值为所选取位置（坐标、世界）的变量

修改项
----------
可使用 [Set Variable](/技能/列表/setvariable) 的修改项

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| value | val, v | 所选取的位置 | @self |

新增于 MM 5.0

示例
----

```yaml
测试:
 Skills:
 - setvarloc{var=caster.1;v=@self} @self
 - m{m=<caster.var.1>} @self
```

额外信息
--

- [x] 别称: variablesetlocation, setvarloc