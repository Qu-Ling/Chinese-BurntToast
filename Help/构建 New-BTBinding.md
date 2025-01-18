# New-BTBinding

## 作用

创建新的通用Toast绑定对象。

## 语法

```powershell
New-BTBinding [[-Children] <IToastBindingGenericChild[]>] [-AddImageQuery]
 [[-AppLogoOverride] <ToastGenericAppLogo>] [[-Attribution] <ToastGenericAttributionText>] [[-BaseUri] <Uri>]
 [[-HeroImage] <ToastGenericHeroImage>] [[-Language] <String>]
```

## 描述

New-BTBinding 函数创建一个新的通用 Toast 绑定，您可以在其中为 Toast 通知提供文本、图像和其他视觉元素。

## 案例

### -------------------------- 案例 1 --------------------------

```powershell
PS C:\>$text1 = New-BTText -Content 'This is a test'
PS C:\>$text2 = New-BTText
PS C:\>$text3 = New-BTText -Content 'This more testing'
PS C:\>$progress = New-BTProgressBar -Title 'Things are happening' -Status 'Working on it' -Value 0.01
PS C:\>$image1 = New-BTImage -Source 'C:\BurntToast\Media\BurntToast.png'
PS C:\>$image2 = New-BTImage -Source 'C:\BurntToast\Media\BurntToast.png' -AppLogoOverride -Crop Circle
PS C:\>$image3 = New-BTImage -Source 'C:\BurntToast\Media\BurntToast.png' -HeroImage
PS C:\>$binding1 = New-BTBinding -Children $text1, $text2, $text3, $image1, $progress -AppLogoOverride $image2 -HeroImage $image3
```

此示例使用各种 BurntToast 函数创建多个对象，然后使用它们作为输入创建泛型 Toast 绑定。

## 参数

### -AddImageQuery 添加图片查询

设置为“true”以允许 Windows 将查询字符串附加到 Toast 通知中提供的图像 URI。如果您的服务器托管图像并且可以处理查询字符串，请使用此属性，方法是根据查询字符串检索图像变体，或者忽略查询字符串并返回指定的图像（不含查询字符串）。此查询字符串指定比例、对比度设置和语言。

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

### -AppLogoOverride 覆盖通知图标

Toast 通知上显示的图标的可选覆盖。
后跟带有'-AppLogoOverride'的New-BTImage对象。

```yaml
Type: ToastGenericAppLogo
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Attribution 归属文本

Win10的周年更新中的新增功能：显示为属性文本的可选文本元素。

在没有Win10的周年更新的设备上，此文本将像另一个 Text 元素一样显示在 Children 列表的末尾。

>(翻译著：不知为什么，该参数在目前翻译版本好像无法被识别使用)

```yaml
Type: ToastGenericAttributionText
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BaseUri 基本路径

如果图片路径为相对路径，则会在该基本路径下查找对应图片。

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Children 子元素

Toast 正文的内容，可以包括文本 （New-BTText）、图像 （New-BTImage）、组（尚未实现）和进度条 （New-BTProgressBar）。

此外，Text 元素必须位于任何其他元素之前。如果 Text 元素放在任何其他元素之后，则当您尝试检索 Toast XML 内容时，将引发异常。

最后，某些 Text 属性（如 HintStyle）在根子文本元素上不受支持，并且仅在 Group 内工作。如果您在没有Win10周年更新的设备上使用组，则组内容将被直接删除。

```yaml
Type: IToastBindingGenericChild[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HeroImage 主页图片

周年更新中的新增功能：可选的主页图像（显示在 Toast 通知上的具有视觉冲击力的图像）。

在没有周年更新的设备上，主图图像将被忽略。

>(翻译著：需要添加有-HeroImage的图片元素)

```yaml
Type: ToastGenericHeroImage
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Language 语言

The target locale of the XML payload, specified as BCP-47 language tags such as "en-US" or "fr-FR". This locale is overridden by any locale specified in binding or text. If this value is a literal string, this attribute defaults to the user's UI language. If this value is a string reference, this attribute defaults to the locale chosen by Windows Runtime in resolving the string.

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

## 输入

TODO

## 输出

ToastBindingGeneric

## 其他

此函数的大部分帮助文本都归功于本模块所依赖的 UWPCommunityToolkit 库的作者。

请看 [originating repo](https://github.com/windows-toolkit/WindowsCommunityToolkit).

## 相关链接

[New-BTBinding](https://github.com/Windos/BurntToast/blob/main/Help/New-BTBinding.md)
