特效技能: Spin
--------------------------

旋转技能目标的朝向.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| duration         | d     | 旋转的持续时间（单位: 刻, 支持[占位符](/技能/占位符)）  | 40             |
| velocity         | v     | 旋转速度, 正数顺时针转负数逆时针转（支持[占位符](/技能/占位符)） | 18 |

技巧
--------

通过设置转速为0以锁定施法者朝向.

通过多次激活来做到"螺旋升天".

提示
---

MC 1.13 以下的版本可在使用下列技能修改实体的pitch为0后  
激活速度为0的spin, 以让实体的其它功能正常工作  
如下列的技能组可防止因视角而导致[projectile](/技能/列表/projectile)发射方向错误
```yaml
 - skill{s=[
  - setvar{var=skill.1;t=float;v=<caster.l.yaw>-1}
  - delay 1
  - cmd{;c="entitydata @s {Rotation:[<caster.var.1>f]}";astarget=true;asop=true}
  - projectile{ot=[  - e:p ];se=false;sb=false;i=1} @forward{f=999}
  ]} @self ~oninteract
```

示例
--------

```yaml
测试实体:
 Type: husk
 Skills:
 - spin{duration=20;velocity=30} @self ~ondamaged
```
受击后转一秒圈圈

额外信息
--

- 别称: effect:spin, e:spin