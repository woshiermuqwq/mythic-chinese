技能: Skill
--------------------------

向目标激活指定技能组(位于Skills文件夹的文档内).

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| skill | s, meta, m, mechanics, $, () | 被执行的技能组 | 无 |
| forcesync | sync      | 是否在主线程执行 | false   |

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

示例
--------

      Skills:
      - skill{skill=技能组} @T ~onAttack
      - skill{s=技能组} @Trigger ~onSpawn
      - skill:技能组 @Trigger ~onDeath
      - skill
          {
          skill=一个技能组;
          sync=true
          } @self ~onDamaged