**描述:** 若脚下为指定方块(可为多种).

---

**修改项:**

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| material     | m | 用于检测的多种方块 |

---

一列可用的方块种类.

https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html

---

**示例:**

```
Conditions:
- onblock{b=WATER,LAVA} false
```

---

**拓展信息:**

- [x] 检测对象: 位置