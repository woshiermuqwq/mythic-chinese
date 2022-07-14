技能: Track Location
--------------------------

记录技能目标的当前位置  
仅能记录一个位置

新增于MM 4.13

示例（实体配偶之）
--------

```yaml
 Skills:
 - tracklocation @trigger ~onInteract
 - teleport @trackedlocation ~onDamaged
```
施法者被右键后记录右键者的位置, 施法者受伤后传送到所保存位置.