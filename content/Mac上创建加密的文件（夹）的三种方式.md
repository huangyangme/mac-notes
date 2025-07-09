## 1，用自带磁盘工具创建 dmg 加密文件

打开磁盘工具，在菜单栏选择「文件-新建映像-给予文件夹新建映像」。

[![](https://macpai.cn/content/images/2025/01/Pasted-Graphic-2-1.png)](https://macpai.cn/content/images/2025/01/Pasted-Graphic-2-1.png)

选择要加密的文件夹，选择加密强度（推荐 256 位 AES）和密码，然后存储。

[![](https://macpai.cn/content/images/2025/01/Pasted-Graphic-3.png)](https://macpai.cn/content/images/2025/01/Pasted-Graphic-3.png)

下次点开带加密的 dmg 文件，就会先要求输入密码才能打开。

[![](https://macpai.cn/content/images/2025/01/Pasted-Graphic-5.png)](https://macpai.cn/content/images/2025/01/Pasted-Graphic-5.png)

这种方案的好处是 macOS 不需要安装第三方软件。坏处是不兼容 Mac 以外的设备平台（包括iPhone、iPad、安卓、Windows PC）。

iOS 平台可以通过安装例如 [Disk Decipher](https://disk-decipher.app/?ref=macpai.cn) 这样的第三方 app 实现打开 DMG 文件。

## 2，使用第三方解压缩软件制作加密的压缩包

以 [Keka](https://www.keka.io/en/?ref=macpai.cn) 为例，可以把文件夹创建成带 AES-256 加密密码的 ZIP 压缩吧文件。

[![](https://macpai.cn/content/images/2025/01/--------.png)](https://macpai.cn/content/images/2025/01/--------.png)

下次点开带加密的 ZIP 文件，会先提示输入密码。

[![](https://macpai.cn/content/images/2025/01/Pasted-Graphic-6.png)](https://macpai.cn/content/images/2025/01/Pasted-Graphic-6.png)

这种方案的好处是 ZIP 兼容性最高（iOS无需安装软件即可解锁并解压），坏处是每次都会解压出一个新文件夹。

另外，现有的大多数操作系统例如 macOS（在 macOS 11.0 Big Sur 之前）或 Windows 默认不支持 AES-256 加密的 ZIP 文件。

## 3，用第三方文件加密工具创建加密文件

也可以安装第三方专门加密文件的软件，比如跨 macOS 和 Windows 平台的 [Encrypto](https://apps.apple.com/cn/app/encrypto-secure-your-files/id935235287?mt=12&ref=macpai.cn)，但是这种方案很受限于软件本身，加密后的文件兼容性差（设备必须安装此软件），并且隐私安全方面有更多顾虑。