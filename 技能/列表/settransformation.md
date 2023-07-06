技能: Set Transformation（5.3.3）
--------------------------

转动所选取的展示实体的指定方向

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| action   |  | 转动模式 | add |
| Transformation   | | 所选取方向 |   |

可用转动模式:  
| 模式 | 描述 |
| - | - |
| Add | 以当前方向的朝向为基准加上一个值 |SET, ADD, MULTIPLY, DIVIDE
| Set | 直接设置方向的朝向 |
| Multiply | 以当前方向的朝向为基准乘以一个值 |
| Divide | 以当前方向的朝向为基准除以一个值 |

可用方向:
| 模式 | 描述 |
| - | - |
| Translation | 转移 |
| Scale | 转移+旋转 |
| Rgiht_Location | 顺时针旋转 |
| Left_Location | 逆时针旋转 |

示例（实体配置）
--------

```yaml
测试:
 Type: husk
 Skills:
 - transformation{action=set;transformation=translation;value=0,0,1} @self
 - transformation{action=set;transformation=right_rotation;value=0,0,0,1} @self ~onTimer:10
```
