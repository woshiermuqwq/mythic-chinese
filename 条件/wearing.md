**描述:** 若实体指定槽位为指定物品.

---

不工作于1.13以下

---

**修改项:**

| 修改项名  | 别称      | 描述 | 默认值 |
| --------- | --------- | ----------- | - |
| armorslot | slot, s   | 用于检测的槽位. | Head |
| material  | mat, m, mythicmobsitem, mmitem, mmi, item | 用于检测的物品名(可为MythicMobs物品 从 4.13 起可为MMOItems物品) | Dirt |

**可用槽位:**

| 头   | 胸甲  | 护腿 | 靴子 | 主手 | 副手    |   
| ---- | ----- | ---- | ---- | ---- | ------- |   
| HEAD | CHEST | LEGS | FEET | HAND | OFFHAND |   
---

**示例:**

```
Conditions:
- wearing{slot=HAND;m=IRON_SWORD} true
```

---

**漏洞:**
- 检测MythicMobs物品时,若玩家指定槽位放着 ID一致且带有附魔的原版物品,则此原版物品符合条件.
- 检测原版物品时,若玩家指定槽位放着 ID一致的MythicMobs物品,则此MythicMobs符合条件.
- 检测任意物品时,玩家指定槽位所放着的物品必须为满耐久.
---

**拓展信息:**

- [x] 检测对象: 实体
- [x] 别称: iswearing wielding iswielding