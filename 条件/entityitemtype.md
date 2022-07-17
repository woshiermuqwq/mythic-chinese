**描述:** 若技能目标（掉落物）的物品种类为 .

---

修改项
---

| 修改项名  | 别称           | 描述                      | 默认值 |
| --------- | -------------- | ------------------------- | --- |
| item | i, material, m, mm, mythicitem | 用于检测的物品, 支持Mythic物品 | 无 |

新增于 MM 4.14.0

示例
---

```yaml
 Conditions:
 - entityitemtype{types=diamond} true
```

拓展信息
---

- 检测对象: 实体