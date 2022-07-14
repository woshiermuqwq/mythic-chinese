技能: Chain (4.9)
--------------------------

向技能目标发射链条（瞬间命中）, 随后在多个实体之间传递链条.

传递就像“闪电链”,如,如果有人站在墙 的另一边,而你却站在门口  此技能可能  
从你身上连锁到他们身上,因为此技能也会在命中方块后尝试连锁  

传递过程中同一个实体只能被传递一次,且命中方块/实体后,传递起点由施法者  
变为所命中事物.

换句话说,传递命中事物后将以所命中事物为"施法者"再次激活传递以尝试传递技能  
到其它目标,但实际上多次传递都归于 施法者所释放的传递.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| onBounce         | ob         | 传递命中后所激活的技能组 | 无 |
| bounces          | b          | 最大传递次数（支持[占位符](/技能/占位符)） | 2       |
| bouncedelay            | bd, delay, d, interval, i          | 传递命中后将技能传递到其它可被传递实体的间隔(刻) | 1       |
| bounceradius           | bouncerange, radius, range, r          | 传递所命中的事物与可被传递实体的最大距离(方块格) | 5       |
| hitSelf          | hs         | 施法者是否可被传递 | false   |
| hitTarget        | ht         | 被传递的第一个事物是否必须是技能目标 | true    |
| hitPlayers       | hp         | 玩家是否可被传递 | true    |
| hitNonPlayers    | hnp        | 非玩家实体是否可被传递 | false   |
| bounceConditions | conditions, cond, c | 满足条件的可被传递实体才能够被传递 | 无    |

新增于 MM 4.8

示例（实体配置）
--------

```yaml
 Skills:
 - chain{
  bounces=5;
  bounceRadius=10;
  bounceDelay=1;
  hitSelf=false;
  hitPlayers=true; 
  hitNonPlayers=true;
  hitTarget=true;
  onBounce=[
    - effect:particleline{p=flame;fromOrigin=true}
  ];
  bounceConditions=[
    - inlineofsight
    - hasaura{aura=标记} false
  ]} @target ~onTimer:20
```
每秒向仇恨目标发射链条  
链条传递次数为5  
传递判定范围为半径10格方块  
传递延迟为0.05秒  
无法传递至施法者  
可传递至玩家  
可传递至技能目标  
传递时激活粒子线技能  
只有在事业内且拥有光环: `标记` 的实体才能被传递 