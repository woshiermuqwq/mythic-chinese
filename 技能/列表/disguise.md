技能: Disguise
--------------------------

令自身伪装.

此技能的修改项可以缩写为一行包含着伪装种类与伪装选项的字符串.

若MM版本在4.12以下, 请使用技能: [Disguise Old](技能/列表/disguiseold)

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| disguise  | d, type, t | 伪装内容,包含"setCustomName"选项时不可写入双引号 | Player Ashijin |

新增于 MM 4.12

示例
--------

```yaml
伪装测试:
  Skills:
  - disguise{d=Sheep SetBurning SetSpinning SetCustomNameVisible setCustomName Zombie} @self
```
```yaml
伪装测试:
  Skills:
  - disguise{d="Zombie setYModifier -1.5 setPitchLocked setInvisible setHelmet PLAYER_HEAD"} @self
```
```yaml
伪装测试:
  Skills:
  - disguise{d=PLAYER Sharrk_kunjang setDisguiseName 鲨鲨} @self
```
```yaml
伪装成成熟小麦:
  Skills:
  - disguise{d=alling_block Wheat[age=7]} @self
```


拓展信息
--------

- **支持** Audience