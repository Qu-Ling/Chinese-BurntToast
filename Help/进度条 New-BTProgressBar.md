# New-BTProgressBar

## 作用

为气泡通知创建一个新的进度条元素。

## 语法

### 静态进度 (默认)

```powershell
New-BTProgressBar [-Title <String>] -Status <String> -Value <Double> [-ValueDisplay <String>]
```

### 动态进度

```powershell
New-BTProgressBar [-Title <String>] -Status <String> -Indeterminate [-ValueDisplay <String>]
```

## 描述

New-BTProgressBar 函数为 气泡通知 创建一个新的进度条元素。

必须指定进度条的状态（status）和值（-value 或 --Indeterminate），还可以选择性地给进度条添加标题并覆盖进度的自动文本表示。

## 案例

### -------------------------- 案例 1 --------------------------

```powershell
PS C:\>New-BTProgressBar -Status 'Copying files' -Value 0.2
```

此命令创建一个填充了 20% 的进度条，当前状态为'Copying files'（正在复制文件），下方显示默认文本大小为20%。

### -------------------------- 案例 2 --------------------------

```powershell
PS C:\>New-BTProgressBar -Status 'Copying files' -Indeterminate
```

此命令创建一个具有动态动画的进度条，而不是填充到一定百分比的条。

### -------------------------- 案例 3 --------------------------

```powershell
PS C:\>New-BTProgressBar -Status 'Copying files' -Value 0.2 -ValueDisplay '4/20 files complete'
```

此命令创建一个填充了 20% 的进度条，当前状态为'Copying files'，默认文本被覆盖为'4/20 files complete'。

### -------------------------- 案例 4 --------------------------

```powershell
PS C:\>New-BTProgressBar -Title 'File Copy' -Status 'Copying files' -Value 0.2
```

此示例创建一个填充了 20% 的进度条，当前状态为'Copying files'，下方显示默认文本 20%。

进度条显示在标题'File Copy'之下。

## 参数

### -Title 标题

显示在进度条左上方的文本。通常用于说明进度条所代表的内容。

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Names
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status 进度状态

显示在进度条左下方的文本。用于显示正在执行的操作的当前状态。

示例包括：运行、暂停、停止、完成。

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Indeterminate 动态加载动画

当完成的百分比未知时使用。结果进度条会显示系统生成的动画，而不是填充的条。

不能与设置的 Value 同时使用。

```yaml
Type: SwitchParameter
Parameter Sets: Indeterminate
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value 进度值

指定以双精度浮点数表示的进度条填充百分比，介于 0 和 1（含）之间。

例如，0.4 表示 40%，1 表示 100%。

```yaml
Type: Double
Parameter Sets: Determinate
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ValueDisplay 进度文本展示

将 默认的百分比 替换为 输入的文本 展示在进度条的右下方。

例如，参数-Value 0.2 时，该参数的默认文本为“20%”，此参数可将该文本替换为你自定义的内容。

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

## INPUTS 输入框

字符串

无法将输入管道传输到此 cmdlet。

## OUTPUTS 输出

AdaptiveProgressBar

## NOTES 其他

## RELATED LINKS 相关链接

[New-BTProgressBar](https://github.com/Windos/BurntToast/blob/main/Help/New-BTProgressBar.md)
