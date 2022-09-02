##

SCConflict 是国人开发的一款插件  
兼容高版本 MythicMobs 与 MMOI
tems  
其功能为实现游戏内常有的元素克制

查询伤害调整
---

`/scc check`: 使执行者进入或退出查看模式，在查看模式右键任何Mythic实体都会显示其所有的伤害调整

格式
---

格式与伤害调整极为相似  
在此处定义的伤害调整的标识符为 `config`
```yaml
测试实体:
 Type: 任意实体种类
 Display: ...
 Reduction:
 - MMOItems伤害类型 算法 数值
 - MMOItems伤害类型 算法 数值
 - ...
```

算法
---

* 忽略: 将所受到的该伤害类型的伤害乘以该数值
* `add 数值`: 将所受到的该伤害类型的伤害加上该数值

示例
---

```yaml
测试实体:
 Type: ZOMBIE
 Display: '测试实体'
 Reduction:
 - Physical 0.2
 - Magic 5
```
这只僵尸将减免80%物理伤害, 但会额外受到4倍魔法伤害
```yaml
测试实体:
 Type: ZOMBIE
 Display: '测试实体'
 Reduction:
 - Magic add 5
```
这只僵尸将在受到魔法伤害时额外受到5点伤害

### 相关技能

#### addDynamicModifier（adm）

添加MMOItems伤害调整
但变更的伤害调整针对MMOItems伤害类型  
若使用该技能创建多个算法为`mt`且对应伤害类型相同的伤害调整, 与[On Damaged](/技能/列表/ondamaged)一致  
这些伤害调整将以乘法形式叠加

**修改项**:

| 修改项 | 描述 | 默认值 |
| - | - | - |
| key | 所创建伤害调整的标识符, 用于在删除伤害调整时选取该伤害调整 | default |
| mt | 算法, `mul`: 乘法; `add`: 加法（详细算法与[上文](/实体/MMOItems伤害调整#算法)一致） | mul |
| dt | 所创建伤害调整对应的伤害类型 | Physical |
| s | 所创建伤害调整对应的调整数值（与[上文](/实体/MMOItems伤害调整#算法)一致） | 0.9 |
| d | 所创建伤害调整的持续时间（秒） | 无限制 |

```yaml
测试:
 Type: ZOMBIE
 Display: '物防僵尸'
 Health: 40
 Damage: 10
 Skills:
 - adm{dt=Physical;mt=mul;s=0.9;d=200;delay=100} @self ~onSpawn
```
生成10秒后, 在200秒内减免10% MMOItems物理伤害


#### delDynamicModifier（ddm）

移除MMOItems伤害调整

**修改项**:

| 修改项 | 描述 | 默认值 |
| - | - | - |
| key | 所移除伤害调整的标识符 | default |
| num | 若有多个符合该标识符的伤害调整, 则移除多少个 | 1 |
| reverse | 是否倒序查找符合的标识符<br>若为否则可理解为移除最早获得的, 标识符符合的伤害调整 | false |

```yaml
测试:
 Type: ZOMBIE
 Display: '物防僵尸'
 Health: 40
 Damage: 10
 Skills:
 - adm{key=dzf;dt=Physical;mt=mul;s=0.1} @self ~onSpawn
 - ddm{key=dzf} @self ~onDamaged 0.1
 ```
生成10秒后永久减免90% MMOItems物理伤害  
但受伤有10%几率移除该减伤效果