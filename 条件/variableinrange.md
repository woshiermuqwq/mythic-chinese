**描述:** 若类型为数值的变量的数值在指定范围内.

---

**修改项:**

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| var | 无 | 用于检测的变量名 |
| value | val, v | 用于检测的变量值 |

---

**示例:**

```
  Conditions:
  - variableInRange{var=caster.冷却;value=<0.01} cancel
  Skills:
  - setvariable{var=caster.冷却;type=float;value="10"}
  - message{m="&7冷却结束"}
```

---

**拓展信息:**

- [x] 检测对象: 技能