**描述:** 若实体拥有状态效果且时长与等级在指定数值范围内.

---

**修改项:**

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| type      | t       | 用于检测的药水效果类型              |
| level     | lvl, l  | 用于检测的等级数值范围    |
| duration  | d       | 用于检测的时长数值范围 |

---

**示例:**

```
Conditions:
- haspotioneffect{t=SLOW;l=0-2;d=0-9999} true
```

```
TargetConditions:
- haspotioneffect{t=Speed;l=0-9} true
```

---

**拓展信息:**

- [x] 检测对象: 实体