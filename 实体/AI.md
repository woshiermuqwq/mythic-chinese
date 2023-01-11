此页面将列出所有可用的AI行动器与AI目标选择器

---

**AI行动器**
---
AI行动器将决定实体该做什么. 若所写AI行动器不适用于实体, 那么它可能没有效果.  
如给实体种类为僵尸的Mythic实体写上"EatGrass(啃草)"是没有任何作用的.  

无法修改鱿鱼、史莱姆、蝙蝠、幻翼、末影龙、蜜蜂、猪灵（包括暴君）、恶魂、恼鬼的AI.

有攻击性质的行动器（如 meleeattack）在被动生物（如 鸡）上无法正常工作.（原因: 缺少attack_damage属性NBT）  
高版本被动实体虽然可使用攻击性质的AI行动器, 但需要定义 `Damage: 数值` 一项

与阵营相关的AI行动器, 若玩家为OP则仍然会将玩家当作 "指定阵营或其它阵营" 内的实体

例子:

```yml
超级实体:
  Type: zombie
  Health: 200
  Display: '非凡的 僵尸'
  AIGoalSelectors:
  - clear
  - meleeattack
  - randomstroll
```

这只僵尸会近距离攻击目标,无目标时会随机走动.

**所有实体可用**

| AI行动器名                       | 别称             | 描述                   |
| -------------------------------- | ---------------- | ---------------------- |
| clear                            | reset            | 清除默认(原版)AI行动器<br>**并防止生物朝向发生变动** |
| breakdoors                       |                  | 破坏路线上的门         |
| eatgrass                         |                  | 啃草                   |
| float                            | swim             | 漂浮在水上             |
| lookatplayers                    |                  | 看向玩家               |
| opendoors                        | opendoor         | 开启路径上的门         |
| closedoors                       | restrictopendoor | 关闭路径上的门         |
| randomlookaround                 | lookaround       | 看向周围               |
| gotospawnlocation{maxrange(max, r)=寻找的最大距离（格方块）;minrange(min, mr)=与出生点所保持的距离（格方块）;speed=移速;droptarget(dt)=是否无视当前目标走向出生点}                 | gotospawn        | 走向实体的出生点       |
| doNothing{fleeconditions=[  - 条件 条件活动 ]}       **[仅限付费版]** | nothing{conditions(cond, c)=[  条件 ]} | 条件不满足就不进行操作 |

**生物可用**

flee开头的AI行动器共有的修改项:

| 修改项名 | 描述 | 默认值 |
| - | - | - |
| distance | 远离距离 | 5 |
| speed | 逃离速度 | 2 |
| safespeed=2 | 即将达到远离距离时的逃离速度 | 1 |

| AI行动器名                          | 别称             | 描述                                   |
| ----------------------------------- | ---------------- | -------------------------------------- |
| avoidcreepers                       |                  | 躲避爬行者                             |
| avoidskeletons                      |                  | 躲避骷髅                               |
| avoidzombies                        |                  | 躲避僵尸                               |
| fleesun                             |                  | 躲避日光                               |
| meleeattack                         |                  | 近距离攻击方式                         |
| movetowardstarget                   |                  | 走向目标                               |
| movetowater（5.2.1）  | | 走向水源 |
| movetolava（5.2.1）  | | 走向熔岩 |
| moveblock{material=方块id;radius=水平检索半径;radiusy=垂直检索半径;speed=移动速度}                   |                  | 走向特定方块（5.2.1）                               |
| randomstroll                        |                  | 随机走动                               |
| restrictsun                         |                  | 躲避高亮度地区                         |
| fleeplayers                         | runfromplayers   | 躲避玩家                               |
| fleegolems                          | runfromgolems    | 躲避铁傀儡                             |
| fleevillagers                       | runfromvillagers | 躲避村民                               |
| fleewolves                          | runfromwolves    | 躲避狼                                 |
| fleefaction{f=阵营名}（5.2.1） | | 躲避处在指定阵营内的实体（可作用于玩家） |
| fleeConditional{conditions=} **[仅限付费版]** | fleeIf           | 躲避符合条件的实体.    |
| spiderattack                        |                  | 跳跃攻击方式(如狼、蜘蛛)               |
| leapattarget                        |                  | 朝目标冲刺                             |
| moveindoors                         |                  | 室内活动                               |
| movethroughvillage                  |                  | 村庄内活动                             |
| movetowardsrestriction              |                  | 未知                                   |
| patrol x1,y1,z1;x2,y2,z2;x3,y3,z3;… | patrolroute      | 依次走到多个坐标点路程需≤实体跟随距离) |
| gotolocation x,y,z                  | goto             | 走到指定坐标点(路程需≤实体跟随距离)    |
| gotoowner{followrange(fr, r, maxrange)=跟随距离（格方块）;minrange(mr)=与主人所保持的距离（格方块）;speed=移速;droptarget(dt)=是否无视当前目标走向主人}                         |                  | 走向主人(路程≤实体跟随距离)      |
| gotoparent{followrange(fr, r, maxrange)=跟随距离（格方块）;minrange(mr)=与父系实体所保持的距离（格方块）;speed=移速;droptarget(dt)=是否无视当前目标走向父系实体}                         |                  | 走向父系实体(路程≤实体跟随距离)      |
| gotoparent                          |                  | 走向父系实体(路程≤实体跟随距离)        |
| gotowater（5.0.5） | | 寻找并进入水源 |
| panicWhenOnFire                     | panic            | 着火时寻找水源熄火 |
| randomFly | | 随机飞行 |

