**描述:** 若技能目标（玩家）背包内指定槽位上的物品是否与被比较的物品相似.

修改项
---

| 修改项名  | 别称           | 描述                      | 默认值 |
| --------- | -------------- | ------------------------- | --- |
| slot | s | 用于检测的槽位, 支持数字与英文 | HAND |
| item | i, material, m, mm, mythicitem | 用于检测的物品, 支持Mythic物品） | 无 |

新增于 MM 4.14.0

可用槽位英文名
---

| 槽位名    | 槽位名别称 | 槽位数字 | 描述                                                                                                 |
|---------| - | - | ----
| Head    | Helmet | 4 |  头部 |
| Chest   | 无 | 3 | 身体 |
| Legs    | 无 | 2 | 腿部 |
| Feet    | 无 | 1 | 脚部 |
| Hand    | MainHand | 0 | 主手 |
| OffHand | 无 | 5 | 副手 |

槽位数字ID图
---

[![](https://i.ibb.co/p0C9m88/u-1608297699-3723010909-fm-253-fmt-auto-app-138-f-JPEG-webp.jpg)

示例
---

```yaml
 Conditions:
 - itemissimilar{i=测试物品;slot=25} true
```

拓展信息
---

- 检测对象: 实体
- 别称: issimilar, similarto