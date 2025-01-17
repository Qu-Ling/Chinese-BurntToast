# New-BTImage

## 作用

为气泡通知创建一个新的图像元素。

## 语法

### 图片 (默认)

```powershell
New-BTImage [-Source <String>] [-AlternateText <String>] [-Align <AdaptiveImageAlign>]
 [-Crop <AdaptiveImageCrop>] [-RemoveMargin] [-AddImageQuery]
```

### 应用图标

```powershell
New-BTImage [-Source <String>] [-AlternateText <String>] [-AppLogoOverride] [-Crop <AdaptiveImageCrop>]
 [-AddImageQuery]
```

### 主页图片

```powershell
New-BTImage [-Source <String>] [-AlternateText <String>] [-HeroImage] [-AddImageQuery]
```

## 描述

New-BTImageElement 函数为气泡通知创建一个新的图像元素。

你可以使用 New-BTImageElement 的参数来指定源图像、备用文本、在 Toast 通知中的放置位置和裁剪形状。

## 案例

### -------------------------- 案例 1 --------------------------

```powershell
PS C:\>$image1 = New-BTImage -Source 'C:\Media\BurntToast.png'
```

此命令创建一个标准图像对象，用于包含在 气泡 的主体中。

### -------------------------- 案例 2 --------------------------

```powershell
PS C:\>$image2 = New-BTImage -Source 'C:\Media\BurntToast.png' -AppLogoOverride -Crop Circle
```

此命令创建一个图像对象，作为气泡中左边的图片，裁剪成圆形。

### -------------------------- 案例 3 --------------------------

```powershell
PS C:\>$image3 = New-BTImage -Source 'C:\Media\BurntToast.png' -HeroImage
```

此命令创建一个图像，用作 气泡 的主页图像。

## 参数

### -AddImageQuery 添加图片查询

Set to true to allow Windows to append a query string to the image URI supplied in the Tile notification. Use this attribute if your server hosts images and can handle query strings, either by retrieving an image variant based on the query strings or by ignoring the query string and returning the image as specified without the query string. This query string specifies scale, contrast setting, and language.

设置为true，以允许Windows向磁贴通知中提供的图像URI追加查询字符串。如果您的服务器托管图像并能处理查询字符串，请使用此属性。无论是通过查询字符串获取图像变体，还是忽略查询字符串并按指定返回图像，都可以。这个查询字符串指定了缩放比例、对比度设置和语言。

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

图像的水平对齐方式。对于 气泡 通知，仅在位于分组内时支持此设置（尚未实现。）

The horizontal alignment of the image. For Toast, this is only supported when inside a group (not yet implemented.)


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

### -AlternateText 图片描述

图像的描述，适用于辅助技术的用户。

（编译著：-AlternateText 参数用于指定当图片由于大小或其他原因无法显示时，气泡通知会显示该参数输入的替代文本。）

A description of the image, for users of assistive technologies.


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

### -AppLogoOverride

指定将图像用作 气泡 上的图标。
（编译著：-AppLogoOverride 参数不是BurntToast通知库的标准参数。如果你想要使用自定义图标，应该使用 -AppLogo 参数）

Specifies that the image is to be used as the logo on the toast.

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

### -Crop 裁剪形状

控制所需的图像裁剪。自Windows10周年更新以来在 气泡 上受支持

（编译著：截止目前翻译版本貌似没有什么用？）

Control the desired cropping of the image. Supported on Toast since Anniversary Update.

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

指定将图像用作 气泡 上的主图图像。

Specifies that the image is to be used as the hero image on the toast.

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

### -RemoveMargin 删除边缘

默认情况下，图像周围有 8px 的边距。您可以通过包含此开关来删除此边距。自Windows10周年更新以来在 Toast 上受支持。

By default, images have an 8px margin around them. You can remove this margin by including this switch. Supported on Toast since Anniversary Update.

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

### -Source 图像路径

图像的 URI。可以来自您的应用程序包、应用程序数据或 网络。网络图片的大小必须小于 200 KB。

The URI of the image. Can be from your application package, application data, or the internet. Internet images must be less than 200 KB in size.

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

TODO 待做

## 输出

AdaptiveImage

ToastGenericAppLogo

ToastGenericHeroImage

## 其他
此函数的大部分帮助文本都归功于本模块所依赖的 UWPCommunityToolkit 库的作者。

详情请见 [originating repo](https://github.com/Microsoft/UWPCommunityToolkit).

## 相关链接

[New-BTImage](https://github.com/Windos/BurntToast/blob/main/Help/New-BTImage.md)
