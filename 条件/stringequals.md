**描述:** 若实体的一个变量等于另一个变量.

修改项
---

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| value1 | val1, v1 | 变量1 |
| value2 | val2, v2 | 变量2 |

示例
---

```yaml
 Conditions:
 - stringequals{val1="<caster.var.这是一个变量>";val2="<caster.var.这是另一个变量>"} true
```
```yaml
 Conditions:
 - stringequals{val1="%denizen_<player[<trigger.uuid>].item_in_hand.has_nbt[special_item]>%";val2="true"} true
```
使用Denizen, PlaceholderAPI, MythicMobs 检测玩家是否拥有指定NBT “special_item.”.
```yaml
 Conditions:
 - stringequals{val1="%denizen_<player[<trigger.uuid>].item_in_hand.raw_nbt.get[mythic_type].after[string:]>%";val2="SomeMythicItem"} true
```

拓展信息
---

- 检测对象: 技能
- 缩写: stringeq