复制技能目标的双手槽/护甲槽上的物品并穿戴  
先前的装备将被覆盖   
击杀实体后将掉落所复制装备

## 修改项
| 修改项名 | 缩写 | 描述 | 默认值 |
|------|----|----|-----|
| helmet  h, helm, head | 是否复制头盔 | true |
| chestplate | c, p, chest, plate | 是否复制胸甲 | true |
| leggings | l, legs, leggs, pants | 是否复制护腿 | true |
| boots | b, f, s, feet, shoes | 是否复制靴子 | true |
| mainhand | m, mh, main, hand | 是否复制主手 | true |
| offhand |o, oh, off, secondary | 是否复制副手 | true |

## 示例

```yaml
黑手:
 Skills:
 - skill{s=[
  - copycatEquipment
  - cmd{c="minecraft:clear <target.name>";asop=true}
  ]} @NearestPlayer
```
`/mm t cast 黑手` 后复制并穿戴离自身最近的玩家的装备  
~~随后清除其背包~~