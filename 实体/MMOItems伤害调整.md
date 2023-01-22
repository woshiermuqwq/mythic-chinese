##
SCConflict 是国人开发的一款插件

购买请 +Q: 1360197420, 价格45r

兼容高版本 MythicMobs 与 MMOItems

其功能为实现游戏内常有的元素克制

## 插件命令

`/scc check` 使执行者进入或退出查看模式，在查看模式下右键任何实体都会显示其所有的伤害调整（包含已过期的伤害调整以及未过期伤害调整的剩余时间）。

## 基本格式

只需参考下面的配置语法，在怪物根节点下的 `Reduction` 字段下进行配置，就可以非常轻松的为怪物设置默认伤害调整。

注：在此处定义的伤害调整的标识符为 `config`

```yaml
测试实体:
  Type: 任意实体种类
  Display: ...
  Reduction:
  - 伤害匹配器 算法 数值
  - 伤害匹配器 算法 数值
  - ...
```

## 伤害匹配器

几乎所有由玩家造成的伤害总是包含 Magic 和 Physical 中的至少一个；也总是包含 Unarmed、Weapon、Skill 和 Projectile 中的至少一个。

| 匹配器名    | 匹配规则         |
| ----------- | ---------------- |
| Magic       | 魔法伤害         |
| Physical    | 物理伤害         |
| Unarmed     | 空手伤害         |
| Weapon      | 武器伤害         |
| Skill       | 技能伤害         |
| Projectile  | 弹射物伤害       |
| El_<元素ID> | 匹配一种元素伤害 |
| ANY         | 匹配任何伤害     |

### 算法

* 忽略：将所受到的该伤害类型的伤害乘以该数值
* `add 数值`：将所受到的该伤害类型的伤害加上该数值

### 示例配置

```yaml
# 这只僵尸将减免 80% 物理伤害
# 但会额外受到 4 倍魔法伤害
坚硬盔甲僵尸:
  Type: ZOMBIE
  Display: '坚硬盔甲僵尸'
  Reduction:
  - Physical 0.2
  - Magic 5
```

```yaml
# 这只僵尸免疫一切非魔法伤害
# 并将魔法伤害降低至 5 点
魔导师:
 Type: ZOMBIE
 Display: '魔导师'
 Reduction:
 - ANY 0
 - Magic add 5
```

```yaml
# 这只僵尸受到的火元素伤害会降低至十分之一
# 但会受到十倍的冰元素伤害
岩浆僵尸:
  Type: ZOMBIE
  Display: '岩浆僵尸'
  Reduction:
  - el_FIRE 0.1
  - el_ICE 10
```



## 相关技能

### addDynamicModifier（adm）

添加 MMOItems 伤害调整
但变更的伤害调整针对 MMOItems 伤害类型  
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
生成的 10 秒后, 在 200 秒内减免 10% MMOItems 物理伤害


### delDynamicModifier（ddm）

移除 MMOItems 伤害调整

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
 - adm{key=dzf;mt=mul;s=0.1} @self ~onSpawn
 - ddm{key=dzf} @self ~onDamaged 0.1
 ```
初始减免 90% MMOItems 物理伤害  
但受伤有 10% 几率移除该减伤效果