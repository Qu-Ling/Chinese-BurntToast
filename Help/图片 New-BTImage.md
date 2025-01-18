# New-BTImage

## 作用

为 Toast 通知创建新的图像元素。

## 语法

### 普通图片 (默认)

```powershell
New-BTImage [-Source <String>] [-AlternateText <String>] [-Align <AdaptiveImageAlign>]
 [-Crop <AdaptiveImageCrop>] [-RemoveMargin] [-AddImageQuery]
```

### 应用图标

```powershell
New-BTImage [-Source <String>] [-AlternateText <String>] [-AppLogoOverride] [-Crop <AdaptiveImageCrop>]
 [-AddImageQuery]
```

### 背景图片

```powershell
New-BTImage [-Source <String>] [-AlternateText <String>] [-HeroImage] [-AddImageQuery]
```

## 描述

New-BTImageElement 函数为 Toast 通知创建新的图像元素。

您可以使用 New-BTImageElement 的参数来指定图片、图片的替换文本、在 Toast 通知上的位置（主页图片，通知图标，主体图片）以及裁剪形状。

## 案例
### -------------------------- 案例 1 --------------------------

```powershell
PS C:\>$image1 = New-BTImage -Source 'C:\Media\BurntToast.png'
```

此命令将创建一个要包含在 Toast 主体中的标准图片对象。

### -------------------------- 案例 2 --------------------------

```powershell
PS C:\>$image2 = New-BTImage -Source 'C:\Media\BurntToast.png' -AppLogoOverride -Crop Circle
```

此命令将指定一个图片用作 Toast 上的通知图标，并裁剪为圆形。

### -------------------------- 案例 3 --------------------------

```powershell
PS C:\>$image3 = New-BTImage -Source 'C:\Media\BurntToast.png' -HeroImage
```

此命令将指定一个图片用作 Toast 的主页图像。

## 参数

### -AddImageQuery 添加图片查询

设置为 true 以允许 Windows 将查询字符串附加到 Tile 通知中提供的图像 URI。如果您的服务器托管图像并且可以处理查询字符串，请使用此属性，方法是根据查询字符串检索图像变体，或者忽略查询字符串并返回指定的图像（不含查询字符串）。此查询字符串指定比例、对比度设置和语言。

>(翻译著：简单来说，选择此参数后会生成该图片的一些信息，系统可以通过这些信息处理图片，或者应该翻译成：添加图片信息 更好理解)

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

### -Align 水平对齐图片

图像的水平对齐方式。对于 Toast，仅在组内（尚未实现）时支持此功能。

```yaml
Type: AdaptiveImageAlign
Parameter Sets: Image
Aliases:
Accepted values: Default, Stretch, Left, Center, Right

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AlternateText 替代文本

图像的描述，适用于辅助技术的用户。

>(翻译著：当图片不能正常展示时，会展示该文本)

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

### -AppLogoOverride 覆盖应用图标

指定将图片用作 Toast 上的图标。

>(翻译著：如果不指定图标，用powershell执行的话，会是powershell的图标)

```yaml
Type: SwitchParameter
Parameter Sets: AppLogo
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Crop 裁剪

控制所需的图像裁剪。自Win10的周年更新以来在 Toast 上受支持。

```yaml
Type: AdaptiveImageCrop
Parameter Sets: Image, AppLogo
Aliases:
Accepted values: Default, None, Circle

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HeroImage 主页图片

指定将图像用作 toast 上的主页图片。

```yaml
Type: SwitchParameter
Parameter Sets: Hero
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveMargin 边缘裁剪

默认情况下，图像周围有 8px 的边距。您可以通过包含此开关来删除此边距。自Win10的周年更新以来在 Toast 上受支持。

```yaml
Type: SwitchParameter
Parameter Sets: Image
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source 图片路径

图像的 URI。可以来自您的应用程序包、应用程序数据或网络。网络图片的大小必须小于 200 KB。

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $Script:DefaultImage
Accept pipeline input: False
Accept wildcard characters: False
```

## 输入

TODO

## 输出

AdaptiveImage

ToastGenericAppLogo

ToastGenericHeroImage

## 其他
Credit for most of the help text for this function go to the authors of the UWPCommunityToolkit library that this module relies upon.

Please see the [originating repo](https://github.com/Microsoft/UWPCommunityToolkit).

## 相关链接

[New-BTImage](https://github.com/Windos/BurntToast/blob/main/Help/New-BTImage.md)
