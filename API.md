此部分与插件开发有关，若您不会Java编程，可以跳过此部分
## JavaDocs

MythicMobs的JavaDocs页面:

1. [https://www.mythicmobs.net/javadocs/](https://www.mythicmobs.net/javadocs/)

## Maven

### Repository

```xml
<repository>
    <id>nexus</id>
    <name>Lumine Releases</name>
    <url>https://mvn.lumine.io/repository/maven-public/</url>
</repository>
```

### Dependency

```xml
<dependency>
    <groupId>io.lumine.xikage</groupId>
    <artifactId>MythicMobs</artifactId>
    <version>4.9.1</version>  
    <scope>provided</scope>
</dependency>
```

## 示例

MythicMobs API包含许多事件和帮助程序类以提供帮助\
你可以使用我们的怪物、物品和技能系统。

这里有一些可以帮助你起步的例子：

1. [MythicMobs API Examples Repo](https://github.com/xikage/MythicMobs-API-Examples)

## 事件
| 事件名 | 描述 |
|-----|----|
| [MythicReloadedEvent](/api/events/MythicReloadedEvent) | 重载 |
| [MythicMobSpawnEvent](/api/events/MythicMobSpawnEvent) | 生成实体 |
| [MythicMobDeathEvent](/api/events/MythicMobDeathEvent) | 实体死亡 |
| [MythicMobDespawnEvent](/api/events/MythicMobDespawnEvent) | 实体消失 |
| [MythicMobLootDropEvent](/api/events/MythicMobLootDropEvent) | 实体掉落 |
| [MythicConditionLoadEvent](/api/events/MythicConditionLoadEvent) | 条件加载 |
| [MythicDropLoadEvent](/api/events/MythicDropLoadEvent) | 掉落配置加载 |
| [MythicMechanicLoadEvent](/api/events/MythicMechanicLoadEvent) | 技能加载 |
| [MythicTargeterLoadEvent](/api/events/MythicTargeterLoadEvent) | 目标选择器加载 |