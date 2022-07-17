**描述:** 若目标实体在俩坐标点点所形成的区域内.

---

修改项
---

| 修改项名  | 别称           | 描述                      |
| --------- | -------------- | ------------------------- |
| location1 | loc1, l1, a | A点坐标 |
| location2 | loc2, l2, b | B点坐标 |
| relative | r | 坐标是否以施法者坐标为中心并进行偏移 |
| world | 无 | 所检测的世界名 |
---

示例
---

```yaml
 TargetConditions:
 - cuboid{location1=x,y,z;location2=x,y,z;world=world;relative=true}
```

拓展信息
---

- [x] 检测对象: 实体与施法者(比较)