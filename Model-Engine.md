### Model Engine（模型引擎）
**Model Engine 是一个付费插件: [SpigotMC页面](https://www.spigotmc.org/resources/conxeptworks-model-engine%E2%80%94ultimate-entity-model-manager-1-14-1-16-5.79477/) 以及它需要资源包才可以工作.  
[点我前往 Model Engine 的最新百科](https://github.com/Ticxo/Model-Engine-Wiki).  
[点我加入 Discord 频道](https://discord.gg/vbdyuac) 加入频道以咨询问题**

*Model Engine 可以免费试用一些模型, 所以你可以在购买之前进行尝试, 在百科上有一个免费的测试模型. *

### Model Engine 工作原理

Model Engine 主要使用盔甲架去显示模型, 其次是资源包.  
模型的每个部位都是一个盔甲架, 所以这其实很占用资源.

下方是一个效果示例

![https://i.ibb.co/99zsNby/9month1.gif](https://i.ibb.co/99zsNby/9month1.gif)

### 技能

使用 "kindletronjr" 以为实体套上模型:  
`- model{mid=kindletronjr;n=false} @self ~onSpawn`  
当实体攻击时使用一个"模型阶段"以做到攻击动画的效果:  
`- state{mid=kindletronjr;s=attack;3} @self ~onAttack`

更多属性和技能请见:
https://github.com/Ticxo/Model-Engine-Wiki/wiki/Mechanics

### 示例:

```yml
模型示例:
 Type: SILVERFISH
 Health: 20
 Damage: 0
 Skills:
 - model{mid=kindletronjr} ~onSpawn
 - skill{s=KindletronJRInit;sync=true} @self ~onAttack
 Options:
  Silent: true
  MovementSpeed: 0.1
  MaxCombatDistance: 25
  PreventOtherDrops: true
  PreventBlockInfection: true
```