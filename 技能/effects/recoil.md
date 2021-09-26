**特效技能: Recoil** 

Kicks the casters screen to simulate recoil.

---

**修改项:**

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| recoil           | r     | 后坐力大小 | 1              |
| pitch            | p     |  | 1to-1              |
---



**示例:**

```
- recoil{r=1;pitch=-1to-1} @self ~onAttack
- recoil{r=4;pitch=10to-10} @self ~onAttack
```