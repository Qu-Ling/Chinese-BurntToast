# New-BurntToastNotification

## 作用

创建并显示 Toast 通知。

## 语法

### 指定提示声 (默认)

```powershell
New-BurntToastNotification [-Text <String[]>] [-AppLogo <String>] [-Sound <String>] [-Header <ToastHeader>] [-ProgressBar <AdaptiveProgressBar>]
```

### 静音提示

```powershell
New-BurntToastNotification [-Text <String[]>] [-AppLogo <String>] [-Silent] [-Header <ToastHeader>] [-ProgressBar <AdaptiveProgressBar>]
```

### 推迟与取消按钮

```powershell
New-BurntToastNotification [-Text <String[]>] [-AppLogo <String>] -SnoozeAndDismiss [-Header <ToastHeader>] [-ProgressBar <AdaptiveProgressBar>]
```

### 自定义按钮

```powershell
New-BurntToastNotification [-Text <String[]>] [-AppLogo <String>] -Button <IToastButton[]> [-Header <ToastHeader>] [-ProgressBar <AdaptiveProgressBar>]
```

### 静音，推迟与取消按钮

```powershell
New-BurntToastNotification [-Text <String[]>] [-AppLogo <String>] [-Silent] -SnoozeAndDismiss [-Header <ToastHeader>] [-ProgressBar <AdaptiveProgressBar>]
```

### 静音与自定义按钮

```powershell
New-BurntToastNotification [-Text <String[]>] [-AppLogo <String>] [-Silent] -Button <IToastButton[]> [-Header <ToastHeader>] [-ProgressBar <AdaptiveProgressBar>]
```

### 提示音，推迟与取消按钮

```powershell
New-BurntToastNotification [-Text <String[]>] [-AppLogo <String>] [-Sound <String>] -SnoozeAndDismiss [-Header <ToastHeader>] [-ProgressBar <AdaptiveProgressBar>]
```

### 提示音与自定义按钮

```powershell
New-BurntToastNotification [-Text <String[]>] [-AppLogo <String>] [-Sound <String>] -Button <IToastButton[]> [-Header <ToastHeader>] [-ProgressBar <AdaptiveProgressBar>]
```

## 描述

New-BurntToastNotification 函数在 Microsoft Windows 10 上创建并显示 Toast 通知。

您可以指定显示的文本和/或图像，以及选择在显示 Toast 通知时播放的声音。

您可以选择使用 Toast 别名调用 New-BurntToastNotification 函数。

## 案例

### -------------------------- 案例 1 --------------------------

```powershell
PS C:\>New-BurntToastNotification
```

此命令创建并显示具有所有默认值的 Toast 通知。

### -------------------------- 案例 2 --------------------------

```powershell
PS C:\>New-BurntToastNotification -Text 'Example Script', 'The example script has run successfully.'
```

此命令创建并显示具有自定义文本标题和文本内容的 Toast 通知。

### -------------------------- 案例 3 --------------------------

```powershell
PS C:\>New-BurntToastNotification -Text 'WAKE UP!' -Sound 'Alarm2'
```

此命令创建并显示 Toast 通知，该通知会播放循环警报声音，并且持续时间比默认 Toast 更长。


### -------------------------- 案例 4 --------------------------

```powershell
PS C:\>$BlogButton = New-BTButton -Content 'Open Blog' -Arguments 'https://king.geek.nz'
PS C:\>New-BurntToastNotification -Text 'New Blog Post!' -Button $BlogButton
```


