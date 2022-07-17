**描述:** 若与实体所处世界的世界出生点距离在指定范围之内.

修改项
---

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| distance | d | 用于检测的数值范围 |

示例
---

```yaml
 Conditions:
 - distancefromspawn{d=<100} true
```
```yaml
 Conditions:
 - distancefromspawn{d=>50} true
```

拓展信息
---

- 检测对象: 位置