技能: Projectile
--------------------------

向目标发射抛射物.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| onTick               | oT          | Meta-Skill executed every [interval] ticks at the projectile's origin location.                                                                                                                       | None              |
| onHit                | oH          | Meta-Skill executed when the projectile hits entities that allow be hit. Targets hit are inherited by the meta-skill.                                                                                                    | None              |
| onEnd                | oE          | Meta-Skill executed when the projectile ends.                                                                                                                                                           | None              |
| Type                 | t           | The "type" of projectile. Default projectiles are launched from the mob's location towards the target. METEOR type projectiles fall from the sky above the target.                                      | NORMAL            |
| Interval             | i           | How often (in ticks) the projectile updates its position                                                                                                                                                | 4                 |
| HorizontalRadius     | hRadius, hR | The horizontal radius entities will be hit in around the projectile.                                                                                                                                    | 1.25              |
| VerticalRadius       | vRadius, vR | The vertical radius entities will be hit in around the projectile.                                                                                                                                      | Horizontal Radius |
| Duration             | d           | The max duration (in ticks) the projectile will persist.                                                                                                                                                | 100               |
| MaxRange             | mr          | The maximum range (in blocks) the projectile will travel.                                                                                                                                               | 40                |
| Velocity             | v           | The velocity of the projectile                                                                                                                                                                          | 5                 |
| StartYOffset         | syo         | Start Y Offset - Lets you offset where on the casting mob the projectile shoots from.                                                                                                                   | +1                |
| StartFOffset         | sfo         | Start Forward Offset - How far in front of the mob the projectile starts                                                                                                                                | +1                |
| StartSideOffset      | sso         | Start Side Offset - How far to the side of the mob the projectile starts                                                                                                                                | 0                 |
| TargetYOffset        | tyo         | Target Y Offset - Lets you offset where on the target the projectile shoots at.                                                                                                                         | +1                |
| HorizontalOffset     | hO          | Horizontal Offset will rotate the projectile's horizontal starting velocity around a 360-degree axis.                                                                                                   | 0                 |
| VerticalOffset       | vO          | Vertical Offset will rotate the projectile's vertical starting velocity around a 360-degree axis.                                                                                                       | 0                 |
| HitPlayers           | hp          | Whether the projectile will only hit player.                                                                                                                                      | true              |
| HitNonPlayers        | hnp         | Whether the projectile will hit any entities(including caster but not players).                                                                                                                                      | false             |
| StopAtEntity         | sE          | Whether the projectile will stop upon hitting a targetable entity.                                                                                                                                      | true              |
| StopAtBlock          | sB          | Whether the projectile will stop upon hitting an opaque block.                                                                                                                                          | true              |
| HugSurface           | hs          | Whether or not the projectile should move along the ground.                                                                                                                                             | false             |
| HeightFromSurface    | hfs         | For NORMAL projectiles, how high above the surface the projectile should glide if HugSurface is set to TRUE. For METEOR projectiles, how high above the surface the projectile starts above the target. | 0.5               |
| PowerAffectsRange    | par         | Whether a mob's [power level](power level) affects the projectile's range.                                                                                                                              | true              |
| PowerAffectsVelocity | pav         | Whether a mob's [power level](power level) affects the projectile's velocity.                                                                                                                           | true              |
| gravity              | g           | Determines the gravity of the projectile; use fractions (0.1-0.2) for low gravity                                                                                                                       | 0                 |
示例
--------

