技能: Speak
--------------------------

向技能目标发送聊天栏信息并弹出悬浮以显示文本.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| offset        | o           | 悬浮字文本的垂直偏移值 | 0.4f                             |
| radius        | r           | 聊天栏信息可被指定格数半径范围内的所有玩家所看见 | 12  |                            
| maxlinelength | ll, mll, ml | 悬浮字文本最大字符长度 | 22                               |
| lineprefix    | lp          | 悬浮字文本前缀 | &f                               |
| message       | m           | 聊天栏与悬浮字的文本 | 无                             |
| sendchatmessage | chatmessage, chat | 是否发送聊天栏信息 | true |
| chatprefix    | cp          | 聊天栏文本前缀 | &lt;caster.name&gt;&f&lt;&co&gt; |
| duration      | d, t        | 悬浮字持续时间(刻) | 文本字符长度 * 4              |

示例
--------

```yaml
 Skills:
 - speak{offset=0.6f;radius=30;maxlinelength=22;lineprefix="&5";message=" 我回来了!";chatprefix=<caster.name>&f<&co>;duration=200} @self ~onSpawn
```

额外信息
--

- [x] 别称: speech