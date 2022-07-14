技能: Potion
--------------------------

将状态效果应用于技能目标.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| effect         | type, t              | 所应用的[状态效果](/物品/状态效果).                           | 无      |
| duration     | d              | 持续时间(刻).                                                  | 100     |
| level        | lvl, l              | 状态效果等级,实际等级为所写值+1. | 1       |
| overwrite        | ow, override, or, force  | 是否替换相同状态效果(等级)                          | false   |
| hasParticles | particles, p | 是否显示状态效果粒子                                   | true    |
| hasIcon      | icon, i      | 是否显示状态效果图标                                        | true    |

示例
--------

此技能组将对技能目标造成持续10秒的移速降低100%(缓慢5)效果与10伤害.

```yaml
测试:
 Skills:
 - potion{type=SLOW;duration=200;level=4}
 - damage{amount=10}
```

提示
----

击杀实体时, 被击杀实体先前的状态效果施加者不会成为击杀者  
这意味着 凋零 等状态效果击杀实体后, 施法者不会触发已配置好的  
击杀信息.

解决方法:  

```yaml
测试实体:
  Type: husk
  Skills:
  - skill:凋零效果 @trigger ~onattack
```

```yaml
凋零效果:
  Skills:
  - potion{t=wither;d=60}
  - ondamaged{auraname=1;d=60;c=9999;i=1;damageMods="WITHER 0";ot=给予伤害}
给予伤害:
  Cooldown: 1
  TargetConditions:
  - hasaura{aura=1} false
  - haspotioneffect{t=wither}
  Skills:
  - damage{a=1;i=true}
```

额外信息
--------

- **支持** [占位符](/技能/占位符)（仅限值类型为数值的修改项与type）
- [x] 状态效果无效报错: `The 'type' attribute must be a valid potion type`