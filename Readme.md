
# Real-ESRGAN-GUI

<img width="600" src="https://user-images.githubusercontent.com/39271166/192086070-aedde748-588f-456a-9c88-6fb77877b293.png">

-----

它是一个名为 [realesrgan-ncnn-vulkan](https://github.com/xinntao/Real-ESRGAN-ncnn-vulkan) 的 CLI 工具的简单 GUI 封装程序，而 [realesrgan-ncnn-vulkan](https://github.com/xinntao/Real-ESRGAN-ncnn-vulkan) 则是 [Real-CUGAN](https://github.com/xinntao/Real-ESRGAN-ncnn-vulkan) 的 NCN（Vulkan）实现。 
自 v1.2.0 起，[real-CUGAN](https://github.com/bilibili/ailab/tree/main/Real-CUGAN) 的 NCNN（Vulkan）实现 [realcugan-ncnn-vulkan](https://) github.com/nihui/realcugan-ncnn-vulkan）。 
可以清晰、美观地放大（提高）插图和动画等低分辨率和低质量图像。


使用 [Flutter on Desktop](https://flutter.dev/multi-platform/desktop) 制作（v1.0.0）总共花费了约 5-6 个小时。 
易于制作，用户界面简洁 [Flutter](https://flutter.dev/) 最佳！

## 安装

### Windows

仅支持 Windows 10 或更高版本的 64 位操作系统；不支持 Windows 8 或更早版本和 32 位操作系统。

GPU 包括 [realesrgan-ncnn-vulkan](https://github.com/xinntao/Real-ESRGAN-ncnn-vulkan) / [realcugan-ncnn-vulkan](https://github.com/nihui) /realcugan-ncnn-vulkan) 同样，英特尔显卡、英伟达™（NVIDIA®）GPU 和 AMD GPU 也可使用。

<img width="600" src="https://user-images.githubusercontent.com/39271166/192085275-01e56bc9-4ca8-4e90-b9b9-5092fb9e497b.png">

从 [Releases](https://github.com/tsukumijima/Real-ESRGAN-GUI/releases) 页面下载最新的 Real-ESRGAN-GUI。 
下载 `Real-ESRGAN-GUI-(version)-windows.zip`.

下载后，解压缩 "Real-ESRGAN-GUI-(version)-windows.zip "到合适的文件夹，然后双击其中的 "Real-ESRGAN-GUI.exe"。 
您可以尝试在桌面上创建快捷方式。
### macOS

与 Intel Mac 和 Apple Silicon（M1、M1 Pro、M2 ... 等）兼容。 等）。 
我的印象是，使用 Apple Silicon 的 Mac 生成图像的速度比英特尔 Mac 快（或许最高级别的英特尔 Mac 与之不同）。

<img width="600" src="https://user-images.githubusercontent.com/39271166/189374416-15501eeb-41ba-452c-bef3-402dc450f31d.png">

从 [Releases](https://github.com/tsukumijima/Real-ESRGAN-GUI/releases) 页面下载最新的 Real-ESRGAN-GUI。 
下载 `Real-ESRGAN-GUI-(version)-macos.zip`.

下载后，解压缩 "Real-ESRGAN-GUI-(version)-macos.zip "并将其中的 "Real-ESRGAN-GUI.app "移动到应用程序文件夹。 
然后双击 `Real-ESRGAN-GUI.app`。

## 待遇

有两种模式可供选择：[文件选择]，逐个选择文件；[文件夹选择]，一次性放大文件夹中的多个图像。

### Real-ESRGAN

<img width="600" src="https://user-images.githubusercontent.com/39271166/192085942-8efaeacd-256e-4359-88da-0e3e71caf2df.png">

这是一种通用的人工智能图像放大算法，可在任何状态下生成相当优质的图像。 
它主要针对插图和动画，但也可通过 `realesrgan-x4plus` 模型用于实景照片。

与 Real-CUGAN 相比，线条会更清晰，颜色会稍有变化，细节也会丢失。 
不过，它生成的图像美观大方，人工智能特有的伪影也少得多。 
在大多数情况下，它都能给出令人满意的分数，我的印象是，线条颜色本身保存得很好。

#### 模型

realesr-animevideov3 "是最快、最准确的模型（推荐使用）。 
与 `realesrgan-x4plus-anime` 相比，它的边缘（分辨率）较低，但能干净利落地去除噪点，效果自然，同时相对保留了原始图像的细节。 
虽然 `realesrgan-x4plus` 更适合制作照片，但 `realesr-animevideov3` 也有相当不错的效果（会损失一些细节）。

如果对 `realesr-animevideov3` 的效果不满意，可以试试 `realesrgan-x4plus-anime` 。 
它能提供更高分辨率的完成效果，但往往会比 `realesr-animevideov3` 损失更多细节（不过如果不比较两者，是看不出区别的）。

`realesrgan-x4plus` 是一个可用于各种图像的模型，而不仅仅是插图和动画。 不过，在 Intel UHD Graphics 620 环境下，它的运行速度相当慢（花了好几分钟......）。 
即使使用相同的图像和 "realesrgan-x4plus"，在使用英伟达™（NVIDIA®）图形处理器的环境中生成放大图像也只需要几秒钟。 
这是一个通用模型，因此既可用于照片，也可用于插图，但对于动画，"realesrgan-x4plus-anime "生成的图像更像卡通。

### Real-CUGAN

<img width="600" src="https://user-images.githubusercontent.com/39271166/192086045-2c265db2-d8e0-4785-8297-e7585af53d3b.png">

一种专门用于插图和动画的人工智能图像放大算法。 
它比 Real-ESRGAN 的 "realesr-animevideov3 "慢，但能在放大图像的同时保留整个图像的细节。

不过，在动画捕获的情况下，我的印象是线条的颜色变得更暗，图像也往往比 `realesr-animevideov3` 更清晰。
其他细节当然会保留下来，但图像仍然很 "暗"，因此我认为 `realesr-animevideov3` 能为动画提供更好的效果。 

在绘制有大量渐变的插图时（不是动画绘制），细节和模糊度（锐利度）都能得到保持，这往往比容易破坏细节的 Real-ESRGAN 效果更好。 
不过，与真实-ESRGAN 相比，人工痕迹（部分图像失真）更容易出现，这可能是由于保留了细节的缘故。 这一点可以忽略不计，但...


另一项功能是指定降噪级别。 
将去噪级别设置为最大值，可以强力去除 JPEG 噪点，但细节会略有减少。 
请注意，只有在指定了 "models-se "模型时，降噪级别 1 和 2 才可用。

<img width="100%" src="https://user-images.githubusercontent.com/39271166/192088956-c386a241-4714-4a6d-9c78-b78faee8db8b.jpg">

本来，Real-CUGAN 完全不适合放大实景照片，如果不进行降噪处理，图像会变得各种糟糕。 
不过，**如果你敢于将低分辨率照片的尺寸调整到 600px 或更小，然后在将 Real-CUGAN 去噪级别设置为 3（最大值）的情况下将其放大，那么输出的图像将具有动漫背景般的细节。 **  
进一步的手动色彩校正会使图像看起来像卡通背景（关键是大幅降低对比度，增加高光和黑色，降低清晰度）。 
这可能还有其他用途，例如用作插图的背景。


#### 模型

推荐使用`models-pro`模型，因为它最精确。 
models-se "是一个比 "models-pro "更老的模型，但它提供了更大范围的放大和去噪级别。

models-nose "只能放大到两倍的放大倍率，但能生成具有纤细、锐利线条边缘的独特图像。 
不过，细节往往会丢失。

## 故障排除

### 无法启动，显示错误信息 "无法继续执行代码，因为未找到 MSVCP140.dll"。

[Visual C++ 可再分发软件包 2015-2022](https://docs.microsoft.com/ja-jp/cpp/windows/latest-supported-vc-redist?view=msvc-170) 需要安装。 
[vc_redist.x64.exe](https://aka.ms/vs/17/release/vc_redist.x64.exe) 然后双击下载的 `vc_redist.x64.exe` 进行安装。

安装完成后，再次双击 `Real-ESRGAN-GUI.exe` 即可正常启动。

### 将缩放因子设置为 [缩放至 2x 分辨率] [缩放至 3x 分辨率] 会破坏生成的图像。

可能是后端使用的 [realesrgan-ncnn-vulkan](https://github.com/xinntao/Real-ESRGAN-ncnn-vulkan) 中的错误或规范。 我们对此无能为力...  
需要注意的是，有时可以适当放大到两倍分辨率。 我的印象是，当 Real-ESRGAN 应用于原始分辨率较高的图像（如全高清）时，更有可能出现这种情况。

Real-ESRGAN 的开发前提似乎是它最初设计用于将图像放大 4 倍，因此如果这不起作用，请将其设置为 [放大至分辨率的 4 倍]，然后尝试使用图像编辑软件适当调整图像大小。

### 无法放大图像，显示错误 "放大图像失败"。

虽然很难说出确切的原因，因为有各种可能的原因，但第一种可能性是目标文件路径不正确（如文件夹不存在、路径规格不正确等）。

此外，如果 GPU 驱动程序版本过期，也可能出现问题，如无法生成图像或只能生成黑色图像。 
建议将 GPU 驱动程序更新到最新版本。

## 捐款和支持。

**目前我们只接受 [Amagif (亚马逊礼券)](https://www.amazon.co.jp/b?node=3131877051&tag=tsukumijima-22)。 **  

如果您仍然愿意捐款，请将 Amagif 的 URL 发送至 [Twitter 上的 DM（点击打开 DM）](https://twitter.com/messages/compose?recipient_id=) 1116800514614628352) 或 `tsukumizima at gmail.com`，这将是对我们发展的极大鼓励...... 🙏🙏🙏。

还有一个**[亚马逊愿望清单](https://www.amazon.co.jp/hz/wishlist/ls/3AZ4RI13SW2PV)。 ** 任何礼物都会让我们喜极而泣 ......😭🙏。

除此之外，您还可以点击链接**[这里](https://www.amazon.co.jp/?tag=tsukumijima-22)，然后在亚马逊（Amazon Associate）上购物来支持我们。 **  
您可以购买任何产品，但[推荐率（产品价格中给协理参与者的百分比）](https://affiliate.amazon.co.jp/help/node/topic/GRXPHT8U84RAYDXZ)越高，价格越高，我收到的钱就越多。 Kindle 电子书、食品和饮料的推荐率似乎更高。 

> 也许如果你从 GitHub 跳转到亚马逊，你可能会被[referrer](https://wa3.i-3-i.info/word129.html) 检查拒绝，所以复制并粘贴链接到新打开的标签页可能会更好。

## License

[MIT License](License.txt)
