技能: Run AI Goal Selector
--------------------------

为目标新增一个 最低优先度的AI行动器.

可用AI行动器的详细内容见->[点击这儿](/实体/AI)

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| goal | 无 | AI行动器名 | 无 |

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
-   gotolocation / goto (parse the specialchars!) Look here:
    [Variables](/skills/stringvariables)
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
-   patrol / patrolroute (parse the special chars!) Look here:
    [Variables](/skills/stringvariables)
-   randomlookaround / lookaround
-   randomstroll
-   restrictopendoor
-   closedoors
-   restrictsun

示例
-------

    修改AI行动器示例:
      Skills:
      - runaigoalselector{goal=clear}
      - runaigoalselector{goal=fleesun}
      - runaigoalselector{goal=randomstroll}

