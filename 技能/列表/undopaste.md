技能: Undo Pate (5.3.0)
--------------------------

撤销通过 [Fawe Paste](/TranslatedByShark/Mythic-Manual-CN/-/wikis/%E6%8A%80%E8%83%BD/%E5%88%97%E8%A1%A8/fawepaste) 所生成的区域(schematics)

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| id | "pasteid, pid | 所要撤销的操作名或区域文件名 | 无 |

示例
--------

```yaml
### 撤销已定义内部名的区域
- fawePaste{s=cs.schem;id=cs} @self ~onSpawn
- undoPaste{id=cs} @self ~onDamaged
### 撤销未定义内部名的区域
- fawePaste{s=cs.schem} @self ~onSpawn
- undoPaste{id=cs.schem} @self ~onDamaged
```
出生后粘贴区域: `cs.schem`, 并将其存储为操作: `cs`  
受伤后撤销操作: `cs`

出生后粘贴区域: `cs.schem`  
受伤后撤销区域: `cs.schem`

额外信息
-

- [x] 别称: undoSchematic, undoSchem
