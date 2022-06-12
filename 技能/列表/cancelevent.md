技能: CancleEvent
--------------------------

取消对应的触发器事件.

-   取消事件所处技能组必须在实体技能配置内被强制激活(sync=true).  
    示例:  - skill{s=免伤;sync=true} ~onDamaged
-   不支持延迟激活.

可影响的触发器
-----------------

-   ~onAttack
-   ~onDamaged
-   ~onExplode
-   ~onInteract
-   ~onCombat
-   ~onTeleport
-   ~onUse(需Crucible)
-   ~onShoot(需Crucible)
-   ~onConsume(需Crucible)
-   ~onPressQ(需Crucible)


示例
-------

技能组配置:

    免伤:
      Skills:
      - CancelEvent

实体配置:

    免伤实体:
      Type: villager
      Skills:
      - skill:免伤{sync=true} ~onDamaged