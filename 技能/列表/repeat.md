通用修改项: Repeat 与 RepeatInterval
--------------------------

设置重复激活次数与重复激活间隔(刻).

俩者仅能作为技能修改项.

实际激活次数为 重复激活次数(Repeat)的值+1

重复激活过程所耗时间为 (Repeat值+1) * RepeatInterval的值.

示例
--------
    
      Skills:
      - message{m="a";repeat=49;repeatInterval=1} @target

在2.5秒内向当前目标发送50次"a".

额外信息
-------

**支持** [占位符](/技能/占位符（≥4.11）