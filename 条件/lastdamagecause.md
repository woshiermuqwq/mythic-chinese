**描述:** 若最后一次受伤的伤害类型为(内在).

修改项
---

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| damagecause | cause, c | 无 |

可用的伤害类型列表: [点我](/实体/伤害调整)

示例
---

```yaml
 Conditions:
 - lastdamagecause{c=ENTITY_ATTACK} true
```

关于 内/外 在
---

此条件检测的是内在  
而条件: [Damage Cause](/条件/damagecause) 检测的是外在

这是一个技能组:  
```yaml
测试:
 Skills:
 - damage{damagecause=FIRE_TICK;amount=999} @eir{r=5}
```
该技能组会对范围内实体造成伤害来源为 烧伤 的伤害  
若杀死玩家，会提示该玩家被烧死，所以选项: `damagecause=FIRE_TICK` 是有效的  
（顺带一提，伤害来源不需要全大写，这边是为了规范）

这是一个实体配置:  
```yaml
123:
 Health: 50
 Type: slime
 Faction: 1
 Display: '1'
 AIGoalSelectors:
 - clear
 Options:
  Size: 2
  Silent: true
  PreventSplit: true
 Skills:
 - m{m=表面伤害来源skill} @world ~ondamaged ?damagecause{c=skill}
 - m{m=内在伤害来源skill} @world ~ondamaged ?lastdamagecause{c=skill}
 - m{m=表面伤害来源烧伤} @world ~ondamaged ?damagecause{c=fire_tick}
 - m{m=内在伤害来源烧伤} @world ~ondamaged ?lastdamagecause{c=fire_tick}
 - m{m=真正的伤害来源<skill.var.real-damage-cause>（5.2.1）} @world ~ondamaged
```
符合对应条件会收到对应消息  
不多解释, 当我 `/mm t cast 测试` 后:  
![image](uploads/b3f9acb75875617f2c2d583b40c62970/image.png)  
可见条件: [Damage Cause]并没有正常工作, 这是因为该条件在伤害技能应用伤害来源时尚未更新所需读取的伤害来源

拓展信息
---

- 检测对象: 实体