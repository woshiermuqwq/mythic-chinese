**描述:** 若实体当前生命在指定数值范围内.

修改项
---

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| amount    | a, health, h       | 用于检测的血量数值范围 |

示例
---

```yaml
Conditions:
- health{h=50} true
```

```yaml
# 当前生命在50以下
Conditions:
- health{h=<50} true
```

```yaml
# 当前生命在10以上
Conditions:
- health{h=>10} true
```

```yaml
# 技能目标生命在50%以下
检测目标:
 Skills:
 - skill:检测百分比 @entitiesinradius{radius=16}
检测百分比:
 Skills:
 - setvariable{variable=skill.aaa;type=float;value=<target.php>}
 - skill:检测成功
检测成功:
 TargetConditions:
 - variablerange{var=skill.aaa;value=<50}
 Skills:
 - damage{a=999}
```

```yaml
# 自身生命在50%以下
检测目标:
 Skills:
 - skill:检测百分比 @self
检测百分比
 Skills:
 - setvariable{variable=skill.aaa;type=float;value=<target.php>}
 - damage{a=999} ?varrange{var=caster.aaa;v=<50}
```

拓展信息
---

- 检测对象: 实体
- 别称: hp