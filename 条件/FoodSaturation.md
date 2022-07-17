**描述:** 若实体的饱和度在指定范围内.  
饱和度: 溢出的饱食度

修改项
---

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| amount | a, food, f, saturation, s | 用于检测的数值范围 |

示例
---

```yaml
 TargetConditions:
 - FoodSaturation{a=<1} true
```

拓展信息
---

- 检测对象: 实体
- 别称: hungerSaturation