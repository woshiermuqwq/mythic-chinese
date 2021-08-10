**描述:** 若末影龙动作阶段为(可多个).

---

**修改项:**

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| phases | phase | 用于检测的多个末影龙阶段名 |

---

**示例:**

```
Conditions:
- enderdragonphase{phase=CIRCLING} true
```

Conditions:
- enderdragonphase{phases=FLY_TO_PORTAL,LEAVE_PORTAL}

···

可用的末影龙阶段名列表 https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/entity/EnderDragon.Phase.html

---

**拓展信息:**

- [x] 检测对象: 实体