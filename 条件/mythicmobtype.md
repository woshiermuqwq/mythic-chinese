**描述:** 若实体为指定MythicMobs实体.

修改项
---

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| type      | types, t | 用于检测的多个MythicMobs实体名 |

**示例:**

```yaml
 Conditions:
 - mythicmobtype{t=测试A,测试B,测试C} true
```

拓展信息
---

- 检测对象: 实体
- 别称: mmtype