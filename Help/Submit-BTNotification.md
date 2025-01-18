# Submit-BTNotification

## 作用

提交已完成的 气泡 通知以供显示。

## 语法

```powershell
Submit-BTNotification [[-Content] <ToastContent>] [[-SequenceNumber] <UInt64>] [[-UniqueIdentifier] <String>] [[-AppId] <String>]
```

## 描述

Submit-BTNotification 函数会将已有的 气泡 通知提交到操作系统的通知管理器进行显示。

## 案例

### -------------------------- 案例 1 --------------------------

```powershell
PS C:\>Submit-BTNotification -Content $Toast1 -UniqueIdentifier 'Toast001'
```

此命令从 New-BTContent 函数提交完整的 气泡 内容对象 $Toast 1，并使用唯一标识符对其进行标记，以便可以替换/更新它。

## 参数

### -AppId 

Specifies the AppId of the 'application' or process that spawned the toast notification.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: $Script:Config.AppId
Accept pipeline input: False
Accept wildcard characters: False
```

### -Content 内容

一个 Toast Content 对象，它是使用 New-BTContent 函数创建的 Base Toast 元素。

```yaml
Type: ToastContent
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SequenceNumber

快速更新 Toast （当前未正常工作） 时，序列号有助于确保不按顺序接收的 Toast 不会以可能混淆的方式显示。

序列号越高，表示 toast 越新。

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UniqueIdentifier 唯一标识符

唯一标识 Toast 通知的字符串。提交与上一个 Toast 具有相同标识符的新 Toast 将替换上一个 Toast。

在更新进程进度、使用进度栏或以其他方式更正/更新 toast 上的信息时，这非常有用。

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

TODO

## OUTPUTS

None

## NOTES

## RELATED LINKS

[Submit-BTNotification](https://github.com/Windos/BurntToast/blob/main/Help/Submit-BTNotification.md)
