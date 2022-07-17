**描述:** 若最后一次受伤的伤害类型为.

建议使用 [Damage Cause](/条件/damagecause).

修改项
---

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| damagecause | cause, c | 无 |

可用的伤害类型列表: [点我](/实体/伤害调整)

---

**示例:**

```yaml
 Conditions:
 - lastdamagecause{c=ENTITY_ATTACK} true
```

拓展信息
---

- 检测对象: 实体