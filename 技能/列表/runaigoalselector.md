技能: Run AI Goal Selector
--------------------------

为技能目标新增一个 最低优先度的AI行动器  
使用 `clear` 时将清除已在实体配置内配置好的AI行动器  
使用其它AI行动器之前必须先进行 `clear`

可用AI行动器的详细内容见->[点击这儿](/实体/AI)  
从 4.13 起支持付费版AI行动器

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| aigoalselector | goalselector, goal, string, s | AI行动器名 | 无 |

可用AI行动器列表
------------------------

-   clear or reset (清除默认AI行动器)
-   arrowattack
-   skeletonbowattack / bowshoot / bowmaster
-   breakdoor
-   eatgrass
-   fleegolems / runfromgolems
-   fleeplayers / runfromplayers
-   fleevillagers runfromvillagers
-   fleesun
-   float / swim
-   gotolocation / goto (从 4.13 起支持[占位符](技能/占位符))
-   gotoowner
-   lookatplayers
-   leapattarget
-   meleeattack
-   spiderattack
-   moveindoors
-   movethroughvillage
-   movetowardsrestriction
-   movetowardstarget
-   opendoor
-   opendoors
-   patrol / patrolroute (从 4.13 起支持[占位符](技能/占位符))
-   randomlookaround / lookaround
-   randomstroll
-   restrictopendoor
-   closedoors
-   restrictsun

示例
-------

```yaml
修改AI行动器示例:
 Skills:
 - runaigoalselector{goal=clear}
 - runaigoalselector{goal=fleesun}
 - runaigoalselector{goal=randomstroll}
```
令施法者躲避日光和随机走动, 不会干别的事

额外信息
---

- [x] 别称: aigoal