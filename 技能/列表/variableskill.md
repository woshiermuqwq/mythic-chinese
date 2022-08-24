技能: VariableSkill
--------------------------

向技能目标激活指定技能组(位于Skills文件夹的文档内).

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| skill | s, meta, m, mechanics, $, () | 被执行的技能组, (支持[占位符](/技能/占位符)) | 无 |
| forcesync | sync      | 是否在主线程执行 | false   |

关于 与[Skill](/技能/列表/skill) 的区别
-----

技能组名支持占位符, 这意味着现在可以在不检测变量的条件下  
变相令不支持占位符的技能支持占位符, 如 [Summon](/技能/列表/summon)的 `Type`  
假设我们要让怪物被右键后随机召唤"1""2""3"内的一个, 若仅使用 [Skill](/技能/列表/skill)则需要  
```yaml
测试实体:
 Type: husk
 Skills:
 - setvar{var=caster.summon;v=<random.1to3>} @self ~oninteract
 - skill:召唤检测 @self ~oninteract

###技能文档

召唤检测:
 Skills:
 - summon{t=1} ?varrange{var=caster.summon;v=1}
 - summon{t=2} ?varrange{var=caster.summon;v=2}
 - summon{t=3} ?varrange{var=caster.summon;v=3}
```
使用 VaribleSkill 后

```yaml
测试实体:
 Type: husk
 Skills:
 - setvar{var=caster.summon;v=<random.1to3>} @self ~oninteract
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

额外信息
----

- 别称: metavariableskill, vskill