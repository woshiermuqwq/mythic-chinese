技能: Base Damage
--------------------------

对目标造成等值于(手持武器攻击力 + 基础攻击力) * 百分比的伤害.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| multiplier           | m | 所乘以的百分比（支持[占位符](/技能/占位符)）         | 1    |
| preventknockback | pkb, pk | 是否不会造成击退   | false   |
| preventimmunity  | pi      | 是否无视受伤间隔   | false   |
| ignorearmor      | ia, i    | 是否无视实体防御 | false   |
| ignoreenchantments      | ignoreenchants, ie    | 是否无视防御附魔 | false   |
| element | e, damagetype, type | 所造成伤害的伤害种类 | 无 |
| damagecause | dc, cause | 所造成伤害的伤害类型 | Entity_Attack |

示例
--------

受伤后对目标造成15[(0 + 10) * 1.5]伤害.

      AMob:
        Type: HUSK
        Damage: 10
      Skills:
      - bd{m=1.5} @T ~onDamaged

1 = 100%

拓展信息
--------

- 别称: bd, weapondamage, wd