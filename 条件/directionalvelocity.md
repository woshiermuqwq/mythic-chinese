**描述:** 若实体的三轴动量在指定范围内.

---

**修改项:**

| 修改项名  | 别称           | 描述                      | 默认值
| --------- | -------------  | ------------------------- | - |
| x | 无 | X轴动量 | 无 |
| absx | 无 | 是否检测X轴动量的绝对值 | false |
| y | 无 | Y轴动量 | 无 |
| absy | 无 | 是否检测Y轴动量的绝对值 | false |
| z | 无 | XZ轴动量 | 无 |
| absz | 无 | 是否检测Z轴动量的绝对值 | false |

---

**示例:**

```yaml
 - aura{d=100;ot=[  - potion{t=glowing;d=3} ?!directionalvelocity{y=0} ?!directionalvelocity{y=>0} ]} @self
```
激活技能5秒内, 当自身正在下落时发光

---

拓展信息
---

- 检测对象: 实体