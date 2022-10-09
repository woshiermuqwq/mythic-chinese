技能: Orbital
--------------------------

Orbital是[Projectile](技能/列表/projectile)的一种,且会与[Aura](/技能/列表/aura)  
类似,围绕技能目标转动,与[Projectile](技能/列表/projectile)一样,Orbital的抛射物  
命中实体后可激活指定技能组,还有许多类似的地方  
施法者消失后消失

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| onStart             | oS       | 激活环绕后所激活的技能组 | 无          |
| onTick              | oT       | 环绕到达下一个点时所激活的技能组 [更多信息](#子技能组) | 无          |
| onHit               | oH       | 环绕抛射物命中实体后所激活的技能组 [更多信息](#子技能组) | 无          |
| onEnd               | oE       | 环绕结束所激活的技能组 [更多信息](#子技能组) | 无          |
| Charges             | c        | 环绕整体最大可命中次数 | 0 |
| Duration            | d        | 环绕整体最大持续时间(刻) | 100 |
| Interval            | i        | 环绕多久转动到下一个点(游戏刻)<br>意味着该选项也可影响环绕整体速度<br>也决定onTickSkill的激活频率 | 4 |
| Radius              | r        | 环绕整体半径(格方块)范围 | 4 |
| HitRadius           | hr       | 环绕抛射物碰撞箱水平半径 | 1             |
| HitSelf | hs | 环绕抛射物是否可命中施法者 | false |
| HitPlayers | hp | 环绕抛射物是否可命中玩家 | true |
| HitNonPlayers | hnp | 环绕抛射物是否可命中非玩家实体 | false |
| VerticalHitRadius   | vhr, vr  | 环绕抛射物碰撞箱垂直半径（格方块） | 1             |
| Points              | p        | 环绕整体由多少个点组成<br>环绕每游戏刻所绕过的角度=360/该选项值 | 32            |
| XRotation           | rotx, rx | 环绕整体绕X轴转向的角度（角度制）<br>角度制简单理解就是半径越大, 效果差距就越大<br>实际值应 x  0.0174532925199544 | 0             |
| YRotation           | roty, ry | 环绕整体绕Y轴转向的角度（角度制）                                                                                                                                             | 0             |
| ZRotation           | rotz, rz | 环绕整体绕Z轴旋转的角度（角度制）                                                                                                                                             | 0             |
| XOffset             | ox       | 环绕整体的X轴偏移值                                                                                                                               | 0             |
| YOffset             | oy       | 环绕整体的Y轴偏移值                                                                                                                               | 0             |
| ZOffset             | oz       | 环绕整体的Z轴偏移值                                                                                                                               | 0             |
| AngularVelocityX    | avx, vx  | 环绕整体绕X轴旋转的速度                                                                                                                       | 0             |
| AngularVelocityY    | avy, vy  | 环绕整体绕Y轴旋转的速度                                                                                                                        | 0             |
| AngularVelocityZ    | avz, vz  | 环绕整体绕Z轴旋转的速度                                                                                                                        | 0             |
| CancelOnGiveDamage  | cogd     | 环绕整体是否在受到伤害后消失 | false         |
| CancelOnTakeDamage  | cotd     | 环绕整体是否在造成伤害后消失 | false         |
| CancelOnDeath       | cod      | 环绕整体是否在施法者死亡后消失 | true          |
| CancelOnTeleport    | cot      | 环绕整体是否在施法者传送后消失 | false         |
| CancelOnChangeWorld | cocw     | 环绕整体是否在施法者变更世界后消失 | false         |
| CancelOnSkillUse    | cosu     | 环绕整体是否在施法者激活技能后消失 | false         |
| CancelOnQuit        | coq      | 环绕整体是否在施法者退出游戏后消失 | true          |
| StartingPoint（4.12） | sq | 环绕抛射物从环绕整体的 第几点 位置开始<br>取决于环绕有多少点 | 0 |

修改项: bulletType 新增于 MM 4.11 (此处未列出 使用方法与[Projectile](技能/列表/Projectile)一致).  

子技能组
---

onTickSkill的[坐标原点](/目标选择器/origin)为激活该技能组时时环绕所处点的位置  
onHitSkill的[坐标原点](/目标选择器/origin)为命中实体时环绕所处点的位置  
onEndSkill的[坐标原点](/目标选择器/origin)为环绕结束时环绕所处点的位置  
**强烈建议阅读[坐标原点](/目标选择器/origin), 因其通常用于制作范围伤害**

若技能组目标选择器为空则选取拥有该环绕的事物  

拥有环绕的实体死亡并不会激活onEndSkill  

注意
-------------


环绕的起始角度可通过修改项: `X/Y/ZRotate`、`StartingPoint` 改变   
但不受技能目标视角影响 

当 Orbital 的 bullet 为 mob 时, 该实体可以被命令所删除  
这意味着orbital套orbital能做到随时停止第二个orbital  
或直接杀死拥有第一个Orbital的实体即可同时停止俩个orbital

修改项: `X/Y/ZOffset/Velocity/Rotate` 值若为一个占位符  
则环绕期间变更占位符的值将自动更新环绕的偏移/轴速度/轴旋转

示例
--------

```yaml
环绕测试:
 Skills:
 - orbital{onTickSkill=环绕测试-Tick;onHitSkill=环绕测试-Hit;points=20;interval=1;duration=200;charges=1;rx=0;ry=20;rz=20}
环绕测试-Tick:
 Skills:
 - effect:particles{particle=flame;amount=20;speed=0;hS=0.2;vS=0.2} @origin
环绕测试-Hit:
 Skills:
 - Damage{amount=10}
 - Potion{type=SLOW;duration=100;level=2}
```
螺旋升天:
```yaml
bc:
 Skills:
 - o{i=1;ot=1;ry=0.785398164640625;p=1;r=2} @self
 - o{i=1;ot=1;ry=2.35619449019250;p=1;r=2} @self
 - o{i=1;ot=1;ry=3.92699081698974;p=1;r=2} @self
 - o{i=1;ot=1;ry=5.497787143785636;p=1;r=2} @self
1:
 Skills:
 - e:p{a=1} @origin
```

额外信息
-------

- **支持** [占位符](/技能/占位符)（仅限值类型为数值的修改项, 如radius）
- 缩写: o