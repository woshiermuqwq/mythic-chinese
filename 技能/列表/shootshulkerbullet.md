技能: Shoot Shulker Bullet
--------------------------

向技能目标发射潜影贝导弹  
技能目标必须是实体

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| interval  | i       | 导弹刷新间隔     | 4             |
| onTick    | oT      | 导弹刷新后所释放的技能  | 无          |
| onHit     | oH      | 导弹命中后所释放的技能 | 无 |
| onEnd     | oE      | 导弹结束后所释放的技能 | 无          |

新增于 MM 4.12

示例
--------

```yaml
潜影贝导弹测试:
  Skills:
  - ShootShulkerBullet{oT=潜影贝导弹测试_oT;oH=潜影贝导弹测试_oH;oE=潜影贝导弹测试_oE;i=1} @target
  
潜影贝导弹测试_oT:
  Skills:
  - particles{particle=reddust;color=#ffffff;size=0.66;a=2;hs=0;vs=0;s=0;y=0} @origin
潜影贝导弹测试_oH:
  Skills:
  - damage{a=5}
潜影贝导弹测试_oE:
  Skills:
  - particlesphere{particle=reddust;color=#ffffff;size=0.66;a=30;r=1;hs=0;vs=0;s=0;y=0} @origin
```

@origin对于导弹所释放的技能而言,选取的是抛射物为坐标原点而不是选取施法者为坐标原点.

额外信息
---

- [x] 别称: shootshulker