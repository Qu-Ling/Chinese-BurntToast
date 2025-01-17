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

When updating toasts (not curently working) rapidly, the sequence number helps to ensure that toasts recieved out of order will not be displayed in a manner that may confuse.

A higher sequence number indicates a newer toast.

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

### -UniqueIdentifier

A string that uniquely identifies a toast notification. Submitting a new toast with the same identifier as a previous toast will replace the previous toast.

This is useful when updating the progress of a process, using a progress bar, or otherwise correcting/updating the information on a toast.

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
