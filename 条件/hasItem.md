**描述:** 若实体拥有指定数量的指定物品.

修改项
---

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| item      | i    | 用于检测的物品类型, 支持Mythic物品<br>使用 `mmoitems.TYPE.ID` 以检测MMOItems物品 |
| amount    | 无 | 用于检测的物品数量 |

新增于MM 4.13, 低版本替代方法见下

示例
---

```yaml
 Conditions:
 - hasitem{i=STICK;amount=2} true
```
当背包内刚好有俩根木棍

低版本替代示例
---

```yaml
 Conditions:
 - ownsitem{list="where=ANY;material=DIAMOND;amount=1to64;lore=§6测试";action=false}
```
当背包内没有一颗 __描述中带有金色字体"测试"__ 的钻石（若要检测"有", 则将 `action=false` 改`true`）

拓展信息
---

- 检测对象: 实体