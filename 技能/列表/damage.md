技能: Damage
--------------------------

对目标造成伤害.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| damage           | a | 所造成的伤害数值         | 1    |
| preventknockback | pkb, pk | 是否不会造成击退   | false   |
| preventimmunity  | pi      | 是否无视受伤间隔   | false   |
| ignorearmor      | i,ia    | 是否无视实体防御 | false   |
| element | type | 所造成伤害的伤害类型 | 无 |

### 伤害类型 (Element)
  伤害类型的使用方法:

  伤害测试技能:
    Skills:
    - damage{amount=10;element=FIRE} @target ~onUse
    - damage{amount=10;element=ICE} @target ~onUse

上述这俩伤害类型可被伤害调整所影响:

    伤害测试实体: 
      Type: COW 
      DamageModifiers:
        - LIGHTNING 0.1
        - FIRE 2.0
        - AIR 1.0
        - ICE 0.5 
      Skills:
        - message{m="受到 <skill.var.damage-amount> <skill.var.damage-type>伤害"} @PIR{r=50} \~onDamaged

### 示例

      Skills:
      - damage{amount=20;ignoreArmor=true} @target ~onTimer:20

每秒对目标造成20点无视防御的伤害

    冰冻:
      Skills:
      - effect:sound{s=block.fire.extinguish;v=1;p=0.5} @PIR{r=6}
      - e:particles{p=explode;a=8;vs=0.5;hs=0.5;s=0;y=1;repeat=5;repeatInterval=20} @PIR{r=6}
      - effect:particles{p=drip_water;a=10;vs=0.5;hs=0.5;s=0;y=1;repeat=5;repeatInterval=20} @PIR{r=6}
      - potion{t=SLOW;d=120;l=6} @PIR{r=6}
      - damage{a=120;pkb=true} @PIR{r=6}

此技能组将对半径6格方块范围内的所有玩家播放熄火音效  
播放白烟粒子效果与溅水粒子效果,造成120点不附带击退  
效果的伤害并附带6秒的移速降低120%的状态效果.

### 应用变量示例

      Skills:
      - damage{amount=<caster.var.somevariable> * 0.5 + 1} @target ~onTimer:20

每秒对目标造成 变量somevariable的值 * 0.5 +1 的伤害,当变量值为2时,造成2点伤害  
为4时,造成3点伤害..