特效技能: Sound
--------------------------

于技能目标位置播放指定音效的指定种类.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| sound            | s     | 用于播放的音效（支持[占位符](/技能/占位符)） | entity.zombie.attack_iron_door |
| pitch            | p     | 音高,数值在0.01~2之间（支持[占位符](/技能/占位符)）  | 1.0            |
| volume           | v     | 音效响度(可被离音源所写值*16格方块远的实体所听见) | 1.0            |
| soundcategory    | sc    | 音效种类 | 无     |

示例
--------

```yaml
 Skills:
 - sound{s=entity.enderman.scream} @self
```

关于使用非原版音效
-----

见-> [点我](https://www.bilibili.com/read/cv7852806)

```yaml
测试:
 Type: husk
 Options:
  NoAI: true
  Silent: true
 Disguise: player sharrk_kunjang
 Skills:
 - s{s=mua.shark} @self ~oninteract
 - s{s=slap.shark} @self ~ondamaged
 - s{s=slap.shark} @self ~ondamaged
 - s{s=slap.shark} @self ~ondamaged
 - s{s=slap.shark} @self ~ondamaged
 - s{s=slap.shark} @self ~ondamaged
```
装了我专栏内的资源包的玩家  
左键可以听到拍打音效, 右键则会收到"诶"音效

额外信息
------

- **支持** Audience
- 别称: effect:sound, s, e:sound, e:s