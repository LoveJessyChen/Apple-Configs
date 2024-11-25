# Mac 关闭SIP和SSV的方法

## 0.进入恢复模式

ARM：将Mac彻底关机，长按电源键（10s以上）进入恢复模式，出现Macintosh和设置两个选项，用鼠标点击右侧的“设置”，点按下方的“继续”，进入恢复模式。

（Intel：将Mac彻底关机，短按电源键后，同时快速长按“Command”和“R”，进入恢复模式）



## 1. 具体操作：

1.1 点击最顶上菜单“实用工具”–选择“终端”，打开终端工具（Terminal）；

1.2 打开终端工具之后，输入下面命令运行，注意空格；

`csrutil disable`

（ARM机型会出现[y/n]: 提示，请输入y确认，

Enter password for user xxxx 时候，输入你的Mac开机用户名与密码并按回车键。）

 [IMG_2423.HEIC](IMG_2423.HEIC) 

1.3 退出终端，打开“实用工具”——》启动安全性实用工具。

勾选“宽松安全性”下方的“两个”复选框（即“允许用户管理来自被认可开发者的内核扩展”和“允许远程管理内核扩展和软件自动更新”）后，点按“好”，退出安全性实用工具。

 [IMG_2424.HEIC](IMG_2424.HEIC) 



1.4 关闭SSV：打开终端，输入下面的命令：

`csrutil authenticated-root disable`

（ARM机型会出现Enter password for user xxxx 时候，输入你的Mac开机用户名与密码并按回车键。）

 [IMG_2425.HEIC](IMG_2425.HEIC) 



1.5 检查是否成功关闭，用status参数：

`csrutil status`

`csrutil authenticated-root status`

 [IMG_2426.HEIC](IMG_2426.HEIC) 



最后，点击苹果标志，重启或关机 退出恢复模式。