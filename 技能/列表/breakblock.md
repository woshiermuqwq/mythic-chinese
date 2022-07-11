技能: Break Block
--------------------------

破坏指定位置的方块.  
无效技能.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| doDrops   | drops, d | 是否掉落所破坏的方块 | true          |
| doEffect  | effect, e | 是否播放方块破坏粒子 | true |
| useTool   | tool, t | 是否使用手持物品破坏 | true |

所有修改项新增于 MM4.12

----------

1. 
```yaml
破坏方块测试:
  Skills:
  - breakblock{forcesync=true;doEffect=true;doDrops=true;useTool=true} @targetlocation
```

当玩家未手持可破坏指定方块的物品时,破坏后播放粒子效果,但不会掉落方块(反之则会).

2. 
```yaml
破坏方块测试:
  Skills:
  - breakblock{forcesync=true;doEffect=true;doDrops=true;useTool=false} @targetlocation
```

无论玩家是否手持可破坏指定方块的物品,破坏后都会掉落方块,但不会播放粒子效果.

--------

示例
--------

被右键后破坏位于 `X: 100, Y: 64, Z: 100` 的方块.
```yaml
 Skills:
 - breakblock{forcesync=true} @location{c=100,64,100} ~onInteract
 - ...
```