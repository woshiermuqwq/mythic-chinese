**描述:** 若实体为指定MythicMobs实体.

---

**修改项:**

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| type      | types, t | 用于检测的多个MythicMobs实体名, 可被设为"ANY"以检测目标是不是一个MythicMobs实体 |

---

**示例:**

```
Conditions:
- mythicmobtype{t=CoolZombie,IceZombie,SnowZombie} true
```

```
TargetConditions:
- mythicmobtype{t=HotZombie,LavaZombie,FireZombie} true
```

---

**拓展信息:**

- [x] 检测对象: 实体