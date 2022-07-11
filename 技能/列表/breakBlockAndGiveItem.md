技能: Break Block And Give Item
--------------------------

破坏目标选择器所指定位置的方块并掉落该方块

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| doDrops   | drops, d | 是否掉落所破坏的方块 | true          |
| doEffect  | effect, e | 是否播放方块破坏粒子 | true |
| useTool   | tool, t | 是否使用手持物品破坏 | true |
| fakelooting | fl | 是否播放给予物品效果 | true |
| items | item, i | 所给予的额外物品 | 无 |

示例 (物品技能)
--------

破坏方块后若方块种类为泥土或草方块则给予玩家钻石.
```yaml
#物品配置
特殊的物品:
  Id: GOLDEN_SHOVEL
  Display: '幸运锹'
  Skills:
  - skill{s=点土成钻;sync=true} @TargetLocation ~onBreakBlock

#技能组配置
点土成钻:
  TargetConditions:
  - blocktype{t=DIRT,GRASS_BLOCK} true
  Skills:
  - breakBlockAndGiveItem{dodrops=false;items=diamond}
```