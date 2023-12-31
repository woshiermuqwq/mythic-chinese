# 快速起步

SCConflict 是国人开发的一款插件 购买请 +Q: 1360197420, 价格45r 兼容高版本 MythicMobs 与 MMOItems 其功能为实现游戏内常有的元素克制

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

# 初窥门径

## 伤害匹配器

几乎所有由玩家造成的伤害总是包含 Magic 和 Physical 中的至少一个；也总是包含 Unarmed、Weapon、Skill 和 Projectile 中的至少一个。

| 匹配器名 | 匹配规则 |
|------|------|
| Magic | 魔法伤害 |
| Physical | 物理伤害 |
| Unarmed | 空手伤害 |
| Weapon | 武器伤害 |
| Skill | 技能伤害 |
| Projectile | 弹射物伤害 |
| El\_<元素ID> | 匹配一种元素伤害 |
| ANY | 匹配任何伤害 |

## 算法

* 忽略：将所受到的该伤害类型的伤害乘以该数值
* `add 数值`：将所受到的该伤害类型的伤害加上该数值

## 示例配置

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

添加 MMOItems 伤害调整 但变更的伤害调整针对 MMOItems 伤害类型\
若使用该技能创建多个算法为`mt`且对应伤害类型相同的伤害调整, 与[On Damaged](/%E6%8A%80%E8%83%BD/%E5%88%97%E8%A1%A8/ondamaged)一致\
这些伤害调整将以乘法形式叠加

**修改项**:

| 修改项 | 描述 | 默认值 |
|-----|----|-----|
| key | 所创建伤害调整的标识符, 用于在删除伤害调整时选取该伤害调整 | default |
| mt | 算法, `mul`: 乘法; `add`: 加法（详细算法与[上文](/%E5%AE%9E%E4%BD%93/MMOItems%E4%BC%A4%E5%AE%B3%E8%B0%83%E6%95%B4#%E7%AE%97%E6%B3%95)一致） | mul |
| dt | 所创建伤害调整对应的伤害类型 | Physical |
| s | 所创建伤害调整对应的调整数值（与[上文](/%E5%AE%9E%E4%BD%93/MMOItems%E4%BC%A4%E5%AE%B3%E8%B0%83%E6%95%B4#%E7%AE%97%E6%B3%95)一致） | 0.9 |
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
|-----|----|-----|
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

初始减免 90% MMOItems 物理伤害\
但受伤有 10% 几率移除该减伤效果

# 进阶用法

## 复杂伤害匹配器

该版本将伤害匹配器分为简单伤害匹配器与复杂伤害匹配器，在该版本之前的所有你编写的伤害匹配器均为简单伤害匹配器。复杂伤害匹配器通过 &、|、! 三种逻辑运算符连接简单伤害匹配器，可以让你根据多条简单伤害匹配器匹配伤害。

该插件的逻辑运算符在执行上与其他地方有很大部分，类似 `A & B & C` 的复杂伤害匹配器在预处理时会被自动解析哪些是运算符，哪些是简单伤害匹配器。当复杂伤害匹配器触发时，会先计算所有简单伤害匹配器并将所有结果放入结果序列，然后依次触发所有符号，最后更具结果序列中第一个结果判断伤害是否符合复杂伤害匹配器。
- **与运算符&** 删去结果序列的前两个，然后在序列的最前端加入他们的与结果 
- **或运算符|** 删去结果序列的前两个，然后在序列的最前端加入他们的或结果 
- **非运算符!** 将结果序列的第一个反转

因此，简单伤害匹配器与运算符的相对位置其实并不重要，`A & B & C` 与 `A B C & &` 是完全相同的。

```yaml
# 将既是武器伤害又是火元素伤害的伤害降低至 20%
# 将技能伤害和魔法伤害提升至 500%
# 将非冰属性伤害提升至 200%
Reduction:
- 'WEAPON & EL_FIRE 0.2'
- 'SKILL | MAGIC 5'
- '! el_ICE 2'
```

# 开发者

注意：阅读该板块需要您有一定 Java 基础

## 创建简单伤害匹配器

你需要继承 SimpleMatcher 并将这个类注册到 SimpleMatcherManager

除了实现父类的抽象方法以外，你还必须实现以下方法

- `static Boolean is(String key)` 用于快速检测伤害匹配器主键是否属于该类
- `static SimpleMatcher getInst(String key)` 用于实例化伤害匹配器

```mermaid
graph TD
    M{{"Matcher"}} -->|超接口| SM(SimpleMatcher) & CM(ComplexMatcher);
    subgraph LR Manager[SimpleMatcherManager]
        TM(TypeMatcher) & EM(ElementMatcher) & AM(AnyMatcher);
    end
    SM -->|超类| TM & EM & AM;
    TM -->|实例化| Type_P([PhysicalMatcher]) & Type_AndMore([....]);
    EM -->|实例化| El_F([FireMatcher]) & El_AndMore([....]);
    AM -->|实例化| AnyMatcher([AnyMatcher]);
```