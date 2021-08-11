技能: Disguise
--------------------------

令自身伪装.

在 MM4.12中,此技能的修改项可以缩写为一行包含着伪装种类与伪装选项的字符串.

若MM版本在4.12以下,请使用技能: disguiseOld

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| disguise  | d, type | 伪装内容 | 无 |

示例
--------

**4.12的写法**

使用 **/mm test cast 伪装测试** 测试下方技能.  
令自身伪装成 处在旋转视角状态 燃烧状态 名字永远可见 且名字为Zombie的羊.
```
伪装测试:
  Skills:
  - disguise{d="Sheep SetBurning SetSpinning SetCustomNameVisible setCustomName Zombie"} @self
```

令自身伪装成 Y轴偏移为-1.5格方块 视角无法俯仰视 实体本身不可见 头戴玩家头颅的僵尸.

```
伪装测试:
  Skills:
  - disguise{d="Zombie setYModifier -1.5 setPitchLocked setInvisible setHelmet PLAYER_HEAD"} @self
```

---------
**4.12以下的写法**

      Skills:
      - disguiseOld{d=SHEEP}

---------
