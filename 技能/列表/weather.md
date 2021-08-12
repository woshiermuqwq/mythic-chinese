技能: Weather
=================

修改目标所处世界的天气.

修改项
----------

| 修改项名 | 别称   | 描述                                               | 默认值 |
|-----------|-----------|-----------------------------------------------------------|---------|
| type      | sunny | 天气类型,可为 "sunny", "rainy", "stormy" | sunny   | 无 |
| duration  |           | 天气持续时间(刻) | 500     |

  
天气类型别称:  
|**Sunny**| sun, clear|

|            |                |
|------------|----------------|
| **Rainy**  | rain           |
| **Stormy** | storm, thunder |

示例
--------

      Skills:
      - weather{type=storm;duration=6000} ~onSpawn
