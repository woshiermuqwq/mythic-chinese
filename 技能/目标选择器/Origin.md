**描述**:选取坐标原点,对于一些特殊类技能(如projectile)的onTick技能,坐标原点是抛射物本身,而不是施法者.

修改项
-----

| 修改项名 | 别称 | 描述 | 默认值 |
| -------- | ---- | ---- | ------ |
| xoffset | x | X轴偏移值 | 0.0 |
| yoffset | y | y轴偏移值 | 0.0 |
| zoffset | z | z轴偏移值 | 0.0 |

注意事项
--------

一些特殊技能内的元（子）技能（onTickSkill、onEndSkill等）
若使用该目标选择器, 则该目标选择器会选取  执行技能时该抛射物所处的坐标.  

可搭配@origin的特殊技能:  
- [Projectile](/技能/列表/Projectile)
- [Misstile](/技能/列表/Missile)
- [Chain](/技能/列表/Chain)
- [Chain Missile](/技能/列表/ChainMissile)

运用示例
-------

1. 发射抛射物,命中后以抛射物为中心创造技能区域:
```
    Skills:
    - projectile{oh=[  - projectile{ot=[  - e:p{p=flame} @origin ];oh=[  - d{a=1;i=true} @eno{r=3;ignore=self} ];i=10;v=0;type=METEOR;se=false;sb=false};sb=false;i=1;v=7} @target
```

2. 收缩环绕:
```
    Skills:
    - orbital{ot=[  - orbital{ot=[  - e:p{p=flame} @origin ];r=3;d=600;i=1;p=32;vy=60} @origin ];r=3;d=600;i=30;p=12} @self ~onSpawn
```