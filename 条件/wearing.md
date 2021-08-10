**描述:** .

---

**修改项:**

| 修改项名  | 别称      | 描述 |
| --------- | --------- | ----------- |
| armorslot | slot, s   | 用于检测的槽位. |
| material  | mmitem, m | 用于检测的物品名(可为MythicMobs物品与MMOItems物品) |
| checklore | cl        | 用于检测的Lore |

**可用槽位:**

| HEAD | CHEST | LEGS | FEET | HAND | OFFHAND |   
| 头   | 胸甲  | 护腿 | 靴子 | 主手 | 副手    |   
| ---- | ----- | ---- | ---- | ---- | ------- |   

---

**示例:**

```
Conditions:
- wearing{slot=HAND;m=IRON_SWORD} true
```

---

**拓展信息:**

- [x] 检测对象: 实体
- [x] 别称: iswearing wielding iswielding