技能: Track Location
--------------------------

记录技能目标的当前位置  
用于搭配目标选择器: [@TrackedLocation](/技能/目标选择器#技能目标选择器必须被写在元技能技能组内)  
仅能记录一个位置  
施法者不能为玩家  

新增于MM 4.13

示例（实体配置）
--------

```yaml
 Skills:
 - tracklocation @trigger ~onInteract
 - teleport @trackedlocation ~onDamaged
```
施法者被右键后记录右键者的位置, 施法者受伤后传送到所保存位置.