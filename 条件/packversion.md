**描述:** 若已安装的指定配置包版本为给定版本.

---

**修改项:**

| 修改项名  | 别称           | 描述                      |
| --------- | -------------  | ------------------------- |
| packid | pack, p | 所指定的配置包名 |
| packversion | packv, version, v | 所指定的版本号 |

---

**示例:**

```yaml
 Conditions:
 - packversiogreater{p="1";v="5.0.0"}
 Skills:
 - teleport @casterspawn
```
当已安装名为1的配置包且版本号高于5.0.0时, 传送回施法者的出生点

---

拓展信息
---

- 检测对象: 服务器
- 别称: mythicpackversion, packversionis