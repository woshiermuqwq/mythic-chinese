**描述:** 若实体拥有指定权限.

OP拥有全部权限, 这包括你所写的自定义权限

修改项
---

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| permission | p     | 用于检测的权限名. |

---

示例
---

```yaml
 Conditions:
 - haspermission{p=权限.权限节点} true
```
```yaml
 TargetConditions:
 - haspermission{p=权限.权限节点} true
```
```yaml
 TriggerConditions:
 - haspermission{p=权限.权限节点.权限节点} true
```

拓展信息
---

- 检测对象: 实体(玩家)
- 别称: permission