技能: Skill
--------------------------

向技能目标激活指定技能组(位于Skills文件夹的文档内).

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| skill | s, meta, m, mechanics, $, () | 被执行的技能组 | 无 |

关于 Sync
-----

正常情况下MM技能都是异步执行的, 就是做啥都会比原版慢一步  
一些技能需要 `sync=true`, 如常用的 [Cancel Event](/技能/列表/cancelevent)  
以及施法者为非玩家时的 [Ray Trace](/技能/列表/raytrace) [To](/技能/列表/raytraceto)  
但当 `sync=true` 的技能组调用其它技能组时, 其将变为异步执行  
就比如:
```yaml
###实体文档
实体:
 Type: husk
 Skills:
 - skill:测试{sync=true} ~onTimer:60
###技能文档
测试:
 Skills:
 - projectile{ot=测试tick;d=100}
 - delay 100
 - aura{ot=测试tick;d=100}
测试tick:
 Skills:
 - message{m=1}
 - raytrace{...}
```  
上述示例内的 `message` 会正常执行, 但 `raytrace` 不会被执行  
因施法者为非玩家时, raytrace需在主线程进行  
虽技能组: 测试 在主线程进行, 但由于 `raytrace` 为技能组: 测试tick 内的技能行  
且该技能组为 [Projectile](/技能/列表/projectile)/[Aura](/技能/列表/aura) 所调用  
该技能组则变回了异步执行, 所以需要这么改:
```yaml
测试:
 Skills:
 - skill:测试tick{repeat=99;repeatinterval=1}
 - delay 100
 - skill{s=测试tick}
测试tick:
 Skills:
 - message{m=1}
 - raytrace{...}
```

关于 与[Variable Skill](/技能/列表/variableskill) 的区别
-----

技能组名支持占位符, 这意味着现在可以在不检测变量的条件下  
变相令不支持占位符的技能支持占位符, 如 [Summon](/技能/列表/summon)的 `Type`  
假设我们要让怪物被右键后随机召唤"1""2""3"内的一个, 若仅使用 [Skill](/技能/列表/skill)则需要  
```yaml
测试实体:
 Type: husk
 Skills:
 - setvar{caster.summon;v=<random.float.1to3>} @self ~oninteract
 - skill:召唤检测 @self ~oninteract

###技能文档

召唤检测:
 Skills:
 - summon{t=1} ?varrange{var=caster.1}
 - summon{t=2} ?varrange{var=caster.2}
 - summon{t=3} ?varrange{var=caster.3}
```
使用 VaribleSkill 后```yaml
测试实体:
 Type: husk
 Skills:
 - setvar{caster.summon;v=<random.float.1to3>} @self ~oninteract
 - vskill{s=召唤<caster.var.1>} @self ~oninteract

###技能文档

召唤1:
 Skills:
 - summon{t=1}
召唤2:
 Skills:
 - summon{t=2}
召唤3:
 Skills:
 - summon{t=3}
```

示例（实体配置）
--------

```yaml
 Skills:
 - skill{skill=技能组} @T ~onAttack
 - skill{s=技能组B} @server ~onSpawn
 - skill:技能组C @Trigger ~onDeath
 - skill
  {
  skill=一个技能组;
  sync=true
  } @self ~onDamaged
```
攻击后以仇恨目标为技能目标激活技能组: `技能组`  
生成后以全服玩家为技能目标激活技能组: `技能组B`  
死亡后以击杀者为技能目标激活技能组: `技能组C`  
受伤后以攻击者为技能目标激活技能组: `一个技能组`, 且在主线程激活


额外信息
----

- 别称: metaskill, meta