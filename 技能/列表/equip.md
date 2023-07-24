技能: Equip 
--------------------------

穿戴物品（可为原版物品 与 Mythic物品）.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| item | i | 物品名（可为Mythic物品）, 物品名后接":槽位数字"<br>物品与槽位为一个整体<br>多个整体使用","隔开<br>从 MM 5.3 起, ":槽位数字" 可用"(空格)槽位名称"替代 | 无 |

示例 (实体配置 需开启[威胁度](/实体/威胁度))
--------

```yaml
 Skills:
 - equip{i=diamond_sword:0,diamond_helmet:4} @self ~onEnterCombat
 - equip{i=stick:0} @self ~onDropCombat
```
进入战斗后手持钻石剑, 头戴钻石头盔, 结束战斗后手持木剑.

写法2:  
```yaml
 Skills:
 - equip{i=diamond_sword hand,diamond_helmet helmet} @self ~onEnterCombat
 - equip{i=stick hand} @self ~onDropCombat
```
