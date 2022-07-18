**描述:** 若指定变量的值为指定值.

修改项
---

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| variable | var | 用于检测的变量名（未设置时条件报错） |
| value | v | 用于检测的指定字符串 (不支持占位符) |
| scope | s | 变量位于哪儿 |

示例
---

```yaml
测试:
 TargetConditions:
 - variableEquals{var=target.heardbear;value="是"} cancel
 Skills:
 - message{m="&7啊啊啊啊.."}
 - setvariable{var=target.heardbear;value="是";duration=6000}
```

拓展信息
---

- 检测对象: 技能
- 缩写: variableeq, varequals, vareq