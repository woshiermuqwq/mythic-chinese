技能: Take Item (4.14)
--------------------------

移除技能目标（玩家）的指定物品（目标背包无空位时无效）  
低版本替代方法见下.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| items        | item, i, material, mi, m, mythicitem       | 所移除的物品ID（支持Mythic物品） | 1 |
| amount | a | 所移除的物品数量（支持[占位符](/技能/占位符)） | Dirt |

--------

示例（实体配置）
--------

```yaml
 Skills:
 - take{i=diamond_sword} @PIR{r=20} ~onSpawn
 - ...
```
生成后移除半径20格方块内的所有玩家一把钻石剑.

低版本替代方法
---

```yaml
 Skills:
 - cmd{c="minecraft:clear @p minecraft:diamond 0 1 {display:{Lore:["&6测试"]}}";astarget=true;asop=true}
```
清除技能目标 **背包内** 的一颗 描述中含有金色字体的"测试" 的钻石  
该方法需关闭命令反馈`/gamerule sendcommandfeedback false`  
关闭命令反馈相当于通过原版切换模式/更改游戏规则不会反馈信息, 对玩家无影响

或只想消耗主手物品, 可使用[Remove Held Item](/技能/列表/removehelditem)

额外信息
-------

- 别称: take, takeitems, itemtake