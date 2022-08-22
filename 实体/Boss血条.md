**Boss血条**
============

Boss血条允许您创建一个形似末影龙与凋灵的血条,并提供一系列可选项

**语法**
--------

```yml
MythicMobs实体名:
  Type: 实体类型
  BossBar:
    Enabled: true/false(是否开启)
    Title: '标题文本, 支持占位符'
    Range: 显示范围
    Color: 血条颜色
    Style: 血条样式
    CreateFog: true/false(是否创造迷雾效果)
    DarkenSky: true/false(是否改变天气为阴天)
    PlayMusic: true/false(是否播放音效)
```

血条颜色可为: PINK(粉), BLUE(蓝), RED(红), GREEN(绿), YELLOW(黄), PURPLE(紫), WHITE(白)

血条样式列表
-----------

| 样式名 | 描述 |
| - | - |
| SOLID | 平滑 |
| SEGMENTED_6 | 分6段 |
| SEGMENTED_10 | 分10段|
| SEGMENTED_12 | 分12段 |
| SEGMENTED_20 | 分20段 |

在显示范围之外的玩家不会显示Boss血条

**示范**
---------

```yml
超级爬行者:
  Type: creeper
  Display: '&c测试'
  Health: 20
  BossBar:
    Enabled: true
    Title: '测试标题文本'
    Range: 20
    Color: RED
    Style: SOLID
```