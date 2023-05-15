**描述:** 若服务器版本为给定版本.

---

**修改项:**

| 修改项名  | 别称           | 描述                      | 默认值
| --------- | -------------  | ------------------------- | - |
| sv | s | 所指定的版本号 | 1.19.3 |

---

**示例:**

```yaml
 Conditions:
 - packversiogreater{p="1";v="1.19.4"}
 Skills:
 - teleport @casterspawn
```
当服务器版本为1.19.4时, 传送回施法者的出生点

---

拓展信息
---

- 检测对象: 服务器
- 别称: mythicpackversion, packversionis