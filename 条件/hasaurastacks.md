**描述:** 若实体拥有指定光环的层数在指定数值范围内.

修改项
---

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| auraname | name, n | 用于检测的光环名 |
| stacks | s | 用于检测的层数数值范围

示例
---

```yaml
 Conditions:
 - hasaurastacks{n=某光环;s=>3} true
```

拓展信息
---

- 检测对象: 实体
- 别称: hasbuffstacks, hasdebuffstacks, aurastacks, buffstacks, debuffstacks