**描述:** 若所处世界为指定世界.

**低版本不可用（4.11），补救方法见下**

---

**修改项:**

| 修改项名  | 别称           | 描述                      | 默认值 |
| --------- | -------------- | ------------------------- | - |
| world | w | 用于检测的世界名 | tutorial_world |

---

**示例:**

```yaml
Conditions:
- world{w=world} true
```

补救方法（需"Player"占位符拓展)  
执行命令`/papi ecloud download player`后`/papi reload`即可安装
```yaml
Conditions:
- stringequals{v1="world";v2=%player_world%}
```

---

**拓展信息:**

- [x] 检测对象: 位置