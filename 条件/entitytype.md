**描述:** 若实体种类为.

修改项
---

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| type      | types, t | 用于检测的多个实体种类 |

示例
---

```yaml
 Conditions:
 - entitytype{t=ZOMBIE} true
```
```yaml
 TargetConditions:
 - entitytype{t=WITCH} true
```
```yaml
 TriggerConditions:
 - entitytype{t=PLAYER} true
```

拓展信息
---

- 检测对象: 实体
- 别称: mobtype