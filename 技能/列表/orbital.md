技能: Orbital
--------------------------

Orbital是[Projectile](技能/列表/projectile)的一种,且会与[Aura](/技能/列表/aura)
类似,围绕目标转动,与[Projectile](技能/列表/projectile)一样,Orbital的抛射物
命中实体后可激活指定技能组,还有许多类似的地方,

修改项: bullettype 新增于 MM 4.11 (使用方法与[Projectile](技能/列表/Projectile)一致).

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| onStart             | oS       | 激活环绕后所激活的技能组 | 无          |
| onTick              | oT       | 环绕整体刷新后所激活的技能组 | 无          |
| onHit               | oH       | 环绕抛射物命中后所激活的技能组 | 无          |
| onEnd               | oE       | 环绕整体消失后所激活的技能组 | 无          |
| Charges             | c        | 环绕整体最大可命中次数 | 0 |
| Duration            | d        | 环绕整体最大持续时间(刻) | 100 |
| Interval            | i        | 环绕整体的刷新间隔(刻) | 4 |
| Radius              | r        | 环绕整体半径(格方块)范围 | 4 |
| HitRadius           | hr       | 环绕抛射物碰撞箱水平半径 | 1             |
| VerticalHitRadius   | vhr, vr  | 环绕抛射物碰撞箱垂直半径| 1             |
| Points              | p        | 环绕整体由多少个抛射物组成 | 32            |
| XRotation           | rotx, rx | 环绕整体绕X轴转向的角度 | 0             |
| YRotation           | roty, ry | 环绕整体绕Y轴转向的角度                                                                                                                                             | 0             |
| ZRotation           | rotz, rz | 环绕整体绕Z轴旋转的角度                                                                                                                                             | 0             |
| XOffset             | ox       | 环绕整体的Y轴偏移值                                                                                                                               | 0             |
| YOffset             | oy       | 环绕整体的X轴偏移值                                                                                                                               | 0             |
| ZOffset             | oz       | 环绕整体的Z轴偏移值                                                                                                                               | 0             |
| AngularVelocityX    | avx, vx  | 环绕整体绕X轴旋转的速度                                                                                                                       | 0             |
| AngularVelocityY    | avy, vy  | 环绕整体绕Y轴旋转的速度                                                                                                                        | 0             |
| AngularVelocityZ    | avz, vz  | 环绕整体绕Z轴旋转的速度                                                                                                                        | 0             |
| HitPlayers          | hp       | 环绕抛射物是否可命中玩家 | true          |
| HitNonPlayers       | hnp      | 环绕抛射物是否可命中非玩家实体 | false         |
| HitSelf             | hs       | 环绕抛射物可命中施法者 | false         |
| CancelOnGiveDamage  | cogd     | 环绕整体是否在受到伤害后消失 | false         |
| CancelOnTakeDamage  | cotd     | 环绕整体是否在造成伤害后消失 | false         |
| CancelOnDeath       | cod      | 环绕整体是否在施法者死亡后消失 | true          |
| CancelOnTeleport    | cot      | 环绕整体是否在施法者传送后消失 | false         |
| CancelOnChangeWorld | cocw     | 环绕整体是否在施法者变更世界后消失 | false         |
| CancelOnSkillUse    | cosu     | 环绕整体是否在施法者激活技能后消失 | false         |
| CancelOnQuit        | coq      | 环绕整体是否在施法者退出游戏后消失 | true          |

  

注意
-------------

目标选择器: **@origin** 对于Orbital所调用的技能组(如onTick所激活的技能)而言  
选取的是抛射物为坐标原点,而不是施法者.

与origin有关的目标选择器(如@EntitiesNearOrigin),将选取抛射物作为半径范围的中心  
而不是施法者.

与origin无关的目标选择器(如@EIR),则仍选取施法者作为半径范围的中心,所以如果不给  
ntick所激活的技能组写上目标选择器 它会选取施法者作为技能目标).

示例
--------

    环绕测试:
      Skills:
      - orbital{onTick=环绕测试-Tick;onHit=Ic环绕测试-Hit;points=20;interval=1;duration=200;charges=1;rx=0;ry=20;rz=20}
    环绕测试-Tick:
      Skills:
      - e:particles{p=flame;amount=20;speed=0;hS=0.2;vS=0.2} @origin
    环绕测试-Hit:
      Skills:
      - damage{a=10}
      - potion{type=SLOW;duration=100;lvl=2}