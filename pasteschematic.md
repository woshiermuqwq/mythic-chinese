技能: Paste Schematic (4.11)
--------------------------

粘贴一个Schematic文件  
MM 4.13 之前的技能名为: `FawePaste`

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| schematic |  s       | 所粘贴的文件 **位于MythicMobs/Schematics文件夹内**. | 1             |
| pasteAir | air,a       | 是否替换空气 | true             |
| xOffset | x,xo      | 所替换位置的X轴偏移   | 0             |
| yOffset | y,yo      | 所替换位置的Y轴偏移   | 0             |
| zOffset | z,zo      | 所替换位置的Z轴偏移   | 0             |
| chestDropTable | chests,cdt      | 粘贴后用于填充箱子的掉落表   | ""             |
| trappedchestDropTable | trapchests,tcdt      | 粘贴后用于填充陷阱箱的掉落表   | ""             |

示例
--------

```yaml
 Skills:
 - fawePaste{schematic=deserttempleiron.schem;y=6;air=true;chestDropTable=IronDropTable} @origin
```