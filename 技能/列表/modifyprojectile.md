技能: Modify Projectile (4.12)
--------------------------

修改 [projectile](技能/列表/projectile), [missile](技能/列表/missile), [orbital](技能/列表/orbital)抛射物的修改项.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| trait     | t | 修改项名,可以是 inertia(惯性), gravity(重力), velocity(速度), power(技能威力),  radius(半径)（支持[占位符](/技能/占位符)） | |
| action    | a | 修改模式,SET 或 MULTIPLY(乘以)（支持[占位符](/技能/占位符)） | 无 |
| value     | v | 所修改的值（支持[占位符](/技能/占位符)） | | 无 |

示例
--------

```yaml
修改抛射物测试:
 Skills:
 - projectile{oT=测试Tick;i=1;v=8;d=200;mr=100} @forward{f=100;y=0}
测试Tick:
 Skills:
 - particles{particle=flame;a=2;hs=0;vs=0;s=0;y=0} @origin
 - modifyProjectile{trait=VELOCITY;action=MULTIPLY;value=0.95}
```
这个抛射物发射后会缓慢减速.
