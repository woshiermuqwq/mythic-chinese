**描述:** 若技能目标与坐标原点之间存在视觉障碍物.  
所谓视觉障碍物就是不管你朝什么方向都没法看到技能目标  

新增于 MM 4.14

示例
---

每5秒发射一发抛射物  
抛射物将不断拉拢与抛射物位置之间不存在视觉障碍物的 在10格方块范围内的全部实体
```yaml
测试实体:
 Type: husk
 Skills:
 - p{ot=[  - e:p - pull{} @eno{r=10;conditions=[  - lineofsightfromorigin ]} ];se=false;sb=false;md=100} @forward{pitch=0;f=999} ~onTimer:100
```

拓展信息
---

- 检测对象: 技能目标与坐标原点(比较)
- 别称: inlineofsight