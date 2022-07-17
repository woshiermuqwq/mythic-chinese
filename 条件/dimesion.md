**描述:** 若所处世界的维度为.

---

修改项
---

| 修改项名  | 别称           | 描述                      | 默认值 |
| --------- | -------------- | ------------------------- | - |
| dimension | d, environment, e | 所检测的维度 | PLAINS |

可用维度
---

| 维度名 | 描述 |
| - | - |
| NORMAL | 主世界 |
| NETHER | 下界|
| THE_END | 末地 |
| CUSTOM | 来自其它插件 |

新增于 MM 4.13

---

示例
---

```yaml
 Conditions:
 - dimension{d=normal}
```

拓展信息
---

- 检测对象: 位置
- 别称: Environment