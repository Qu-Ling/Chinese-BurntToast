# New-BTContent

## 作用
创建一个新的Toast内容对象。

## 语法

```powershell
New-BTContent [[-Actions] <IToastActions>] [[-ActivationType] <ToastActivationType>] [[-Audio] <ToastAudio>]
 [[-Duration] <ToastDuration>] [[-Launch] <String>] [[-Scenario] <ToastScenario>] [-Visual] <ToastVisual>
```

## 描述

New-BTContent 函数会创建一个新的Toast内容对象，该对象是基本元素，且至少包含一个视觉元素。

## 案例

### -------------------------- 案例 1 --------------------------

```powershell
PS C:\>$binding1 = New-BTBinding -Children $text1, $text2 -AppLogoOverride $image2
PS C:\>$visual1 = New-BTVisual -BindingGeneric $binding1
PS C:\>$content1 = New-BTContent -Visual $visual1
```

此案例将通过 BurntToast 函数创建的大量对象合并到一个绑定中，然后是一个可视元素，最后合并到一个内容对象中。


### -------------------------- 案例 2 --------------------------

```powershell
PS C:\>$content1 = New-BTContent -Visual $visual1 -ActivationType Protocol -Launch 'https://google.com'
```

此命令采用预先存在的视觉对象，并指定在单击 toast 时在 Google 主页上启动浏览器所需的选项。

## 参数

### -Actions 操作

（可选）使用按钮和输入创建自定义操作 （由New-BTAction生成对象.）

```yaml
Type: IToastActions
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ActivationType 激活类型

指定当用户单击此Toast的正文时将使用的激活类型。

```yaml
Type: ToastActivationType
Parameter Sets: (All)
Aliases:
Accepted values: Foreground, Background, Protocol

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Audio 音频

指定自定义音频选项 （New-BTAudio.）

```yaml
Type: ToastAudio
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Duration 显示时长

Toast 应显示的时间。通常应该使用 Scenario 属性，因为该属性会影响 Toast 在屏幕上停留的时间。

```yaml
Type: ToastDuration
Parameter Sets: (All)
Aliases:
Accepted values: Short, Long

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Header 通知头

创意者更新中的新增功能：指定 toast 通知的可选标头 （New-BTHeader.）

```yaml
Type: ToastHeader
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Launch 

当应用程序被 Toast 激活时传递给应用程序的字符串。此字符串的格式和内容由应用程序定义，供其自己使用。当用户点击或单击 Toast 以启动其关联的应用程序时，启动字符串会为应用程序提供上下文，使应用程序能够向用户显示与 Toast 内容相关的视图，而不是以默认方式启动。

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

### -Scenario 方案

指定方案，使 Toast 的行为类似于闹钟、提醒等。

```yaml
Type: ToastScenario
Parameter Sets: (All)
Aliases:
Accepted values: Default, Alarm, Reminder, IncomingCall

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Visual 视觉

指定使用 New-BTVisual 函数创建的可视元素对象。

```yaml
Type: ToastVisual
Parameter Sets: (All)
Aliases:

Required: True
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## 输入

TODO

## 输出

ToastContent

## 其他

此函数的大部分帮助文本都归功于本模块所依赖的 UWPCommunityToolkit 库的作者。

请参阅 [originating repo](https://github.com/windows-toolkit/WindowsCommunityToolkit).

## 其他链接

[New-BTContent](https://github.com/Windos/BurntToast/blob/main/Help/New-BTContent.md)
