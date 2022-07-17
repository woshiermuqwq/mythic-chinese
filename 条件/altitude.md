**描述:** 若与地面距离在指定范围内.

---

**修改项:**

| 修改项名  | 别称           | 描述                      |
| --------- | -------------  | ------------------------- |
| height    | altitude, a, h | 距离地面多高              |

---

**示例:**

```yaml
 Conditions:
 - altitude{h=<0}
 Skills:
 - teleport @casterspawn
```
当自身处在 `虚空（y<0）` 时, 传送回施法者的出生点

---

拓展信息
---

- 检测对象: 实体
- 别称: heightfromsurface