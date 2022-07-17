**描述:** 若所处位置为指定方块(可为多种).

修改项
---

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| block     | blocks, b | 用于检测的多种方块 |

一列可用的方块种类.

https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html

---

示例
---

```yaml
 Skills:
 - skill:cs @pir{r=16}
cs:
 Skills:
 TargetConditions:
 - inblock{b=WATER,LAVA} false
 Skills:
 - damagepercent{m=1;ia=true;pi=true}
```
秒杀半径16格内, 不处在液体内的玩家

---

拓展信息
---

- 检测对象: 位置