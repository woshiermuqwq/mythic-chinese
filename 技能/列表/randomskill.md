技能: Random Skill
--------------------------

向目标激活多个技能组内的一个.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| skills | s, metas, meta, m | 用于选取的多个技能组 | 无 |

示例
--------

    Skills:
    - randomskill{skills=skill1,skill2,skill3}

另一种格式:

    Skills:
    - randomskill{
        skills=
        superskill,
        green_skill,
        skill3,
        grandSkill,
        7331
        }

额外信息
---

- [x] 别称: randommeta