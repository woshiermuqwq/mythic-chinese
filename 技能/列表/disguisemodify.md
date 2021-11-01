技能: Disguise
--------------------------

修改目标的伪装.

此技能的修改项可以缩写为一行包含着伪装种类与伪装选项的字符串.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| disguise  | d, type, t | 伪装内容,包含"setCustomName"选项时不可写入双引号 | Player Ashijin |

示例
--------

```
伪装测试:
  Skills:
  - disguise{d=Sheep SetBurning SetSpinning SetCustomNameVisible setCustomName Zombie} @self
```
```
伪装测试:
  Skills:
  - disguise{d="Zombie setYModifier -1.5 setPitchLocked setInvisible setHelmet PLAYER_HEAD"} @self
```
```
伪装测试:
  Skills:
  - disguise{d=PLAYER Sharrk_kunjang setDisguiseName 鲨鲨} @self
```

拓展信息
--------

- [x] 支持 Audience