# New-BTVisual

## 作用

为 Toast 通知创建新的视觉元素。

## 语法

```powershell
New-BTVisual [-BindingGeneric] <ToastBindingGeneric> [-AddImageQuery] [[-BaseUri] <Uri>]
 [[-Language] <String>]
```

## 描述

New-BTVisual 函数为 Toast 通知创建一个新的视觉元素，该元素定义 Toast 的所有视觉方面。

## 案例

### -------------------------- 案例 1 --------------------------

```powershell
PS C:\>New-BTVisual -BindingGeneric $Binding1
```

此命令将使用一个构建（Binding）元素，创建一个新的 Visual 元素

## 参数

### -AddImageQuery 添加图片查询

指定此开关可允许 Windows 将查询字符串附加到 Toast 通知中提供的图像 URI。如果您的服务器托管图像并且可以处理查询字符串，请使用此属性，方法是根据查询字符串检索图像变体，或者忽略查询字符串并返回指定的图像（不含查询字符串）。此查询字符串指定比例、对比度设置和语言。

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

### -BaseUri 基础路径

如果图片路径为相对路径，则会在该基本路径下查找对应图片。

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BindingGeneric 绑定构建元素

通用 Toast 绑定，可在所有设备上呈现。此绑定元素是使用 New-BTBinding 函数创建的。

```yaml
Type: ToastBindingGeneric
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Language 语言

XML 负载的目标区域设置，指定为 BCP-47 语言标记，如“en-US”或“fr-FR”。此区域设置将被 binding 或 text 中指定的任何区域设置覆盖。如果此值是文本字符串，则此属性默认为用户的 UI 语言。如果此值是字符串引用，则此属性默认为 Windows 运行时在解析字符串时选择的区域设置。

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

## 输入

None

## 输出

ToastVisual

## 其他

此函数的大部分帮助文本都归功于本模块所依赖的 UWPCommunityToolkit 库的作者。

请参阅 [originating repo](https://github.com/Microsoft/UWPCommunityToolkit).

## 相关链接

[New-BTVisual](https://github.com/Windos/BurntToast/blob/main/Help/New-BTVisual.md)
