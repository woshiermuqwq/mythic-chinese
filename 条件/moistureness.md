**描述:** 若耕地的湿润等级为.

---

**修改项:**

| 修改项名  | 别称           | 描述                      | 默认值
| --------- | -------------  | ------------------------- |---|
| level | l, moistness, m | 7 |

---

**示例:**

```yaml
 Conditions:
 - moistureness{m=7}
 Skills:
 - teleport @casterspawn
```
当自身处在完全湿润的耕地上方时, 传送回施法者的出生点

---

拓展信息
---

- 检测对象: 实体
- 别称: moistureness