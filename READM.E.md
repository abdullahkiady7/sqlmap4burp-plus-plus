# sqlmap4burp++ | burp联动sqlmap插件
## 0x01 插件简介
sqlmap4burp++对[sqlmap4burp](https://github.com/difcareer/sqlmap4burp)进行了重构,可在多个平台下快速联动Burp与sqlmap。

![插件ui](doc/sqlmap4burp++ui.png)

在sqlmap4burp基础上进行了如下改动：

* 在支持Windows基础上，拓展对Linux，macOS的支持
* 移除对commons-io-<version>.jar,commons-langs-<version>.jar的依赖
* 移除Burpsuite JTab控件，采用弹窗式配置，让界面更加简洁易用。
* 移除了多余的代码

想了解更多重构细节移步:[《重构sqlmap4burp》](http://gv7.me/articles/2019/refactoring-sqlmap4burp/)

## 0x02 插件编译

```
mvn package
```

## 0x03 插件演示
已经在如下系统测试成功：
* Windows：7,10
* macOS：Mojave 10.14.5
* Linux：Kali2019.2

[![视频演示](https://img.youtube.com/vi/1RWVkztssvw/0.jpg)](https://www.youtube.com/watch?v=1RWVkztssvw)

## 0x04 FQA
#### 1.在macOS下无法弹出Terminal？
出现这种情况，一般有以下两个原因。
* 原因一：没有允许运行外部`Burp suite`运行`osascript`。
* 原因二：没有启动终端（Terminal），请将其启动。若已经是运行状态，那么请重启它！

#### 2.在Linux下弹出Terminal，为何没有执行命令呢？
这是正常现象，插件已经将命令复制到剪贴板，将其粘贴到弹出的命令窗口即可！目前插件在Linux下暂时无法实现启动Terminal的同时使其运行sqlmap命令，所以暂时采用这种临时的方法。

#### 3.插件每次都必须要配置`Python name`和`Sqlmap path`么？
这两个配置是插件保证正常运行的关键，但并不需要每次配置，只需要第一次使用插件时配置好即可。之后无论是关闭插件，重启Burp suite，配置内容都会被记录好。
## 0x05 参考项目
* https://github.com/blueroutecn/Burpsuite4Extender
* https://github.com/difcareer/sqlmap4burp
