**描述:** 若实体拥有指定标签.

---

**修改项:**

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| tag       | t       | 用于检测的标签名 |

---

**示例:**

```
Conditions:
- hastag{t=KilledBoss1} true
```

```
TargetConditions:
- hastag{t=PuzzleRoom1Solved} true
```

---

**拓展信息:**

- [x] 检测对象: 实体
- [x] 别称: hasScoreboardTag