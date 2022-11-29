技能: Set Varibale (4.6)
--------------------------

创建变量(若存在则替换值).

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| variable | name, n, var, key, k | 所设置变量的名称 | 无 |
| scope | s | 所设置变量的[变量类型](技能/变量#变量类型) | skill |
| type | t | 所设置变量的[变量值类型](技能/变量#变量种类) | INTEGER |
| value | v | 所设置变量的变量值,必须用""包裹 | 无 |
| save | 无 | 所设置变量是否在重载后仍然存在（不支持种类为Skill的变量） | false |
| durationn | d, expire, e | 所设置变量最大持续时间(刻) | 无限制 |

示例
--------

此实体每3秒会对半径40格范围内的所有玩家使用测试变量条件技能:

    测试变量条件实体:
      Skills:
      - skill:测试变量条件技能 @PlayersInRadius{r=40} ~onTimer:60

但玩家必须不拥有变量: 某变量 或变量值不为 是 才能被下方俩技能所影响:

    测试变量条件技能:
      TargetConditions:
      - variableEquals{var=target.某变量;value="yes"} false
      Skills:
      - message{m="&7你没有指定变量,这就为你添上"}
      - setvariable{var=target.某变量;value="yes";duration=6000}

若没有变量值为 是 的 某变量 ,才能被发送聊天栏信息,以及设置持续时间为5分钟,变量值为 是 的 某变量.

将PlaceHolderAPI变量值传递到 类型为数值或浮点型 的变量中  
且对目标造成 当前技能伤害数值(MMOItems) 的一百倍伤害(因为被传递变量的值就是当前技能伤害数值).

    PlaceHolderAPI传递变量值:
      Skills:
      - setvariable{var=caster.被传递变量;value="%mmoitems_stat_skill_damage%";type=INTEGER} @self
      - damage{a="100 * <caster.var.被传递变量>"} @PIR{r=5}

将其它变量值传递到 类型为数值或浮点型 的变量中 与 将施法者身上的变量复制到目标身上:
    
    变量传递:
      Skills:
      - setvariable{var=caster.变量A;value="%mmoitems_stat_skill_damage%";type=INTEGER} @self
      - setvariable{var=caster.变量B;value="<caster.var.变量A> * 2";type=INTEGER} @self
      - setvariable{var=caster.变量C;value="<caster.var.变量A> + <caster.var.变量B>";type=INTEGER} @self
      - setvariable{var=target.变量C;value="<caster.var.变量C>";type=INTEGER} @target

将变量A的值设为 当前技能伤害数值(MMOItems) 的值  
将变量B的值设为 变量A的值的俩倍  
将变量C的值设为 变量A的值+变量B的值  
将自身当前目标身上的变量C设为 施法者身上的变量C的值.

关于 Value
----------

SetVaribale内的修改项: Value, 若写入了占位符  
将在 技能目标身上 读取占位符的值  
而不是只能读取位于 施法者身上 的占位符  
一些占位符内存在"{}"等, 会被读取为算术表达式  
这是个漏洞, 如%objective_score_{记分板_名称}%

额外信息
-------

- **支持** [占位符](/技能/占位符)与[变量](/技能/变量)（修改项: Value 需 ≥4.10）
- 缩写: setvar