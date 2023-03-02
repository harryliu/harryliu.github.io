# OEE 机台整体效率监控


## OEE 机台整体效率监控系统
客户：上海中型机械制造工厂(约有近百台数控机床和加工中心)。
在各类加工制造行业，如何提高机台利用率，是每一个企业家都需要关注的，好处有:
- 能最大程度地减少机台采购数量
- 可以合理进行加工任务排期
- 可以防止工人摸鱼, 降低用工成本

为客户定制开发了一套基恩士 TM-3000 测量仪配套的管理系统，反馈不错。 如果有谁需要定制开发，可以联系我，`liuzhongwu2008@163.com.`

## 功能需求
- 以部门为单位，实时收机每台机台的稼动率，在汇总部门机台的总稼动率
- 大屏显示每个部门机台的稼动率
- 如果某个机台在给定时长不工作，可以推送消息给相关负责人

![](../oee_files/2.jpg)


## 部署架构图
![](../oee_files/21.jpg)

  

## Oee.Main 程序配置
Oee.Main 程序提供系统管理和看板功能.  
大屏看板界面:   
![](../oee_files/17.jpg)

管理菜单:  
在使用之前, 需要完成系统基础数据维护工作. 
![](../oee_files/20.jpg) 



## Oee.Collector 程序配置
Oee.Collector 程序负责从PLC中收集机台状态, 并完成状态的预处理工作, 将结果写入到 Oee 数据库中.   
一个工厂可以启动多个 Oee.Collector 程序, 但应确保对于特定一个机台, 只能有一个 Oee.Collector 程序完成信号采集, 要防止多个程序重复收值.    
- 红灯，设备故障, 读数为1
- 绿灯，设备生产运行中, 读数为2
- 黄灯，设备待料待机, 读数为3

 ![](../oee_files/19.jpg)


如果您有类似需求，可以联系我，`liuzhongwu2008@163.com`
