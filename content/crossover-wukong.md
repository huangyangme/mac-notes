![[f9ff21fc1fd04bed981328f2a4ae5d54.jpg]]
## Only M2

第一难就是只有 M2 系列的 Mac 才能运行《黑神话：悟空》，M1 和 M3 系列都不行，据说会有贴图问题。并且在 M2 Max/Ultra 上才能获得画质和流畅度尚可的体验。另外系统要求 macOS 14.0 或以上（且非Beta版）。

## 目前最佳方案只有 CrossOver

虚拟机方案可以吗？不行。不管是 Parallels Desktop 还是 VMware，在 M系列芯片 Mac 上都只能安装 Windows ARM，而 Windows 版 Steam 是 x86 架构的。

Whisky 虽然是跟 CrossOver 类似的代码转译方案，但我测试 Whisky 只能运行《黑神话》性能测试工具，无法运行游戏本体。

简单说一下安装流程：

下载安装 CrossOver → 下载并通过 CrossOver 安装 Steam for Windows →通过此 Steam 购买、下载和运行《黑神话：悟空》游戏。
## 画质设置以及画面效果

我这台 Mac Studio 的配置是 M2 Max + 12核CPU+ 38核GPU（玩这款游戏最重要的指标）。

游戏画质设置主要调整「超采样清晰度」和「画质细节」。

「画质细节」我全部设为「中」，==「全局光照」这一项一定要设为「低」==，不然画面暗部会细节尽失，根本没法看。

有网友建议“务必关闭帧生成，会显著增加卡顿与掉帧”。

![[截屏2024-09-02 11.16.00.0ce81a453ee849f5819d3b19ac721df2.jpg]]

「超采样清晰度」设为「100」（数值越高，画面效果越好，但是流畅度也就是帧率会下降）时，画面效果还不错，明暗过渡真实，画面细节丰富，流畅度大概在 40+fps，勉强能接受。

「超采样清晰度」设为「50」，画面效果看起来会「糊」一些，少了一些真实感，但画面很流畅，帧率几乎能达到 60fps。

![[截屏2024-09-02 11.22.26.9ff43eb843f643789b74661c00f7b598.jpg]]

这种方式下也可以连游戏手柄玩，我用 Switch Pro 手柄连上 Mac，然后就可以用手柄操控游戏了。

相关：

[[whisky-install-games]]
[https://mrmad.com.tw/black-myth-wukong-macos#google\_vignette](https://mrmad.com.tw/black-myth-wukong-macos#google_vignette)

