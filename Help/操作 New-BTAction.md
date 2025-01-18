# New-BTAction

## SYNOPSIS

为 Toast 通知创建一个操作对象。

## 语法

### 自定义操作 (默认)

```powershell
New-BTAction [[-Buttons] <IToastButton[]>] [[-ContextMenuItems] <ToastContextMenuItem[]>] [[-Inputs] <IToastInput[]>]
```

### 延迟和取消

```powershell
New-BTAction -SnoozeAndDismiss
```

## 描述

New-BTAction 函数创建一个 'action' 对象，其中包含定义显示在 Toast 通知底部的控件。

操作可以是系统手动的、自动本地化的延迟和取消按钮，也可以是自定义的输入集合。

## 案例

### -------------------------- 案例 1 --------------------------

```powershell
PS C:\>New-BTAction -SnoozeAndDismiss
```

此命令使用系统处理的 snooze 和 dismiss 模式创建一个操作元素。


### -------------------------- 案例 2 --------------------------

```powershell
PS C:\>New-BTAction -Buttons (New-BTButton -Content 'Google' -Arguments 'https://google.com')
```

此命令将创建一个具有可单击按钮的 action 元素。
该元素显示为Google，点击后将跳转至谷歌界面

### -------------------------- 案例 3 --------------------------

```powershell
PS C:\>$Button = New-BTButton -Content 'Google' -Arguments 'https://google.com'
PS C:\>$ContextMenuItem = New-BTContextMenuItem -Content 'Bing' -Arguments 'https://bing.com'
PS C:\>New-BTAction -Buttons $Button -ContextMenuItems $ContextMenuItem
```

此示例创建一个可左键单击跳转按钮和右键单击展示 菜单 的动作。

## 参数

### -Buttons 按钮

使用 New-BTButton 函数创建的 Button 对象。

一个 Toset 最多可包含5个ContextMenuItems和Button对象。

>(翻译著：也就是ContextMenuItems和Button加起来不超过五个)

```yaml
Type: IToastButton[]
Parameter Sets: Custom Actions
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContextMenuItems 菜单选项

右键单击 Toset 使用 New-BTContextMenuItem 函数创建的菜单对象。

一个 Toset 最多可包含5个ContextMenuItems和Button对象。

>(翻译著：也就是ContextMenuItems和Button加起来不超过五个)

```yaml
Type: ToastContextMenuItem[]
Parameter Sets: Custom Actions
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Inputs 输入框

可以输入 New-BTText或New-BTSelectionBoxItem 函数创建的对象。

一个 Toset 最多可包含5个输入框。

```yaml
Type: IToastInput[]
Parameter Sets: Custom Actions
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SnoozeAndDismiss 延迟和取消

创建系统手动推迟和关闭操作。不能与自定义操作一起使用。

```yaml
Type: SwitchParameter
Parameter Sets: SnoozeAndDismiss
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

Microsoft.Toolkit.Uwp.Notifications.IToastActions

## 其他

## 相关链接

[New-BTAction](https://github.com/Windos/BurntToast/blob/main/Help/New-BTAction.md)
