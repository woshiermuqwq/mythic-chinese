**描述:** .

---

**修改项:**

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| type      | types, t | 用于检测的多个实体种类 |

---

**示例:**

```
Conditions:
- entitytype{t=ZOMBIE} true
```

```
TargetConditions:
- entitytype{t=WITCH} true
```

```
TriggerConditions:
- entitytype{t=PLAYER} true
```

---

**拓展信息:**

- [x] 检测对象: 实体
- [x] 别称: mobtype