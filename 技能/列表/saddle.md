技能: Saddle（5.3.0）
---

为技能目标穿戴/摘下鞍（不会消耗/返还物品）

示例
---

```yaml
测试猪:
 Type: pig
 Skills:
 - saddle ~onspawn
 - saddle @self ~ondamaged
```
出生后装备鞍（与[实体选项: Saddled=true](/实体/选项)效果一致）  
受伤后移除鞍

拓展信息
---

- 别称: givesaddle, setsaddle