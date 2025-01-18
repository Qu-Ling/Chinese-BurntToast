# New-BTText

## 作用

为 Toast 通知创建新的文本元素。

## 语法

```powershell
New-BTText [[-Text] <String>] [[-MaxLines] <Int32>] [[-MinLines] <Int32>] [-Wrap]
 [[-Align] <AdaptiveTextAlign>] [[-Style] <AdaptiveTextStyle>] [[-Language] <String>]
```

## 描述

New-BTTextElement 函数为 Toast 通知创建新的文本元素。

您可以将要在 Toast 通知中显示的文本指定为字符串，也可以运行不带空行参数的函数。

每个文本元素相当于 Toast 通知上的一行，长行将换行。

>(翻译著：且第一行会默认加粗）

## 案例

### -------------------------- 案例 1 --------------------------

```powershell
PS C:\>New-BTText -Content 'This is a line with text!'
```

创建一个文本元素，该元素将在 Toast 通知上显示字符串 'This is a line with text！'

### -------------------------- 案例 2 --------------------------

```powershell
PS C:\>New-BTText
```

创建一个文本元素，该元素将在 Toast 通知上显示空行。

## 参数

### -Align 水平对齐

文本的水平对齐方式。请注意，对于 Toast，此属性仅在文本位于组内（尚未实现）时生效。

```yaml
Type: AdaptiveTextAlign
Parameter Sets: (All)
Aliases:
Accepted values: Default, Auto, Left, Center, Right

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Language 语言

XML 负载的目标区域设置，指定为 BCP-47 语言标记，如“en-US”或“fr-FR”。此处指定的区域设置将覆盖任何其他指定的区域设置，例如 binding 或 visual 中的区域设置。如果此值是文本字符串，则此属性默认为用户的 UI 语言。如果此值是字符串引用，则此属性默认为 Windows 运行时在解析字符串时选择的区域设置。

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxLines 最大行数

允许文本元素显示的最大行数。对于 Toast，顶级文本元素将具有不同的最大行数（在Win10的周年更新中，您可以更改最大行数）。

组内 Toast 上的文本（尚未实现）的行为将与 Tiles 相同（默认为无穷大）。

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinLines 最小行数

文本元素必须显示的最小行数。请注意，对于 Toast，此属性仅在文本位于组内（尚未实现）时生效。

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -Style 样式

该样式控制文本的字体大小、粗细和不透明度。请注意，对于 Toast，仅当文本位于组内（尚未实现）时，该样式才会生效。

```yaml
Type: AdaptiveTextStyle
Parameter Sets: (All)
Aliases:
Accepted values: Default, Caption, CaptionSubtle, Body, BodySubtle, Base, BaseSubtle, Subtitle, SubtitleSubtle, Title, TitleSubtle, TitleNumeral, Subheader, SubheaderSubtle, SubheaderNumeral, Header, HeaderSubtle, HeaderNumeral

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Text 文本

要显示的文本。在 Creators Update 中添加的数据绑定支持仅适用于 toast 顶级文本元素（但似乎尚未通过 PowerShell 工作）。

```yaml
Type: String
Parameter Sets: (All)
Aliases: Content

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wrap

{{填充换行描述}}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## 输入

String

You cannot pipe input to this function.

## 输出

AdaptiveText

## 其他

TODO: Implement [hint-style](https://blogs.msdn.microsoft.com/tiles_and_toasts/2015/06/30/adaptive-tile-templates-schema-and-documentation/)

Credit for most of the help text for this function go to the authors of the UWPCommunityToolkit library that this module relies upon.

Please see the [originating repo](https://github.com/Microsoft/UWPCommunityToolkit)

## 相关链接

[New-BTText](https://github.com/Windos/BurntToast/blob/main/Help/New-BTText.md)
