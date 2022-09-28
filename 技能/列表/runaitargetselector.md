技能: Run AI Target Selector
--------------------------

为目标新增一个 最低优先度的AI目标选择器  
使用 `clear` 时将清除已在实体配置内配置好的AI目标选择器器   
使用其它AI目标选择器器之前必须先进行 `clear`  

从 5.0 起, **令实体**清除掉自身的AI目标选择器将令其忘却仇恨目标  
前提是尚未启用[威胁度](/实体/威胁度)

可用AI目标选择器的详细内容见->[点击这儿](/实体/AI)  
从 4.13 起支持付费版AI目标选择器

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| aitargetselector | targetselector, target, string, s | AI目标选择器名 | 无 |

可用AI目标选择器列表
------------------------

-   clear / reset (清除默认AI目标选择器)
-   hurtbytarget / damager / attacker
-   ownerhurttarget / ownertarget
-   monsters
-   players
-   villagers
-   iron_golems / golems
-   otherfaction
-   otherfactionmonsters
-   otherfactionvillagers
-   specificfaction
-   specificfactionmonsters

示例
-------

```yaml
修改AI目标选择器测试:
 Skills:
 - runaitargetselector{target=clear}
 - runaitargetselector{target=players}
 - runaitargetselector{target=monsters}
```
令自身只会以玩家和怪物为仇恨目标

额外信息
--

- [x] 别称: aitarget