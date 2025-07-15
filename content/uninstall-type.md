---
title: 彻底卸载Mac第三方输入法
description: 
date: 2025-07-15 10:16
tags:
  - 经验
  - 软件
---
## 手动卸载

先在 macOS 系统设置-键盘-输入法编辑里==移除此输入法==。

然后在「活动监视器」里==强制退出此输入法的进程==。

第三方输入法的 app 文件会放在 macOS 的 `/Library/Input Methods` 路径下，==删除即卸载==。

![[640-6.jpg]]

但除了 app 文件，其实还残存着跟输入法相关的「应用程序支持」、「偏好设置」等文件，把它们全部删掉才算真正卸载干净。

### 「微信输入法」相关文件位置

应用程序支持文件（删除整个 WeType 文件夹）：

`~/Library/Application Support/WeType/`

偏好设置文件（删除 .plist 文件）：

`~/Library/Preferences/com.tencent.inputmethod.wetype.plist`

### 「落格输⼊法」相关文件位置

应用程序支持文件（删除整个 LogInputMac3 文件夹）

`~/Library/Application Support/LogInputMac3`

自定义码表方案等（删除整个落格输⼊法文件夹）

`~/Documents/落格输⼊法`

偏好设置文件（删除 .plist 文件）

`~/Library/Preferences/com.logcg.inputmethod.LogInputMac3.plist`
`~/Library/Preferences/com.logcg.inputmethod.LogInputMac3.Settings.plist`

### 「鼠鬚管（Squirrel）输入法」相关文件位置

「鼠鬚管（Squirrel）输入法」的官方项目页面（https://github.com/rime/home/wiki/FAQ）也提供了卸载指导，但说得比较模糊。

应用程序支持文件（删除整个 im.rime.xxx 文件夹）

`~/Library/HTTPStorages/im.rime.inputmethod.Squirrel`

相关配置文件（删除 Rime 文件夹）

`~/Library/Rime`

偏好设置文件（删除 .plist 文件）

`~/Library/Preferences/im.rime.inputmethod.Squirrel.plist`

### 「搜狗输入法」相关文件位置

应用程序支持文件（删除整个 com.sogou.xxx 文件夹）

`~/Library/HTTPStorages/com.sogou.inputmethod.sogou`

`~/Library/HTTPStorages/com.sogou.SogouTaskManager`

偏好设置文件（删除 .plist 文件）

`~/Library/Preferences/com.sogou.SogouTaskManager.plist`

`~/Library/Preferences/com.sogou.inputmethod.sogou.plist`

`~/Library/Preferences/com.sogou.SGAssistPanel.plist`

### 「百度输入法」相关文件位置

应用程序支持文件（删除整个 com.baidu.xxx 文件夹）

`~/Library/HTTPStorages/com.baidu.inputmethod.BaiduIM`

偏好设置文件（删除 .plist 文件）

`~/Library/Preferences/com.baidu.inputmethod.BaiduIM.plist`

## 第三方工具卸载

对比了多款第三方辅助卸载工具后，我发现 [App Cleaner & Uninstaller](https://app-cleaner.com) 卸载得最干净。App Cleaner & Uninstaller 是一款付费软件，支持试用。

App Cleaner & Uninstaller 正版[优惠购买（¥99永久版）](https://lizhi.shop/products/app-cleaner-uninstaller?cid=kj7dpz0h) （🙏感谢支持）