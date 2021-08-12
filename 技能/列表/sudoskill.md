技能: Sudo Skill
--------------------------

令目标作为施法者激活技能.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| skill | s | 所激活的技能组 | 无 |
| setcasterastrigger | sct | 施法者是否作为所激活技能组的触发者 | false |

示例
-------

实体配置:

    SudoMonkey:
      Type: villager
      Display: 'a Villager'
      Skills:
      - sudoskill{s=sudo;cat=true} @trigger ~onDamaged

技能组配置:

    sudo:
      Skills:
      - arrowvolley{a=20;s=25;v=10;f=50;rd=200} @EIR{r=30}
      - message{msg="触发者名: <trigger.name>"} @world

