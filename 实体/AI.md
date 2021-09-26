此页面将列出所有可用的AI行动器与AI目标选择器

---

**AI行动器**
---
AI行动器将决定实体该做什么. 如果所写AI行动器不适用于实体,那么它可能没有效果,如给实体种类为僵尸的MythicMobs
实体写上"EatGrass(啃草)"是没有任何作用的.  
有攻击性质的（如 meleeattack）在被动生物（如 鸡）上无法正常工作.  

与阵营相关的AI行动器, 若玩家为OP则仍然会将玩家当作 "指定阵营或其它阵营" 内的实体

例子:

```
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
| clear                            | reset            | 清除默认(原版)AI行动器 |
| breakdoors                       |                  | 破坏路线上的门         |
| eatgrass                         |                  | 啃草                   |
| float                            | swim             | 漂浮在水上             |
| lookatplayers                    |                  | 看向玩家               |
| opendoors                        | opendoor         | 开启路径上的门         |
| closedoors                       | restrictopendoor | 关闭路径上的门         |
| randomlookaround                 | lookaround       | 看向周围               |
| gotospawnlocation                | gotospawn        | 走向实体的出生点       |
| fleeConditional **[仅限付费版]** | fleeIf           | 躲避符合条件的实体.    |
| doNothing       **[仅限付费版]** |                  | 条件不满足就不进行操作 |

FleeConditional 示例:
```
AIGoalSelectors:
- clear
- fleeConditional{distance=5;speed=2;safespeed=2;conditions=[ - inlineofsight true ]}
    ]}
```

**生物可用**

| AI行动器名                          | 别称             | 描述                                   |
| ----------------------------------- | ---------------- | -------------------------------------- |
| avoidcreepers                       |                  | 躲避爬行者                             |
| avoidskeletons                      |                  | 躲避骷髅                               |
| avoidzombies                        |                  | 躲避僵尸                               |
| fleesun                             |                  | 躲避日光                               |
| meleeattack                         |                  | 近距离攻击方式                         |
| movetowardstarget                   |                  | 走向目标                               |
| randomstroll                        |                  | 随机走动                               |
| restrictsun                         |                  | 躲避高亮度地区                         |
| fleeplayers                         | runfromplayers   | 躲避玩家                               |
| fleegolems                          | runfromgolems    | 躲避铁傀儡                             |
| fleevillagers                       | runfromvillagers | 躲避村民                               |
| fleewolves                          | runfromwolves    | 躲避狼                                 |
| spiderattack                        |                  | 跳跃攻击方式(如狼、蜘蛛)               |
| leapattarget                        |                  | 朝目标冲刺                             |
| moveindoors                         |                  | 室内活动                               |
| movethroughvillage                  |                  | 村庄内活动                             |
| movetowardsrestriction              |                  | 未知                                   |
| patrol x1,y1,z1;x2,y2,z2;x3,y3,z3;… | patrolroute      | 依次走到多个坐标点路程需≤实体跟随距离) |
| gotolocation x,y,z                  | goto             | 走到指定坐标点(路程需≤实体跟随距离)    |
| gotoowner #                         |                  | 走向主人路程需(路程≤实体跟随距离)      |
| gotoparent                          |                  | 走向父系实体(路程≤实体跟随距离)        |
| panicWhenOnFire                     | panic            | 着火时寻找水源熄火 |

**远程攻击方式实体可用**

| AI行动器名        | 别称                    | 描述         |
| ----------------- | ----------------------- | ------------ |
| arrowattack       |                         | 无需拉弓射箭 |
| skeletonbowattack | bowshoot, bowmaster     | 拉弓射箭     |

**猪灵与掠夺者可用**

| AI行动器名     | 别称 | 描述     |
| -------------- | ---- | -------- |
| crossbowAttack |      | 拉弩射箭 |

**AI目标选择器**
---
AI目标选择器(不同于技能的目标选择器)将决定实体选择什么样的实体为目标

例子:

```
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
| attacker                                  | hurtbytarget, damager         | 选取对自身造成伤害的实体                           |
| monsters                                  |                               | 选取原版实体种类为怪物的实体(包括原版)             |
| players                                   |                               | 选取玩家                                           |
| villagers                                 |                               | 选取原版实体种类为村民的实体(包括原版).            |
| golems                                    |                               | 选取原版实体种类为傀儡(包括雪傀儡)的实体(包括原版) |
| nearestConditionalTarget **[仅限付费版]** | nearestConditional, nearestIf | 选取离自身最近的符合条件的实体                     |

NearestConditionalTarget 示例:
```
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

```
AITargetSelectors:
- SpecificFaction 亡灵
```

选取亡灵阵营内的所有实体为目标

**已驯服实体可用**

| AI目标选择器名       | 描述    |
| ------------- | -------------- |
| ownerattacker | 攻击主人的实体 |
| ownertarget   | 主人的目标     |