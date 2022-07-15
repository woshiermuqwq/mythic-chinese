特效技能: Item Spary
--------------------------

于技能目标位置生成物品掉落物抛洒.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| items        | item, i         | 所抛洒的物品名(支持MythicMobs物品)| iron_sword    |
| amount      | a         | 所抛洒的物品掉落物数量          | 10            |
| duration    | d         | 抛洒出的物品掉落物的持续时间  | 20            |
| radius      | r         | 抛洒最大距离(格方块)       | 0             |
| velocity    | v, force, f | 抛洒速度    | 1             |
| yVelocity   | yv, yforce, yf       | 抛洒Y轴速度  | velocity      |
| yOffset     | yo, y | 抛洒起点的垂直偏移量(格方块) | 1             |
| allowpickup | ap        | 跑撒出的物品掉落物是否可被拾起 | false         |
| gravity | g | 所抛洒的掉落物实体是否拥有重力 | true |

注意
--------

物品可被漏斗吸取.

从 MM 4.14.0 起, 所选取的物品支持[掉落表](/物品/掉落), 将随机选取掉落表内的物品抛洒

示例
--------

```yaml
 Skills:
 - effect:itemspray{item=iron_sword;amount=20;velocity=5;d=100} @self
```

额外信息
---

- 别称: e:itemspray, itemspray
- **支持** [占位符](/技能/占位符)（除修改项: allowpickup）