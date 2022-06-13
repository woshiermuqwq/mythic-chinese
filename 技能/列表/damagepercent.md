技能: Damage Percent
--------------------------

对技能目标造成 技能目标最大生命 * 指定百分比的伤害.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| percent           | p | 所乘以的百分比（为负时不造成伤害, 但仍会变红 支持[占位符](/技能/占位符)）         | 0.1    |
| preventknockback | pkb, pk | 是否不会造成击退   | false   |
| preventimmunity  | pi      | 是否无视受伤间隔   | false   |
| ignorearmor      | ia, i    | 是否无视实体防御 | false   |
| ignoreenchantments      | ignoreenchants, ie    | 是否无视防御附魔 | false   |
| element | e, damagetype, type | 所造成伤害的伤害种类 | 无 |
| damagecause | dc, cause | 所造成伤害的伤害类型 | Entity_Attack |

示例 (4.11+)
--------

      Skills:
      - damagepercent{percent=0.5} @target

对当前目标造成其最大生命的50%点伤害