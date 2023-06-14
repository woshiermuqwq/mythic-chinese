技能: Add Trade（5.3.0）
--------------------------

为技能目标(村民)添加交易条目

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| action | mode, m | 添加方式<br>为`Remove`时删除指定行的条目<br>为`Replace`时替代指定行的交易条目 | ADD |
| slot | s, index | 将交易条目插进倒数第几行 | 0（最后一行） |
| ingredient | item， ingredient1, item1, i, i1 | 交易条目需求的第一个物品（格式: `物品ID 数量(若省略则为1)`）<br>支持[Mythic物品](/物品) | STONE |
| ingredient2 | item2, i2 | 交易条目需求的第二个物品（格式: `物品ID 数量(若省略则为1)`）<br>支持[Mythic物品](/物品)  |  |
| result | r | 交易条目结果（格式: `物品ID 数量(若省略则为1)`）<br>支持[Mythic物品](/物品)  | STONE |
| maxuses | uses, u | 每个玩家最多可完成多少次该交易条目 | 2.1E |
| experiencereward | expreward, exp, dropexp | 完成交易是否给予玩家经验 | false |
| villagerexp | villexp, vexp | 完成交易给予村民的职业经验数值 | 0 |
| pricemultiplier | multiplier | 当玩家惹了村民时, 价格提升百分比 | 0 |
| demand | d | 此交易的职业等级需求 | 1 |
| specialprice | 当玩家有恩于村民时, 价格降低百分比 | 1 |
| ignorediscounts | discounts | 价格是否不会出现波动 | false |


额外信息
---

- 别称: removetrade, replacetrade