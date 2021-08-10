**描述:** 若实体的等级(非原版)在指定数值范围内.

---

**修改项:**

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| level     | l     | 用于检测的原版等级范围 |

---

**Examples:**

```
Conditions:
- level{l=10} true
```

```
Conditions:
- level{l=>10} true
```

```
Conditions:
- level{l=1to10} true
```

```
Conditions:
- level{l=<10} true
```

---

**拓展信息:**

- [x] 检测对象: 实体