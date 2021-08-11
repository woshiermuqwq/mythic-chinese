技能: Modify Global Score
--------------------------

修改全局记分板分数.

可用算法:

-   SET(设置)
-   ADD(加)
-   SUBTRACT(减)
-   MULTIPLY(乘以)
-   DIVIDE(除)
-   MOD(除以后取余)

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| objective | obj, o  | 用于修改的记分板名,不存在则创建 |         |
| action    | a       | 算法                                                                                                         | ADD     |
| value     | v       | 修改值                                                                                          |         |

示例
--------

    - modifyglobalscore
        {
        objective=someobjective;
        action=multiply;
        v=2
        } ~onAttack
