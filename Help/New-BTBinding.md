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

### Attribution 

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

### -BaseUri 基础路径

与图片路径中的 相对URI 组合的 默认基本URI。

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

### -Children

The contents of the body of the Toast, which can include Text (New-BTText), Image (New-BTImage), Group (not yet implemented), and Progress Bar (New-BTProgressBar).

Also, Text elements must come before any other elements. If a Text element is placed after any other element, an exception will be thrown when you try to retrieve the Toast XML content.

And finally, certain Text properties like HintStyle aren't supported on the root children text elements, and only work inside a Group. If you use Group on devices without the Anniversary Update, the group content will simply be dropped.

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

### -HeroImage

New in Anniversary Update: An optional hero image (a visually impactful image displayed on the Toast notification).

On devices without the Anniversary Update, the hero image will simply be ignored.

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

### -Language

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

## INPUTS

TODO

## OUTPUTS

ToastBindingGeneric

## NOTES

Credit for most of the help text for this function go to the authors of the UWPCommunityToolkit library that this module relies upon.

Please see the Please see the [originating repo](https://github.com/windows-toolkit/WindowsCommunityToolkit).

## RELATED LINKS

[New-BTBinding](https://github.com/Windos/BurntToast/blob/main/Help/New-BTBinding.md)
