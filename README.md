# RadminSavePassword
程序会自动记录并管理Radmin的密码

## **适用于以下Radmin**
| 属性 |   值   |
|------|:------:|
| 版本 |3.4、3.5|
| 语言 |  多国  |

## **实现原理：**
- 程序在启动后，通过安装系统钩子(Hook)，对Windows窗体创建销毁、鼠标、键盘进行监控，从而达到获取Radmin程序的登陆信息

## **关于钩子(Hook)：**
- 钩子(Hook)，是Windows消息处理机制的一个平台，应用程序可以在上面设置子程以监视指定窗口的某种消息，而且所监视的窗口可以是其他进程所创建的。当消息到达后，在目标窗口处理函数之前处理它。钩子机制允许应用程序截获处理window消息或特定事件。
- 钩子实际上是一个处理消息的程序段，通过系统调用，把它挂入系统。每当特定的消息发出，在没有到达目的窗口前，钩子程序就先捕获该消息，亦即钩子函数先得到控制权。这时钩子函数即可以加工处理（改变）该消息，也可以不作处理而继续传递该消息，还可以强制结束消息的传递。
- 来源：[百度百科]

> **注意：**由于.Net程序安装WH_SHELL和WH_CBT Hook这两个Hook会失败，因此通过C++的DLL间接地安装Hook，然后再通知.Net的程序进行处理的手段
> 
> 详情参阅：
> [http://www.codeproject.com/Articles/18638/Using-Window-Messages-to-Implement-Global-System-H](http://www.codeproject.com/Articles/18638/Using-Window-Messages-to-Implement-Global-System-H)


[百度百科]:http://baike.baidu.com/link?url=vvhHuJDnkVN4IaE319drtMogwGv4Jf-ra3Cik8IcMHvf8iqUsa2noXU42twUMYq9VZyfK1Aml_ApNXzx80C0Q_
