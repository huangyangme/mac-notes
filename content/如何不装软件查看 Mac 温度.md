想查看 Mac 的温度、风扇转速等信息，除了安装「[腾讯柠檬清理](https://lemon.qq.com/?ref=macpai.cn)」、「[iStat Menus](https://bjango.com/mac/istatmenus/?ref=macpai.cn)」这类第三方工具，还有一种不安装 App，只输入命令行就能查看这些信息的方法。

[iStats](https://github.com/Chris911/iStats) 就是这样一款命令行工具，可让你直接在终端输入命令（iStat）就能获取 Mac 的 CPU 温度、风扇速度和电池信息。

首先要打开「终端」app，输入 `sudo gem install iStats` 然后回车，接着输入你的 Mac 登录密码（输入时候不可见），并再次回车。

[![](https://macpai.cn/content/images/2025/01/8267457416_558669.jpg)](https://macpai.cn/content/images/2025/01/8267457416_558669.jpg)

下一次想查看 Mac 的温度，只需要**打开终端，输入 istats 然后回车**就行了。

[![](https://macpai.cn/content/images/2025/01/8267457322_936735.jpg)](https://macpai.cn/content/images/2025/01/8267457322_936735.jpg)

界面会显示 Mac 的 CPU 温度、风扇转速、电池温度和状况（Mac笔记本专属）等。

如果出现温度或风扇过高，状态显示会变成红色，并且闪动。

[![](https://macpai.cn/content/images/2025/01/8267457041_227827.gif)](https://macpai.cn/content/images/2025/01/8267457041_227827.gif)

更多 iStats 命令可以去项目主页 [https://github.com/Chris911/iStats](https://github.com/Chris911/iStats?ref=macpai.cn) 查看。