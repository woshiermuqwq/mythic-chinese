技能: Bar Create
--------------------------

为技能目标创建Boss血条.  
目标可拥有多条Boss血条（血条内部ID可一致）.  
施法者消失（非死亡）后, Boss血条不会消失.  
施法者死亡后, 内部ID一致的Boss血条, 只有最近一次创建的会消失  
解决方案: 重启服务器

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| name      | n       | 血条内部ID（支持[占位符](/技能/占位符)）.                                                                                            | infobar                     |
| display   | d       | 血条标题文本（支持[占位符](/技能/占位符))）.                                                                                      | &lt;skill.var.aura-name&gt; |
| value     | v       | 血条百分比,数值在0~1.0之间.                                                             | 1.0                         |
| color     | c       | 血条颜色,可用: PINK, BLUE, RED, GREEN, YELLOW, PURPLE, WHITE（支持[占位符](/技能/占位符)）.                     | RED                         |
| style     | s       | 血条样式,可用: SOLID, SEGMENTED_6, SEGMENTED_10, SEGMENTED_12, SEGMENTED_20（支持[占位符](/技能/占位符)） . | SOLID                       |

示例
--------

```yaml
 Skills:
 - barCreate{name="测试";display="<caster.name> - <caster.hp>";value=1.0;color=BLUE;style=SEGMENTED_6} @self ~onSpawn
 - ...
```
施法者生成后显示 内部名为 "测试",显示内容为 `施法者名称 - 施法者当前生命`, 百分比为1, 颜色为蓝, 款式为SEGMENTED_6的Boss血条 

拓展信息
-------

- 别称: baradd, createbar