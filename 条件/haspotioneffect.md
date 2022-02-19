**描述:** 若实体拥有状态效果且时长与等级在指定数值范围内.

---

**修改项:**

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| type      | t       | 用于检测的药水效果类型, 为空时代表 ANY              |
| level     | lvl, l  | 用于检测的等级数值范围    |
| duration  | d       | 用于检测的时长数值范围 |

---

**示例:**

```
Conditions:
- haspotioneffect{t=SLOW;l=0-2;d=0-9999} true
```

```
TargetConditions:
- haspotioneffect{t=Speed;l=0-9} true
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

---

**拓展信息:**

- [x] 检测对象: 实体
- [x] 别称: hasPotion