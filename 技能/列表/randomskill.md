技能: Random Skill
--------------------------

向目标激活多个技能组内的一个.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| skills | s, metas, meta, m | 用于选取的多个技能组 | 无 |
| fallbackskill | fbskill, fbs | 若没有选中skills所定义的技能组, 则激活指定技能组 | 无 |

示例
--------

```yaml
 Skills:
 - randomskill{skills=技能组A,技能组B,技能组C}
```
另一种格式:
```yaml
 Skills:
 - randomskill{
  skills=
  技能组D,
  技能组E,
  技能组F,
  技能组G,
  技能组Z
  }
```
上述格式中各个技能组被激活的预期几率是相等的

在 MM 4.13, 可通过该格式自定义每个技能的概率

```yaml
 Skills:
 - randomskill{skills=技能组A 50,技能组B 25,技能组C 15}
```

```yaml
 Skills:
 - randomskill{
  skills=
  技能组D 50,
  技能组E 25,
  技能组F 10,
  技能组G 5,
  技能组Z 20
  }
```
举个例子, 50+25+10+5+20=110  
那技能组F有 10/110≈9% 的几率激活  
Z有 20/110=18%的几率激活

行内技能组写法
---

```yaml
- randomskill{s=
  [  - message{m=A} ],
  [  - m{m=B} ],
  [  - m{m=CDE} 
     - m{m=DEC}
     - m{m=ECD} ]}
```
额外信息
---

- [x] 别称: randommeta