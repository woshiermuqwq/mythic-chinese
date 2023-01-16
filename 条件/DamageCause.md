**描述:** 若最后一次受伤的伤害类型为.

建议使用 [Last Damage Cause](/条件/lastdamagecause).

修改项
---

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| cause | c | 用于检测的伤害类型 |

示例
---

```yaml
 Conditions:
 - damagecause{cause=ENTITY_ATTACK}
```

拓展信息
---

- 检测对象: 实体