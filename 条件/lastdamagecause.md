**描述:** 若最后一次受伤的伤害类型为.

建议使用 [Damage Cause](/条件/damagecause).

修改项
---

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| damagecause | cause, c | 无 |

一列可用的伤害类型列表: 

https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityDamageEvent.DamageCause.html

---

**示例:**

```yaml
 Conditions:
 - lastdamagecause{c=ENTITY_ATTACK} true
```

拓展信息
---

- [x] 检测对象: 实体