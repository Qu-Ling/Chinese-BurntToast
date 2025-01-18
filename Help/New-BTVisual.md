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

此命令将创建一个新的 Visual 元素，将以前配置的绑定元素作为输入。

## 参数

### -AddImageQuery

Specify this switch to allow Windows to append a query string to the image URI supplied in the Toast notification. Use this attribute if your server hosts images and can handle query strings, either by retrieving an image variant based on the query strings or by ignoring the query string and returning the image as specified without the query string. This query string specifies scale, contrast setting, and language.

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

### -BaseUri

A default base URI that is combined with relative URIs in image source attributes.

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

### -BindingGeneric

The generic Toast binding, which can be rendered on all devices. This binding is created using the New-BTBinding function.

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

### -Language

The target locale of the XML payload, specified as BCP-47 language tags such as "en-US" or "fr-FR". This locale is overridden by any locale specified in binding or text. If this value is a literal string, this attribute defaults to the user's UI language. If this value is a string reference, this attribute defaults to the locale chosen by Windows Runtime in resolving the string.

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

None

## OUTPUTS

ToastVisual

## NOTES

Credit for most of the help text for this function go to the authors of the UWPCommunityToolkit library that this module relies upon.

Please see the [originating repo](https://github.com/Microsoft/UWPCommunityToolkit).

## RELATED LINKS

[New-BTVisual](https://github.com/Windos/BurntToast/blob/main/Help/New-BTVisual.md)
