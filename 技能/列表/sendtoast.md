技能: Send Toast
--------------------------

发送进度信息给技能目标（玩家）.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| icon      | i       | 进度图标所采用的物品ID | diamond_sword |
| iconnbt   | nbt     | 进度图标所采用的物品的NBT   | 无           |
| message   | msg, m   | 进度描述文本,用""包裹 | 无           |
| frame     | f       | 进度类型,值必须小写,可为: challenge(挑战), task(任务), goal(目标) | challenge      |


示例（实体配置）
--------

```yaml
 Skills:
 - sendtoast{icon=DIAMOND;iconnbt={CustomModelData:1};message="杀死了一个小怪!";frame=challenge} @PlayersInRadius{r=10} ~ondeath
```
施法者死亡后向半径10格方块范围内的玩家发送图标为钻石, 钻石nbt: `CustomModelData` 值为1, 成就消息为 `杀死了一个小怪!` 的成就

额外信息
--

- [x] 别称: advancementmessage, advmessage, toastmessage, toastmsg