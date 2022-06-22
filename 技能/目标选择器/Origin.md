**描述**: 选取坐标原点,对于一些特殊类技能(如[Projectile](/技能/列表/projectile))的onTick技能,坐标原点是抛射物本身, 而不是施法者.

修改项
-----

| 修改项名 | 别称 | 描述 | 默认值 |
| -------- | ---- | ---- | ------ |
| xoffset | x | X轴偏移值 | 0.0 |
| yoffset | y | y轴偏移值 | 0.0 |
| zoffset | z | z轴偏移值 | 0.0 |
| forwardoffset| | 前后偏移（基于视角） | 0.0 |
| sideoffset| | 左右偏移（基于视角） | 0.0 |

注意事项
--------

一些特殊技能内的元（子）技能（onTickSkill、onEndSkill等）
若使用该目标选择器, 则该目标选择器会选取  执行技能时该抛射物所处的坐标.  

**千万别为目标选择器为@Origin或以坐标原点的技能加上冷却**

可搭配@origin的特殊技能:  
- [Projectile](/技能/列表/Projectile)
- [Missile](/技能/列表/Missile)
- [Chain](/技能/列表/Chain)
- [Chain Missile](/技能/列表/ChainMissile)

一些带有"Origin" 字眼的目标选择器将以执行时抛射物位置为中心（如@Entitiesnearorigin、@Blocksnearorigin）

运用示例
-------

1. 向仇恨目标发射抛射物, 命中后以抛射物为中心创造持续对玩家造成伤害的区域:
```yaml
    Skills:
    - projectile{oh=[
      - projectile{i=10;v=0;type=METEOR;se=false;sb=false};sb=false;i=5;v=7;
        ot=[
        - e:p{p=flame} @origin
        - d{a=1;i=true} @eno{r=3}
        ]} @origin
      ]} @target
```

2. 收缩环绕:
```yaml
    Skills:
    - orbital{ot=[
      - orbital{ot=[
        - e:p{p=flame} @origin
        ];r=3;d=600;i=1;p=32;vy=60} @origin
      ];r=3;d=600;i=30;p=12} @self ~onSpawn
```