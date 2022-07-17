**描述:** 若技能目标与施法者之间存在视觉障碍物  
所谓视觉障碍物就是不管你朝什么方向都没法看到技能目标  

示例（需Crucible 最新付费版MM）
---

手持该钻石剑左键后传送至16格方块内离自身最近的实体
```yaml
测试:
 Id: diamond_sword
 Skills:
 - teleport @eir{r=16;limit=1;sort=nearest;conditions=[  - lineofsigt ]} ~onswing
```
手持该钻石剑左键后传送至16格方块内离自身最近, 且在视野正前方的实体（无需付费版）:
```yaml
测试:
 Id: diamond_sword
 Skills:
 - skill:传送 @eir{r=16;limit=1;sort=nearest} ~onswing

### 技能文档

传送:
 TargetConditions:
 - lineofsight
 - fov{a=60}
 Skills:
 - teleport
```

拓展信息
---

- 检测对象: 实体与施法者(比较)
- 别称: inlineofsight