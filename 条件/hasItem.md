**描述:** 若实体拥有指定数量的指定物品.

修改项
---

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| item      | i    | 用于检测的物品类型, 支持Mythic物品<br>使用 `mmoitems.TYPE.ID` 以检测MMOItems物品 |
| amount    | 无 | 用于检测的物品数量 |

新增于MM 4.13

示例
---

```yaml
 Conditions:
 - hasitem{i=STICK;amount=2} true
```

拓展信息
---

- 检测对象: 实体