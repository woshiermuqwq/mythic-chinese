技能: Json Message
--------------------------

向目标(玩家)发送Json信息.

修改项
----------

| 修改项名 | 别称    | 描述                                                                                                    | 默认值 |
|-----------|------------|----------------------------------------------------------------------------------------------------------------|---------------|
| message   | m       | 信息内容,被双引号所包裹 |         |

示例
--------

正确语法:

      Skills:
      - jsonmessage{m="[{'text':'&aHey, i am a JSON message!'}]"} @trigger ~onInteract
      - jsonmessage{m="[{'text':'Hey, i am a red JSON message!','color':'red'}]"} @trigger ~onInteract


------------------------------------------------------------------------

悬停事件语法:
  
<img src="http://fs5.directupload.net/images/160309/7irfoune.jpg" width="500" height="30" alt="http://fs5.directupload.net/images/160309/7irfoune.jpg" />

      Skills:
      - jsonmessage{m="[{'text':'&7鼠标瞄这儿将显示一些东西','hoverEvent':{'action':'show_text','value':{'text':'&a这就是 一些东西)'}}}]"} @trigger ~onInteract

------------------------------------------------------------------------

点击事件语法:
  
![](http://fs5.directupload.net/images/160309/gjxvhpd8.jpg)

      Skills:
      - jsonmessage{m="[{'text':'&7&n不要点我QAQ :)','clickEvent':{'action':'run_command','value':'/minecraft:kill %player_name%'}}]"} @trigger ~onInteract

