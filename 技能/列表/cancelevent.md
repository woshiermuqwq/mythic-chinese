技能: CancleEvent
--------------------------

取消对应的触发器事件.

-   取消事件所处技能组必须在实体技能配置内被强制激活(sync=true).  
    示例一:  `- skill{s=免伤;sync=true} ~onDamaged`  
    示例二:  `- cancelevent{sync=true} ~ondamaged`
-   不支持延迟激活.

可影响的触发器
-----------------

-   ~onAttack
-   ~onBreed
-   ~onDamaged
-   ~onExplode
-   ~onInteract
-   ~onCombat
-   ~onTeleport
-   ~onUse(需Crucible)
-   ~onShoot(需Crucible)
-   ~onConsume(需Crucible)
-   ~onPressQ(需Crucible)


示例（实体）
-------

```
 Skills:
 - cancelEvent{sync=true} ~onDamaged
```
施法者受伤后取消所受到伤害, 即无敌
