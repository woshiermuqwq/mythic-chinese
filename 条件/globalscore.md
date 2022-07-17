**描述:** 若虚拟实体: \__GLOABL_\_在指定记分板内的分数为.

修改项
---

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| objective | obj, o | 用于检测的指定记分板 |
| value | val, v | 用于检测的分数数值范围

示例
---

```yaml
 Conditions:
 - globalscore{o=KillCount;value=>4} true
```

拓展信息
---

- 检测对象: 无
- 别称: scoreglobal