**描述:** 若手上的物品拥有指定附魔的指定等级.

---

**修改项:**

| 修改项名  | 别称           | 描述                      | 默认值 |
| --------- | -------------  | ------------------------- | - |
| type | t, enchantment, enchant, ench, e | 所检测的附魔名  | ANY |
| level | lvl, l | 所检测的附魔等级 | >0 |

示例
---

```yaml
baa:
 MaxItems: 5
 Conditions:
 - hasenchant{e=LOOT_BONUS_MOBS;lvl=>2}
 Drops:
 - diamond 1
```
当主手物品拥有抢夺3时, 额外给予1颗钻石


拓展信息
---

- 检测对象: 实体
- 别称: hasenchantment