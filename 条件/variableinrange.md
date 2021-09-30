**描述:** 若类型为数值的变量的数值在指定范围内.

---

**修改项:**

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| variable | name, n, var, key, k | 用于检测的变量名（未设置时该条件报错） |
| value | val, v | 用于检测的变量值 |

---

**示例:**

```
  Conditions:
  - varrange{var=caster.冷却;v=<0.01} cancel
  Skills:
  - setvar{var=caster.冷却;t=float;v="10"}
  - m{m=&7冷却结束}
```

---

**拓展信息:**

- [x] 检测对象: 技能
- [x] 别称: varinrange, varrange