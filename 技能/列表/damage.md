技能: Damage
--------------------------

对技能目标造成伤害.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| damage           | a | 所造成的伤害数值（为负时不造成伤害, 但仍会触发受伤事件）         | 1    |
| preventknockback | pkb, pk | 是否不会造成击退   | false   |
| preventimmunity  | pi      | 是否无视受伤间隔   | false   |
| ignorearmor      | ia, i    | 是否无视实体防御 | false   |
| ignoreenchantments      | ignoreenchants, ie    | 是否无视防御附魔<br>MC版本至少为1.19 | false   |
| element | e, damagetype, type | 所造成伤害的伤害种类 | 无 |
| damagecause | dc, cause | 所造成伤害的伤害来源 | Entity_Attack |


### 伤害类型 (Element)
伤害类型的使用方法:

```yaml
伤害测试技能:
 Skills:
 - damage{amount=10;element=FIRE} @target ~onUse
 - damage{amount=10;element=ICE} @target ~onUse
```
上述这俩伤害类型可被伤害调整所影响:
```yaml
伤害测试实体: 
 Type: COW 
 DamageModifiers:
 - LIGHTNING 0.1
 - FIRE 2.0
 - AIR 1.0
 - ICE 0.5 
 Skills:
 - m{m="受到 <skill.var.damage-amount> <skill.var.damage-type>伤害"} @PIR{r=50} ~onDamaged
```

### 示例

```yaml
 Skills:
 - d{a=20;ia=true} @T ~onTimer:20
```
每秒对目标造成20点无视防御的伤害
```yaml
冰冻:
 Skills:
 - sound{s=block.fire.extinguish;v=1;p=0.5} @pir{r=6}
 - e:p{p=explode;a=8;vs=0.5;hs=0.5;s=0;y=1;repeat=5;repeatInterval=20} @PIR{r=6}
 - e:p{p=drip_water;a=10;vs=0.5;hs=0.5;s=0;y=1;repeat=5;repeatInterval=20} @pir{r=6}
 - potion{t=SLOW;d=120;l=6} @PIR{r=6}
 - d{a=120;pk=true} @pir{r=6}

此技能组将对半径6格方块范围内的所有玩家播放熄火音效  
播放白烟粒子效果与溅水粒子效果,造成120点不附带击退  
效果的伤害并附带6秒的移速降低120%的状态效果.

### 应用变量示例

```yaml
 Skills:
 - d{a=<caster.var.somevariable>*0.5+1} @T ~onTimer:20
```
每秒对目标造成 变量somevariable的值 * 0.5 +1 的伤害,当变量值为2时,造成2点伤害  
为4时,造成3点伤害..

提示
----

伤害来源（DamageCause）不同于伤害类型（Element）  
当来源为Fire时, 被击杀者将显示被烧死  
当类型为Fire时, 则只是正常的被打死  
当受伤事件触发时, 仅当伤害来源为 `entity_attack`, `entity_sweep_attack`, `thorns`, `sonic_boom`, `entity_explosion`, 与 `projectile` 时, 受伤事件触发者才会选取到一个实体, 反之无法选中  
远程实体最好将damagecause改为projectile（远程实体无法造成近身攻击, 也就是entity_attack）

额外信息
-------

- **支持** [占位符](/技能/占位符)（仅限值类型不为布尔值的修改项）
- 缩写: d
- 施法者类型不可为 Marker（解决方法是用SudoSkill）