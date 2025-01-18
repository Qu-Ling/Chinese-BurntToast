# New-BTButton

## 作用

Creates a new clickable button for a Toast Notification.

## 语法

### 普通按钮 (默认)

```powershell
New-BTButton -Content <String> -Arguments <String> [-ActivationType {Foreground | Background | Protocol}] [-ImageUri <String>] [-Id <String>]
```

### 延迟按钮

```powershell
New-BTButton -Snooze [-Content <String>] [-Id <String>]
```

### 取消按钮

```powershell
New-BTButton -Dismiss [-Content <String>]
```

## 描述

New-BTButton 函数为 Toast 通知创建一个新的可单击按钮。

一个 Toast 最多有5个按钮。

按钮可以自定义显示文本、图像和参数或系统处理的 延迟和取消 按钮。

## 案例

### -------------------------- 案例 1 --------------------------

```powershell
PS C:\>New-BTButton -Dismiss
```

此命令将创建一个按钮，该按钮模拟单击时“滑走”Toast 的操作。

### -------------------------- 案例 2 --------------------------

```powershell
PS C:\>New-BTButton -Snooze
```

此命令将创建一个按钮，该按钮将在系统默认的推迟时间（通常为 10 分钟）后再次弹出 Toast。

### -------------------------- 案例 3 --------------------------

```powershell
PS C:\>New-BTButton -Snooze -Content 'Sleep' -Id 'TimeSelection'
```

此命令将创建一个按钮，该按钮将在 ID 为 'TimeSelection' 的 SelectionBox 中选择的推迟 Toast。该按钮将显示文本“Sleep”而不是“推迟”。

### -------------------------- 案例 4 --------------------------

```powershell
PS C:\>New-BTButton -Content 'Blog' -Arguments 'https://king.geek.nz'
```

此命令会创建一个显示文本为 “Blog” 的按钮，点击该按钮后将启动一个浏览器窗口并跳转到 [https://king.geek.nz](https://king.geek.nz)

### -------------------------- 案例 5 --------------------------

```powershell
PS C:\>$Picture = 'C:\temp\example.png'
PS C:\>New-BTButton -Content 'View Picture' -Arguments $Picture -ImageUri $Picture
```

此示例创建一个显示文本为“View Picture”的按钮，左侧有一张图片，该按钮将启动默认的图片查看器应用程序，并在单击时加载图片。

## 参数

### -ActivationType 操作类型

定义按下按钮时触发的 ActivationType。

默认为 Protocol，它将在 rlevant 系统默认应用程序中打开 Arguments 参数指定的文件或 URI。

(翻译著:

Protocol：默认值。当按钮被点击时，将使用系统默认的应用程序打开 Arguments 参数指定的文件或 URI;

Foreground：当按钮被点击时，将激活应用程序的前台实例，并传递 Arguments 参数;

Background：当按钮被点击时，将激活应用程序的后台任务，并传递 Arguments 参数;)


```yaml
Type: ToastActivationType
Parameter Sets: Button
Aliases:
Accepted values: Foreground, Background, Protocol

Required: False
Position: Named
Default value: Protocol
Accept pipeline input: False
Accept wildcard characters: False
```

### -Arguments 指定路径

指定应用程序定义的字符串。

对于 BurntToast 通知，这通常是文件或 URI 的路径，并与协议 ActivationType 配对。

```yaml
Type: String
Parameter Sets: Button
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Content 名称

指定要在按钮上显示的文本。

```yaml
Type: String
Parameter Sets: Button
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Snooze, Dismiss
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Dismiss 取消

指定系统处理的关闭按钮。单击生成的按钮与“滑走”或以其他方式关闭 Toast 的效果相同。

显示文本默认为本地化的“Dismiss”，但这可以用 Content 参数覆盖。

```yaml
Type: SwitchParameter
Parameter Sets: Dismiss
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id 

指定相关 Toast 控件的 ID。

标准按钮可以与文本框对齐，使按钮显示在其右侧。

推迟按钮可以与选择框配对，以选择要推迟的时间长度。

```yaml
Type: String
Parameter Sets: Button, Snooze
Aliases: TextBoxId, SelectionBoxId

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ImageUri 图片URI

指定要在按钮上显示的图像图标。

```yaml
Type: String
Parameter Sets: Button
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Snooze 推迟

指定系统处理的贪睡按钮。 当与选择框配对时，打盹时间是可定制的，用户可选择的，否则使用系统默认的打盹时间。
显示文本默认为本地化的"推迟"，但这可以用 Content 参数覆写

```yaml
Type: SwitchParameter
Parameter Sets: Snooze
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## 输入

TODO

You cannot pipe input to this function.

## 输出

Microsoft.Toolkit.Uwp.Notifications.ToastButton

Microsoft.Toolkit.Uwp.Notifications.ToastButtonDismiss

Microsoft.Toolkit.Uwp.Notifications.ToastButtonSnooze

## 其他

## 相关链接

[New-BTButton](https://github.com/Windos/BurntToast/blob/main/Help/New-BTButton.md)
