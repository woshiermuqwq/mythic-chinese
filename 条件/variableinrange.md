**描述:** 若值为非字符串的变量的数值在指定范围内或为具体值.

---

**修改项:**

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| variable | name, n, var, key, k | 用于检测的变量名（未设置时将认定该变量值为1而非"UNDEFINED"） |
| value | val, v | 用于检测的变量值, 支持具体值(如`v=1`)/范围值(如`v=0to1`)<br>为范围值时, `v=>1` 表变量值需大于1而非大于等于1<br>从4.13起支持[占位符](/技能/占位符) |

提示信息
----

**无法**读取技能目标身上的变量, 比如使用[变量传递](/技能/变量)  

错误示范:  
```yaml
测试技能组:
 Skills:
 - skill:测试 @target
 - skill:测试1 @target
测试:
 TargetConditions:
 - varrange{var=caster.测试变量;v=<target.var.测试变量>}
 Skills:
 - m{m=成功}
测试1:
 TargetConditions:
 - varrange{var=target.测试变量;v=<caster.var.测试变量>}
 Skills:
 - m{m=成功}
```

正确示范:  
```yaml
测试技能组:
 Skills:
 - setvar{var=caster.检测;v=<target.var.测试变量>} @target
 - message{m=成功} @target ?varrange{var=caster.检测;v=<caster.var.测试变量>}
 - message{m=成功} @target ?varrange{var=caster.测试变量;v=<caster.var.检测>}
```

---

**示例:**

```yaml
  Conditions:
  - varrange{var=caster.冷却;v=<0.01} cancel
  Skills:
  - setvar{var=caster.冷却;t=float;v="10"}
  - m{m=&7冷却结束}
```

```yaml
  Conditions:
  - varrange{var=caster.测试;v=0}
  Skills:
  - m{m=&7值为0}
```
```yaml
暴击机制:
 Skills:
 - setvar{var=caster.随机数;v=<random.0to100>}
 - skill:暴击检测
暴击检测:
 Conditions:
 - varrange{var=caster.暴击率;v=<<caster.var.随机数>}
 Skills:
 - m{m=暴击了!}
###假设玩家暴击率为70, 那么当随机变量随机到的值<70时暴击, 只有30%的可能性大于70, 也就是不暴击
```

拓展信息
---

- 检测对象: 实体
- 别称: varinrange, varrange