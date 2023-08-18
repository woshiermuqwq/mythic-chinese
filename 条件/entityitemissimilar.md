**描述:** 若技能目标（掉落物实体）与被比较的物品相似（包括堆叠数量等）.

当物品为原版物品时, 条件仅检测物品ID  
当物品为Mythic物品时, 条件仅检测物品ID与物品内部名  

---

修改项
---

| 修改项名  | 别称           | 描述                      | 默认值 |
| --------- | -------------- | ------------------------- | --- |
| item | i, material, m, mm, mythicitem | 用于检测的物品, 支持Mythic物品 | 无 |

新增于 MM 4.14.0

示例
---

```yaml
### 物品配置
测试物品:
  Id: diamond
  Display: '123'
  Lore:
  - '1'
### 技能配置
测试:
 Skills:
 - skill:123 @ino{r=5}
123:
 TargetConditions:
 - entityitemissimilar{i=测试物品}
 Skills:
 - skill:test @targeted{limit=1}
test:
 Conditions:
 - targets
 Skills:
 - remove
```
当执行`/mm t cast 测试`技能后, 移除5格半径范围内的 与Mythic物品: 测试物品相似的 掉落物实体  
即使将该Mythic物品的显示名与描述移除, 该掉落物仍会被移除

拓展信息
---

- 检测对象: 实体