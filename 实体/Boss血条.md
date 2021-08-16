**Boss血条**

Boss血条允许您创建一个形似末影龙与凋灵的血条,并提供一系列可选项

**格式**

```
MythicMobs实体名:
  Type: 实体类型
  Bossbar:
    Enabled: true/false(是否开启)
    Title: '标题文本'
    Range: 显示范围
    Color: 血条颜色
    Style: 血条样式
    CreateFog: true/false(是否创造迷雾效果)
    DarkenSky: true/false(是否改变天气为阴天)
    PlayMusic: true/false(是否播放音效)
```

血条颜色可为: PINK(粉), BLUE(蓝), RED(红), GREEN(绿), YELLOW(黄), PURPLE(紫), WHITE(白)

血条样式可为: SOLID, SEGMENTED_6, SEGMENTED_10, SEGMENTED_12, SEGMENTED_20

在显示范围之外的玩家不会显示Boss血条

**例子**

```
超级爬行者:
  Type: creeper
  Display: '&c测试'
  Health: 20
  Bossbar:
    Enabled: true
    Title: '测试标题文本'
    Range: 20
    Color: RED
    Style: SOLID
```