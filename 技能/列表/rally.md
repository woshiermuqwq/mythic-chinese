技能: Rally
--------------------------

令范围内的所有指定实体(可多种)选取技能目标为仇恨目标  

不影响施法者  
可影响原版实体

被影响实体必须可以攻击（或拥有且可正常使用AI: `meleeattack`）.  

若想直接嘲讽范围内的所有实体请用由插件: [GOOP 拓展的 RallyAll 技能](https://gitlab.com/TranslatedByShark/Gootilities/-/wikis/MythicMobs/%E6%8A%80%E8%83%BD)

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| types           | type, t | 被影响的MythicMobs实体(可为多种) | NONE          |
| radius          | r       | 影响的水平半径范围                                                              | 10            |
| vradius         | vr      | 影响的垂直半径范围                                                                 | 等值于radius        |
| hradius         | hr      | 影响的垂直半径水平                                                               | 等值于radius        |
| overwritetarget | ot      | 是否影响已拥有目标的实体  | true          |

示例
--------

```yaml
集火测试实体:
 Type: husk
 Skills:
 - skill:集火测试 ~ondamaged

#技能文档

集火测试:
 Skills:
 - m{m="<mob.name><&co>集合准备团战"} @PlayersInRadius{r=30}
 - callforhelp{t=被影响实体,被影响实体B;r=30;ot=false} @Trigger
```
施法者受伤后令半径30格方块范围内的所有未拥有目标的 被影响实体,被影响实体B  
选取触发者（攻击者）作为目标.

额外信息
-------

- **支持** [占位符](/技能/占位符)（仅限值类型为数值的修改项）
- 别称: callforhelp