**描述:** 若实体的[实体等级](/实体/等级)在指定数值范围内.

修改项
---

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| level     | l     | 用于检测的等级范围或具体值 |

示例
---

```yaml
### 实体配置

测试实体:
 Type: husk
 Skills:
 - skill:等级掉落 @trigger ~ondeath

### 技能组配置

等级掉落:
 Conditions:
 - level{l=>20} castinstead 掉钻石
 - level{l=>10} castinstead 掉金子
 Skills:
 - dropitem{i=iron_ingot}
掉钻石:
 Skills:
 - droppitem{i=diamond}
掉金子:
 Skills:
 - dropitem{i=gold_ingot}
```
若实体等级低于10则掉铁锭  
高于10则掉铁+金锭, 高于20则掉铁+金锭+钻石

拓展信息
---

- 检测对象: 实体