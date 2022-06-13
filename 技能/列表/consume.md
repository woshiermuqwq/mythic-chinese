技能: Consume
--------------------------

造成伤害后恢复自身生命.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| damage           | d,dmg   | 所造成的伤害数值（为负时无效 支持[占位符](/技能/占位符)） | 1    |
| heal             | h       | 所恢复的生命数值（为负时相当于damage 支持[占位符](/技能/占位符） | 无    |
| preventknockback | pkb, pk | 是否不会造成击退   | false   |
| preventimmunity  | pi      | 是否无视受伤间隔   | false   |
| ignorearmor      | ia, i    | 是否无视实体防御 | false   |
| ignoreenchantments      | ignoreenchants, ie    | 是否无视防御附魔 | false   |
| element | e, damagetype, type | 所造成伤害的伤害种类 | 无 |
| damagecause | dc, cause | 所造成伤害的伤害类型 | Entity_Attack |


示例
--------

对范围内的每个僵尸造成1000伤害,且每伤害1个僵尸就恢复20生命.

      Skills:
      - consume{d=1000;h=20} @MobsInRadius{type=ZOMBIE;r=20}