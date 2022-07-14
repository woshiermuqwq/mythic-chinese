技能: Chain Missile (仅限付费版)
--------------------------

向技能目标发射导弹, 随后在多个实体之间传递导弹.

修改项
----------

可使用所有[Chain](技能/列表/chain)与[Missile](技能/列表/Missile)的修改项

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| returnToCaster | rtc | 传递失败后(被传递实体不符合条件)是否传回施法者 | false | 

示例
--------

```yaml
# 实体配置
 Skills:
 - skill{s=测试} @target ~onTimer:200

# 技能组配置

测试:
 Skills:
 - ChainMissile{bounces=10;r=10;in=1.25;oT=测试_oT;oH=测试_oH;i=1;md=200;mr=30;v=5;hnp=true;hp=true;hR=1;vR=1;sB=False;sE=false;tyo=1;hs=true;hfs=1}
测试_oT:
 Skills:
 - effect:particles{particle=flame;a=1;hs=0;vs=0;s=0;y=0} @origin
测试_oH:
 Skills:
 - damage{a=1;pkb=true}
```

额外信息
--------

- 别称: cmi