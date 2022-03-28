**描述:** 若类型为数值的变量的数值在指定范围内.

---

**修改项:**

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| variable | name, n, var, key, k | 用于检测的变量名（未设置时该条件报错） |
| value | val, v | 用于检测的变量值, 支持具体值/范围值, 同时支持[占位符](/技能/占位符) |

---

**示例:**

```
  Conditions:
  - varrange{var=caster.冷却;v=<0.01} cancel
  Skills:
  - setvar{var=caster.冷却;t=float;v="10"}
  - m{m=&7冷却结束}
```

```
  Conditions:
  - varrange{var=caster.测试;v=0}
  Skills:
  - m{m=&7值为0}
```
```
暴击机制:
 Skills:
 - setvar{var=caster.随机数;v=<random.0to100>}
 - skill:暴击检测
暴击检测;
 Conditions:
 - varrange{var=caster.暴击率;v=<<caster.var.随机数>}
 Skills:
 - m{m=暴击了!}
###假设玩家暴击率为70, 那么当随机变量随机到的值<70时暴击, 只有30%的可能性大于70, 也就是不暴击
```

---

**拓展信息:**

- [x] 检测对象: 技能
- [x] 别称: varinrange, varrange