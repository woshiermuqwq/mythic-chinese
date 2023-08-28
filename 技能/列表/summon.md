技能: Summon
--------------------------

在技能目标位置生成实体.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| type               | t       | 用于生成的实体ID,可为MythicMobs实体名 | SKELETON      |
| amount             | a       | 生成实体数量　（支持[占位符](/技能/占位符)）                                             | 1             |
| level              | l       | 所生成的实体的等级　（支持[占位符](/技能/占位符)）                                                     | 0             |
| radius             | r       | 生成水平范围　（支持[占位符](/技能/占位符)）                    | 0             |
| yRadius            | yr      | 生成垂直范围　（支持[占位符](/技能/占位符)）                                                          | 等值于生成水平范围        |
| yRadiusUpOnly      | yu      | 是否过滤球体范围的下半部分 | true |
| onSurface          | os      | 是否仅生成于固体方块上                                                                        | true          |
| copyThreatTable    | ctt     | 所生成实体是否继承其它实体对施法者的威胁 | false         |
| inheritThreatTable | itt     | 所生成实体是否与施法者共享其它实体对于它的威胁度 | 无 |
| inheritFaction     | if      | 所生成实体是否与施法者处在同一阵营                                                                        | false |
| summonerIsOwner | sio | 施法者是否作为所生成实体的主人 | true |
| summonerIsParent | sip | 施法者是否作为所生成实体的父系实体 | true |

示例
--------

```yaml
生成技能测试:
 Skills:
 - summon{type=WITHER_SKELETON;amount=5;radius=4} @PIR{r=20}
```
在半径20格方块范围内 以每个玩家位置为中心 在半径4格方块范围内生成5个凋零骷髅.

```yaml
### 技能配置
紫荆花传送:
 Skills:
 - summon{type=传送点;amount=1;radius=32;yu=true} @origin
### 实体配置
传送点:
 Type: armor_stand
 Options:
  Invisible: true
  Marker: true
  HasGravity: false
  Despawn: chunk #4.13及以上
  #Despawn: false #4.12及以下保留此行删除上一行, 默认将其忽略
 Skills:
 - skill{s=[
  - forcepull{delay=1;sync=true}
  - remove @self
  ]} @parent ~onspawn
```
通过MM实现原版的紫荆花传送效果

额外信息
-------

**部分修改项支持** [占位符](/技能/占位符)（已列出）