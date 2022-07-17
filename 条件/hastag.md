**描述:** 若实体拥有指定标签.

修改项
---

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| tag       | t       | 用于检测的标签名 |

示例
---

```yaml
 Conditions:
 - hastag{t=cs} true
```
```yaml
 TargetConditions:
 - hastag{t=csd} true
```

拓展信息
---

- 检测对象: 实体
- 别称: hasscoreboardTag