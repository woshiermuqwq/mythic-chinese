
特效技能
-------------

特效技能是技能的一类,通常用于制作视觉效果与音效

修改项 `audience=World` or `audience=Target` 允许特效技能仅对特定实体拥有效果 默认值为 `World`

### 语法

大部分特效技能无需用 **effect(e):**作为前缀  

    Skills:
    - flames @T
    - e:lightning @self
    - ender @pir{r=20}
    - ender @pir{r=20}
    - e:p{p=reddust;c=#EE22CC;a=10;s=1;hS=0.15;vS=.15;audience=Target} @target

### 列表

| 技能名               | 描述                                                                  |
|----------------------|-----------------------------------------------------------------------|
| [Black Screen][]     | 黑屏                       |
| [Block Mask][]       | 令指定位置的方块伪装                        |
| [Block Unmask][]     | 取消指定位置的方块伪装                                  |
| [Block Wave][]       | 于技能目标位置生成方块波                       |
| [Bloody Screen][]    | 令技能目标屏幕变为边界效果                                    |
| [Ender][]            | 于技能目标位置生成末影效果                                             |
| [Ender Beam][]       | 生成末影水晶并向技能目标发射光束                          |
| [Explosion][]        | 于技能目标位置生成爆炸(有音效无伤害)                                            |
| [Firework][]         | 于技能目标位置发射一发烟花火箭（似乎无法工作）                                           |
| [Flames][]           | 于技能目标位置生成火花                                   |
| [Geyser][]           | 于技能目标位置生成向上移动的液体                                   |
| [Glow][]             | 令技能目标发光(修改光色需GlowAPI) |
| [Item Spray][]       | 于技能目标位置抛洒物品掉落物                              |
| [Lightning][]        | 于技能目标位置生成雷击(无伤害)                                        |
| [Particles][]        | 于技能目标位置播放粒子效果                           |
| [Particle Box][]     | 于技能目标位置生成一个不可见的方体, 随机选取方体内指定数量的点                            |
| [Particle Line][]    | 连接施法者与技能目标的粒子线                       |
| [Particle Orbital][] | 于技能目标位置生成粒子环绕并跟随目标                     |
| [Particle Ring][]    | 于技能目标位置生成由粒子组成的空心环                           |
| [Particle Sphere][]  | 于技能目标位置生成由粒子组成的空心球                         |
| [Particle Tornado][] | 于技能目标位置生成粒子龙卷风               |
| [Recoil] | 偏转目标的视角 |
| [Skybox][]           | 修改目标客户端的环境氛围                                            |
| [Smoke][]            | 于目标位置生成烟雾效果                                               |
| [Smoke Swirl][]      | 于目标位置生成烟雾漩涡                                 |
| [Sound][]            | 于目标位置播放音效                             |
| [Spin][]             | 旋转目标的朝向                                                |
| [TotemOfUndying][]     | 于目标位置生成播放激活不死图腾效果     

[skill mechanic]: /技能/列表
  [Targeter]: /技能/targeters/
  [Black Screen]: /技能/effects/blackscreen
  [Block Mask]: /技能/effects/blockmask
  [Block Unmask]: /技能/effects/blockunmask
  [Block Wave]: /技能/effects/blockwave
  [Bloody Screen]: /技能/effects/bloodyscreen
  [Ender]: /技能/effects/ender
  [Ender Beam]: /技能/effects/enderbeam
  [Explosion]: /技能/effects/explosion
  [Firework]: /技能/effects/firework
  [Flames]: /技能/effects/flames
  [Geyser]: /技能/effects/geyser
  [Glow]: /技能/effects/glow
  [Item Spray]: /技能/effects/itemspray
  [Lightning]: /技能/effects/lightning
  [Particles]: /技能/effects/particles
  [Particle Box]: /技能/effects/particlebox
  [Particle Line]: /技能/effects/particleline
  [Particle Orbital]: /技能/effects/particleorbital
  [Particle Ring]: /技能/effects/particlering
  [Particle Sphere]: /技能/effects/particlesphere
  [Particle Tornado]: /技能/effects/particletornado
  [Recoil]: /技能/effects/recoil
  [Skybox]: /技能/effects/skybox
  [Smoke]: /技能/effects/smoke
  [Smoke Swirl]: /技能/effects/smokeswirl
  [Sound]: /技能/effects/sound
  [Spin]: /技能/effects/spin
  [TotemOfUndying]: /技能/effects/totemOfUndying
  [Atom]: /技能/effects/atom
  [Particle Vortex]: /技能/effects/particlevortex
  [DNA]: /技能/effects/dna