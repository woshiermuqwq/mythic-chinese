技能: Orbital
--------------------------

Orbital是[Projectile](技能/列表/projectile)的一种,且会与[Aura](/技能/列表/aura)  
类似,围绕目标转动,与[Projectile](技能/列表/projectile)一样,Orbital的抛射物  
命中实体后可激活指定技能组,还有许多类似的地方  
施法者消失后消失

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| onStart             | oS       | 激活环绕后所激活的技能组 | 无          |
| onTick              | oT       | 环绕整体刷新后所激活的技能组 | 无          |
| onHit               | oH       | 环绕抛射物命中实体后所激活的技能组 | 无          |
| onEnd               | oE       | 环绕整体消失后所激活的技能组 | 无          |
| Charges             | c        | 环绕整体最大可命中次数 | 0 |
| Duration            | d        | 环绕整体最大持续时间(刻) | 100 |
| Interval            | i        | 环绕整体的刷新间隔(刻) | 4 |
| Radius              | r        | 环绕整体半径(格方块)范围 | 4 |
| HitRadius           | hr       | 环绕抛射物碰撞箱水平半径 | 1             |
| HitSelf | hs | 环绕抛射物是否可命中施法者 | false |
| HitPlayers | hp | 环绕抛射物是否可命中玩家 | true |
| HitNonPlayers | hnp | 环绕抛射物是否可命中非玩家实体 | false |
| VerticalHitRadius   | vhr, vr  | 环绕抛射物碰撞箱垂直半径（格方块） | 1             |
| Points              | p        | 环绕整体由多少个点组成 | 32            |
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
| StartingPoint | sq | 环绕抛射物从环绕整体的 第几点 位置开始 | 0 |

修改项: bulletType 新增于 MM 4.11 (此处未列出 使用方法与[Projectile](技能/列表/Projectile)一致).  
修改项: StartingPoint 新增于 MM 4.12（基于修改项: Point）.

注意
-------------

目标选择器: **@origin** 对于Orbital所调用的技能组(如onTick所激活的技能)而言  
选取的是抛射物为坐标原点, 而非施法者.

与origin有关的目标选择器(如@EntitiesNearOrigin), 将选取抛射物作为半径范围的中心  
而非施法者.

与origin无关的目标选择器(如@EIR),则仍选取施法者作为半径范围的中心,所以如果不给  
ntick所激活的技能组写上目标选择器 它会选取施法者作为技能目标).  

环绕的起始角度可通过修改项: `X/Y/ZRotate`、`StartingPoint` 改变   
但不受技能目标视角影响 

当 Orbital 的 bullet 为 mob 时, 该实体可以被命令所删除  
这意味着orbital套orbital能做到随时停止第二个orbital  

修改项: `X/Y/ZOffset` 值若为一个占位符  
则环绕期间变更占位符的值将自动更新环绕的偏移

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
 - o{i=1;ot=[  - e:p{c=#FFFFFF} @origin ];ry=0.785398164640625;p=1;r=2} @self
 - o{i=1;ot=[  - e:p{c=#FFFFFF} @origin ];ry=2.35619449019250;p=1;r=2} @self
 - o{i=1;ot=[  - e:p{c=#FFFFFF} @origin ];ry=3.92699081698974;p=1;r=2} @self
 - o{i=1;ot=[  - e:p{c=#FFFFFF} @origin ];ry=5.497787143785636;p=1;r=2} @self
```

额外信息
-------

- **支持** [占位符](/技能/占位符)（仅限值类型为数值的修改项, 如radius）
- 缩写: o