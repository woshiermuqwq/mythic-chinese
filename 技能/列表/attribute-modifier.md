技能: Attribute Modifier
--------------------------

为技能目标应用原版属性附加值.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| attribute | attr | 所应用的原版属性名 | GENERIC_LUCK(幸运) |
| operation | op | 所应用的方式 | ADD_NUMBER(加法) |
| name | modifiername | 附加值名称 | 施法者的UUID |
| amount | amt, a | 所应用的数值（支持[占位符](/技能/占位符)与[计算](/技能/计算)） | 0.0 |
| duration | dur | 属性附加值持续时间（单位: 刻） | 0.0 |

示例（实体配置）
--------

```yaml
 Skills:
 - attributeModifier{attribute=GENERIC_LUCK;operation=ADD_NUMBER;name=;amount=1;duration=11111110} @self ~onSpawn
```
生成后为自己添上1点幸运
