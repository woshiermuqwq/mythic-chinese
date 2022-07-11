技能: Json Message
--------------------------

向技能目标（玩家）发送Json信息.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|------------------------------------|---------------|
| message   | m       | 信息内容,被双引号所包裹 | 无 |

示例
--------

正确语法:

```yaml
 Skills:
 - skill{s=[
  - jsonmessage{m="[{'text':'&a阿巴阿巴'}]"}
  - jsonmessage{m="[{'text':'红色阿巴阿巴','color':'red'}]"}
  ]} @trigger ~onInteract
```


------------------------------------------------------------------------

悬停事件语法:

```yaml
 Skills:
 - jsonmessage{m="[{'text':'&7鼠标瞄这儿将显示一些东西','hoverEvent':{'action':'show_text','value':{'text':'&a这就是 一些东西)'}}}]"} @trigger ~onInteract
```

------------------------------------------------------------------------

点击事件语法:

```yaml
 Skills:
 - jsonmessage{m="[{'text':'&7&n不要点我QAQ :)','clickEvent':{'action':'run_command','value':'/minecraft:kill %player_name%'}}]"} @trigger ~onInteract
```

