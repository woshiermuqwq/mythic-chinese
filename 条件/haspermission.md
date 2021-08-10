**描述:** 若实体拥有指定权限.

---

**修改项:**

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| permission | p     | 用于检测的权限名. |

---

**示例:**

```
Conditions:
- haspermission{p=permission.node.here} true

TargetConditions:
- haspermission{p=permission.node.here} true

TriggerConditions:
- haspermission{p=permission.node.here} true
```

---

**拓展信息:**

- [x] 检测对象: 实体(玩家)