技能: Give Experience Levels （5.4.0）
--------------------------

提升技能目标(玩家)的原版等级  

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| amount | a | 所给予的原版等级（支持[占位符](技能/占位符)与[计算](技能/计算)） | 0.0 |

示例
--------

```yaml
 Skills:
 - giveexperiencelevels{amount=20} @pir{r=20} ~onSpawn 0.2
```
生成后有20%几率提升半径20米范围内的所有玩家20原版等级.

额外信息
---

- [x] 别称: GiveExplevels