# BurntToast 帮助
## 描述
用于在 Microsoft Windows 10 上创建和显示 气泡通知的模块

## BurntToast 函数
### [New-BTAction](New-BTAction.md)
New-BTAction 函数创建一个“操作”对象，其中定义了显示在 Toast 通知底部的控件。

操作可以是系统处理并自动本地化的“稍后提醒”和“关闭”按钮，也可以是自定义的输入集合。

### [New-BTAppId](New-BTAppId.md)
New-BTAppId 函数在当前用户的注册表项中创建一个新的 AppId 注册表键。如果所需的 AppId 已经存在于注册表中，则不会进行任何更改。

如果没有指定 AppId，则使用 BurntToast 模块根目录中的 config.json 文件中指定的 AppId。

### [New-BTAudio](New-BTAudio.md)
New-BTAudioElement 函数为 Toast 通知创建一个新的音频元素。

你可以使用 New-BTAudioElement 的参数来选择音频文件或标准通知声音（包括警报）。或者，你可以指定 Toast 通知应为静音。

### [New-BTBinding](New-BTBinding.md)
New-BTBinding 函数创建一个新的通用 Toast 绑定，你可以在其中提供文本、图像和其他视觉元素用于你的 Toast 通知。

### [New-BTButton](New-BTButton.md)
New-BTButton 函数为 Toast 通知创建一个新的可点击按钮。一个 Toast 最多可以添加五个按钮。

按钮可以完全自定义显示文本、图像和参数，或者使用系统处理的“稍后提醒”和“关闭”按钮。

### [New-BTContextMenuItem](New-BTContextMenuItem.md)
New-BTContextMenuItem 函数创建一个上下文菜单项对象。

### [New-BTHeader](New-BTHeader.md)
New-BTHeader 函数为 Toast 通知创建一个新的通知标题。

这些标题显示在 Toast 的顶部，并且也用于在操作中心对 Toast 进行分类。

### [New-BTImage](New-BTImage.md)
New-BTImageElement 函数为 Toast 通知创建一个新的图像元素。

你可以使用 New-BTImageElement 的参数来指定源图像、备用文本、在 Toast 通知中的放置位置和裁剪形状。

### [New-BTInput](New-BTInput.md)
New-BTInput 函数在 Toast 通知上创建一个输入元素。

返回的对象可以是用户输入文本的文本框，也可以是用户从选项列表中选择的下拉框。

### [New-BTProgressBar](New-BTProgressBar.md)
New-BTProgressBar 函数为 Toast 通知创建一个新的进度条元素。

你必须指定进度条的状态和值，并且可以可选地给进度条一个标题，或者覆盖进度的自动文本表示。

### [New-BTSelectionBoxItem](New-BTSelectionBoxItem.md)
New-BTSelectionBoxItem 函数创建一个选择框项，用于 New-BTInput 创建的选择框中。

### [New-BTText](New-BTText.md)
New-BTTextElement 函数为 Toast 通知创建一个新的文本元素。

你可以指定要在 Toast 通知中显示的文本为字符串，或者在不带参数的情况下运行该函数以获取空白行。

每个文本元素相当于 Toast 通知中的一行，长行会自动换行。

### [New-BTVisual](New-BTVisual.md)
New-BTVisual 函数为 Toast 通知创建一个新的视觉元素，该元素定义了 Toast 的所有视觉方面。

### [New-BurntToastNotification](New-BurntToastNotification.md)
New-BurntToastNotification 函数在 Microsoft Windows 10 上创建并显示一个 Toast 通知。

你可以指定显示的文本和/或图像，以及选择显示 Toast 通知时播放的声音。

你可以选择使用 Toast 别名调用 New-BurntToastNotification 函数。

### [Submit-BTNotification](Submit-BTNotification.md)
Submit-BTNotification 函数将完成的 Toast 通知提交给操作系统的通知管理器进行显示。
