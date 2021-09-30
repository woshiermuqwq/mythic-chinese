**描述:** 若方块位置的光照等级在指定范围内.

---

**修改项:**

| 修改项名  | 别称           | 描述                      | 默认值 |
| --------- | -------------- | ------------------------- | ----- |
| level | l | 用于检测的光照等级数值范围 | 0 |

---

**示例:**

```
Conditions:
- lightlevelfromblocks{l=10} true
```

```
Conditions:
- lightlevelfromblocks{l=>10} true
```

```
Conditions:
- lightlevelfromblocks{l=1to10} true
```

---

**拓展信息:**

- [x] 检测对象: 位置
- [x] 别称: blocklightlevel