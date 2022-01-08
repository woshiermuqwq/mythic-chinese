技能: Run AI Target Selector
--------------------------

为目标新增一个 最低优先度的AI目标选择器.

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

    修改AI目标选择器测试:
      Skills:
      - runaitargetselector{target=clear}
      - runaitargetselector{target=players}
      - runaitargetselector{target=monsters}

额外信息
--

- [x] 别称: aitarget