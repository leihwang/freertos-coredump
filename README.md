# freertos-coredump
基于国产Phytium 芯片的FreeRTOS Coredump机制的实现

### 项目描述

在基于国产Phytium 芯片的软件开发过程中，经常会因bug导致系统处于异常状态。如系统支持在发生不可恢复的软件错误时，触发Coredump机制，生成Coredump文件，便于事后分析，可以大大提升软件debug效率。coredump文件包含故障时刻系统中所有任务的快照，快照包括任务控制块(TCB)、堆栈等上下文信息。通过分析工具可以快速打印异常状态的上下文信息，便于问题定位。

### 所属赛道

2022全国大学生操作系统比赛的“OS功能设计”赛道

### 参赛要求

- 以小组为单位参赛，最多三人一个小组，且小组成员是来自同一所高校的本科生/研究生
- 如学生参加了多个项目，参赛学生选择一个自己参加的项目参与评奖
- 请遵循“2022全国大学生操作系统比赛”的章程和技术方案要求

### 项目导师

- gitee @leihuang
- email: huanglei1@kylinos.cn
- gitee @cuiyanzhao
- email: cuiyanzhao@kylinos.cn
- gitee @zhangyunfei
- email: zhangyunfei@kylinos.cn

### 难度

高

### 特征

- 需要了解ARM体系结构与编程
- 需要了解FreeRTOS
- 需要了解crash工具

### 参考文档

https://www.freertos.org/

FT-2000／4 四核处理器软件编程手册-V1.5.pdf

armv8结构及指令集.pdf

### License

GPL-3.0

### 预期目标

**注意：下面的内容是建议内容，不要求必须全部完成。选择本项目的同学也可与导师联系，提出自己的新想法，如导师认可，可加入预期目标**

**第一题：Coredump基础功能实现**

1.	可以正常跳转coredump触发程序，执行coredump动作
2.	可以通过本地自动/本地手动的方式触发coredump
3.	可以通过串口等方式将coredump信息传递给上位机，上位机可以使用开源的crash dump工具配合elf完成解析工作


**第二题：Coredump解析工具实现**

以题目一为基础，工具需要追加下列功能：
1.	coredump解析工具可以正确解析下位机通过串口输出的coredump文件，包括不限于寄存器，堆栈，内存等
2.	coredump解析工具能够自动分析coredump文件，能够图形化显示问题现场，GUI开发工具不限

**（可选）第三题：coredump解析工具进阶**

以题目二为基础，工具需要追加下列功能：
1.	coredump生成时能够转储内存信息，转存介质可以是sd，flash等
2.  coredump生成时能够分模块转储内存信息，coredump分析工具能够分模块分析对应的coredump文件，模块可以按地址或功能划分
3.	coredump解析工具支持脚本化配置，可以通过脚本简化定位coredump 内容的过程
4.  上位机可以通过Ethernet触发下位机coredump，并通过Ethernet转储coredump信息
