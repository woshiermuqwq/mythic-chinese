**描述:** 若实体的一个变量等于另一个变量.

---

**修改项:**

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| value1 | val1, v1 | 变量1 |
| value2 | val2, v2 | 变量2 |

---

**示例:**

```
  Conditions:
  - stringequals{val1="是!";val2="是!"} true
```
```
  Conditions:
  - stringequals{val1="%denizen_<player[<trigger.uuid>].item_in_hand.has_nbt[special_item]>%";val2="true"} true
```
使用Denizen, PlaceholderAPI, MythicMobs 检测玩家是否拥有指定NBT “special_item.”.
```
  Conditions:
  - stringequals{val1="%denizen_<player[<trigger.uuid>].item_in_hand.raw_nbt.get[mythic_type].after[string:]>%";val2="SomeMythicItem"} true
```

---

**拓展信息:**

- [x] 检测对象: 技能