FleeConditional 示例:
```yml
AIGoalSelectors:
- clear
- fleeConditional{distance=5;speed=2;safespeed=2;conditions=[ - inlineofsight true ]}
    ]}
```

**动物可用 (5.0.3)**

| AI行动器名        | 别称                    | 描述         |
| ----------------- | ----------------------- | ------------ |
| breed | | 走向繁殖对象 |

**远程攻击方式实体可用**

对近身攻击方式的实体使用将报错, 如僵尸

| AI行动器名        | 别称                    | 描述         |
| ----------------- | ----------------------- | ------------ |
| arrowattack{speed=移速;attackspeedmax=最快射速;attackspeedmin=最慢射速;attackradius=寻敌半径范围}       |                         | 无需拉弓射箭（实体必须可拉弓） |
| skeletonbowattack{speed=移速;attackspeedmin=最慢射速;attackradius=寻敌半径范围} | bowshoot, bowmaster     | 拉弓射箭（实体必须可拉弓）     |

**猪灵与掠夺者可用**

| AI行动器名     | 别称 | 描述     |
| -------------- | ---- | -------- |
| crossbowAttack{speed=移速;attackradius=寻敌半径范围} |      | 拉弩射箭 |

**爬行者可用**

| AI行动器名     | 别称 | 描述     |
| -------------- | ---- | -------- |
| creeperswell（4.14.2） | creeperexplode | 爬行者膨胀后爆炸 |

**AI目标选择器**
---
AI目标选择器(不同于技能的目标选择器)将决定实体选择什么样的实体为目标  
从 MM 4.14.0 开始, 若实体的AI目标选择器被清除(clear), 实体将忘却自己先前的目标, 从而停止攻击

例子:

```yml
超级实体:
  Type: zombie
  Health: 200
  Display: '非凡的 僵尸'
  AIGoalSelectors:
  - meleeattack
  - randomstroll
  AITargetSelectors:
  - clear
  - players
  - golems
```

这只僵尸仅会选取玩家和铁傀儡为目标(因已清除默认AI目标选择器所以不会像原版一样即使被骷髅之类的误伤也不会还击)

**所有实体可用**

| AI目标选择器名                            | 别称                          | 描述                                               |
| ----------------------------------------- | ----------------------------- | -------------------------------------------------- |
| clear                                     |                               | 清除默认(原版)                                     |
| attacker                                  | hurtbytarget, damager         | 选取对自身造成伤害（未令实体变红不算造成伤害）的实体                           |
| monsters                                  |                               | 选取原版实体种类为怪物的实体(包括原版)             |
| players                                   |                               | 选取玩家                                           |
| villagers                                 |                               | 选取原版实体种类为村民的实体(包括原版).            |
| golems                                    |                               | 选取原版实体种类为傀儡(包括雪傀儡)的实体(包括原版) |
| nearestConditionalTarget **[仅限付费版]** | nearestConditional, nearestIf | 选取离自身最近的符合条件的实体                     |

NearestConditionalTarget 示例:
```yml
AITargetSelectors:
- clear
- nearestConditionalTarget{conditions=[
      - entitytype PLAYER true
      - hasaura{aura=marked_for_death} true
    ]}
```

**拥有阵营的实体可用**

| AI目标选择器名                 | 描述                                      |
| ------------------------------ | ----------------------------------------- |
| OtherFaction                   | 选取其它阵营内的所有实体为目标            |
| OtherFactionMonsters           | 选取其它阵营内实体种类为怪物的实体为目标  |
| OtherFactionVillagers          |  选取其它阵营内实体种类为村民的实体为目标 |
| SpecificFaction 阵营名         | 选取指定阵营内的所哟IU实体为目标          |
| SpecificFactionMonsters 阵营名 | 选取指定阵营内实体种类为怪物的实体为目标  |

示例:

```yml
AITargetSelectors:
- SpecificFaction 亡灵
```

选取亡灵阵营内的所有实体为目标

**已驯服实体可用**

| AI目标选择器名       | 描述    |
| ------------- | -------------- |
| ownerattacker | 攻击主人的实体 |
| ownertarget   | 主人的目标     |