此示例创建一个带有按钮的 Toast 通知，单击该按钮后将打开指向 [“https://king.geek.nz”]（https://king.geek.nz） 的链接。

### -------------------------- 案例 5 --------------------------

```powershell
PS C:\>$ToastHeader = New-BTHeader -Id '001' -Title 'Stack Overflow Questions'
PS C:\>New-BurntToastNotification -Text 'New Stack Overflow Question!', 'More details!' -Header $ToastHeader
```

此示例创建一个 Toast 通知，该通知将显示在通知头'Stack Overflow Questions'下。

### -------------------------- 案例 6 --------------------------

```powershell
PS C:\>$Progress = New-BTProgressBar -Status 'Copying files' -Value 0.2
PS C:\>New-BurntToastNotification -Text 'File copy script running', 'More details!' -ProgressBar $Progress
```

此示例创建一个 Toast 通知，其中将包含一个进度条。

### -------------------------- 案例 7 --------------------------

```powershell
PS C:\>New-BurntToastNotification -Text 'Professional Content', 'And gr8 spelling' -UniqueIdentifier 'Toast001'
PS C:\>New-BurntToastNotification -Text 'Professional Content', 'And great spelling' -UniqueIdentifier 'Toast001'
```

此示例将显示一个带有拼写错误的Text，该Toast将替换为第二个Toast，因为它们都共享一个唯一标识符。

## 参数

### -AppLogo 应用图标

指定图像的路径，该图像将覆盖 Toast 通知显示的默认图像。

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Button 按钮

最多允许将 5 个按钮添加到 Toast 通知的底部。这些按钮应使用 New-BTButton 函数创建。

>（翻译著：**自定义按钮不能与SnoozeAndDismiss一起使用**）

```yaml
Type: IToastButton[]
Parameter Sets: Custom Buttons, Silent and Custom Buttons, Sound and Custom Buttons
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Header 通知头

指定使用 New-BTHeader 函数创建的 Toast Header 对象，以便对来自同一AppId的Toast进行分离/分类。

Specify the Toast Header object created using the New-BTHeader function, for seperation/categorization of toasts from the same AppId.

```yaml
Type: ToastHeader
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProgressBar 进度条

指定使用 New-BTProgressBar函数创建的ProgressBar对象。

Specify the Progress Bar object created using the New-BTProgressBar function.

```yaml
Type: AdaptiveProgressBar
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Silent 静音提示

表示 Toast 通知将在屏幕上显示，且不伴有声音。

**不能与 'Sound' 参数一起使用**。

```yaml
Type: SwitchParameter
Parameter Sets: Silent, Silent and Snooze and Dismiss, Silent and Custom Buttons
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -SnoozeAndDismiss 推迟和关闭按钮

在 Toast 通知的底部添加 推迟 和 关闭按钮
>（翻译著：**自定义按钮不能与SnoozeAndDismiss一起使用**）

```yaml
Type: SwitchParameter
Parameter Sets: Snooze and Dismiss, Silent and Snooze and Dismiss, Sound and Snooze and Dismiss
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sound 提示音

选择要伴随 Toast 通知的声音。任何“闹钟”或“通知”的提示音都会自动循环播放，并延长 Toast 在屏幕上的显示时间。

**不能与Silent（静音）参数一起使用。**

>（翻译著：使用该参数记得开通知提示声音）

可选提示音：
- 'Default'
- 'IM'
- 'Mail'
- 'Reminder'
- 'SMS'
- 'Alarm'
- 'Alarm2'
- 'Alarm3'
- 'Alarm4'
- 'Alarm5'
- 'Alarm6'
- 'Alarm7'
- 'Alarm8'
- 'Alarm9'
- 'Alarm10'
- 'Call'
- 'Call2'
- 'Call3'
- 'Call4'
- 'Call5'
- 'Call6'
- 'Call7'
- 'Call8'
- 'Call9'
- 'Call10'

```yaml
Type: String
Parameter Sets: Sound
Aliases:

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Sound and Snooze and Dismiss, Sound and Custom Buttons
Aliases:

Required: True
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -Text 消息文本

指定要在 Toast 通知上显示的文本。最多可以显示三个字符串，其中第一个字符串将作为标题加粗。

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Default Notification
Accept pipeline input: False
Accept wildcard characters: False
```

### -UniqueIdentifier 更新标识符

唯一标识 Toast 通知的字符串。提交与上一个 Toast 具有相同标识符的新 Toast 时会替换旧的 Toast。

在更新进程进度、使用进度条或以其他方式更正/更新 toast 上的信息时，这非常有用。
>（翻译著：这个替换并非无缝替换，根据这个做动态进度条效果很差）

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value:
Accept pipeline input: False
Accept wildcard characters: False
```

## 输入

TODO

您不能通过管道将 input 传递给此函数。

You cannot pipe input to this function.

## 输出

TODO

New-BurntToastNotification 显示创建的 Toast 通知。

New-BurntToastNotification displays the Toast Notification that is created.

## 其他

我对 Parameter Sets 的数量感到*非常*抱歉。最好的解释是：
* 您不能同时指定声音和将 Toast 标记为静音。
* 您不能同时指定 SnoozeAndDismiss 和自定义按钮。

## 相关链接

[New-BurntToastNotification](https://github.com/Windos/BurntToast/blob/main/Help/New-BurntToastNotification.md)
