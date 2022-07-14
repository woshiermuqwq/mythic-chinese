**描述:** 若最后一次受伤的伤害类型为.

---

**修改项:**

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| cause | c | 用于检测的伤害类型 |

---

**示例:**

```yaml
Conditions:
- damagecause{cause=ENTITY_ATTACK}
```

可用的伤害类型列表: https://mineplugin.org/DamageCause

---

**拓展信息:**

- [x] 检测对象: 实体