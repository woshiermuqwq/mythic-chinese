通用修改项: Delay
--------------------------

作为一个修改项: delay=延迟刻数 令使用了该修改项的技能行在指定刻数之后激活.

或作为一行技能: 延迟一段时间(刻)后激活技能组内位于Delay所处行下方的技能.

独立作为一行技能时: 多行Delay值将叠加.

作为技能修改项时: 每个Delay都是独立计算的.

从 MM 4.14.0 起, 支持[占位符](/占位符)

示例 (作为技能行)
--------

      Skills:
      - message{m="瞬间激活的技能行"} @EIR{r=16}
      - delay 10
      - message{m="延迟0.5秒(10刻)激活的技能行"} @EIR{r=16}
      - delay 10
      - message{m="延迟1秒(10刻)激活的技能行"} @EIR{r=16}

示例 (作为技能修改项)
--------

      Skills:
      - message{m="瞬间激活的技能行";delay=0} @EIR{r=16}
      - message{m="延迟0.5秒(10刻)激活的技能行";delay=10} @EIR{r=16}
      - message{m="延迟2秒(40刻)激活的技能行";delay=40} @EIR{r=16}

高版本特性
---

当 delay 值为 0 时, 理论上应该跟没有延迟一样, 但当你为延迟后的技能行添加延迟就会发现...  
它达到了`delay=0.几`的效果, 具体原理未知
```yaml
三叉戟:
 Id: trident
 Skills:

 - skill{s=[
  - delay 0
  - remove @eir{r=16;living=false;limit=1;sort=nearest}
  ]} ~ontrident_throw
···
就拿上面做例子, 如果没有`- delay 0`, 你是无法在投掷三叉戟的一瞬间选取所投掷的三叉戟的  
当你把 `@eir{r=16;living=false;limit=1;sort=nearest}` 移动到 ` ~ontrident_throw` 的左边时  
也无法选取, 这就说明延迟前后的选取的实体不同, 延迟明明是0, 实际却是有特别小的延迟, 足以提升机制自由度