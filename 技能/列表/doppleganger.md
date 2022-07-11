技能: Doppleganger
--------------------------

令自身伪装成技能目标(玩家).

修改项
------

| 修改项名 | 别称 | 描述 | 默认值 |
| - | - | - | - |
| hasnameplate | nameplate | 是否将伪装显示名变更为"_" | false |
| useplayername | upn | 是否使用技能目标玩家的名称作为伪装显示名 | false |

当修改项: UsePlayerName 为false时, HasNamePlate 将自动设为true.

示例
--------

```yaml
 Skills:
 - doppleganger @target ~onDamaged
```
受伤后伪装成仇恨目标（玩家）.

额外信息
-------

- 别称: CopyPlayer