---
-api-id: T:Windows.UI.Color
-api-type: winrt struct
---

<!-- Structure syntax.
public struct Color 
-->

# Color

## -description
Describes a color in terms of alpha, red, green, and blue channels.
## -xaml-syntax
```xaml
<Color ...>predefinedColor</Color>
- or -
<Color ...>#rgb</Color>
- or -
<Color ...>#argb</Color>
- or -
<Color ...>#rrggbb</Color>
- or -
<Color ...>#aarrggbb</Color>
- or -
<Color ...>sc#scR,scG,scB</Color>
- or -
<Color ...>sc#scA,scR,scG,scB</Color>
```

```xaml
<object property="predefinedColor"/>
- or -
<object property="#rgb"/>
- or -
<object property="#argb"/>
- or -
<object property="#rrggbb"/>
- or -
<object property="#aarrggbb"/>
- or -
<object property="sc#scR,scG,scB"/>
- or -
<object property="sc#scA,scR,scG,scB"/>
```


## -xaml-values
<dl><dt>predefinedColor</dt><dd>predefinedColorOne of the colors predefined by the Colors class. See members of Colors for a list. These are static properties. Specify just the color name, for example Transparent. Do not include the static class qualifier in the string: for example Colors.Transparent does not parse in XAML.</dd>
<dt>rgb</dt><dd>rgbA three-character hexadecimal value. The first character specifies the color's R value, the second character specifies the G value, and the third character specifies the B value. For example, 00F.</dd>
<dt>argb</dt><dd>argbA four-character hexadecimal value. The first character specifies the color's A value, the second character specifies its R value, the third character specifies the G value, and the fourth character specifies its B value. For example, F00F.</dd>
<dt>rrggbb</dt><dd>rrggbbA six-character hexadecimal value. The first two characters specify the color's R value, the next two specify its G value, and the final two specify its B value. For example, 0000FF.</dd>
<dt>aarrggbb</dt><dd>aarrggbbAn eight-character hexadecimal value. The first two characters specify the color's A value, the next two specify its R value, the next two specify its G value, and the final two specify its B value. For example, FF0000FF.</dd>
<dt>scA</dt><dd>scAThe color's ScA value as a value between 0 and 1.</dd>
<dt>scR</dt><dd>scRThe color's ScR value as a value between 0 and 1.</dd>
<dt>scG</dt><dd>scGThe color's ScG value as a value between 0 and 1.</dd>
<dt>scB</dt><dd>scBThe color's ScB value as a value between 0 and 1.</dd>
</dl>

## -struct-fields

### -field A
Gets or sets the **sRGB** alpha channel value of the color.
    

### -field R
Gets or sets the **sRGB** red channel value of the color.
    

### -field G
Gets or sets the **sRGB** green channel value of the color.
    

### -field B
Gets or sets the **sRGB** blue channel value of the color.
    

## -remarks
[Color](color.md) is a Windows Runtime structure that represents a color that has four channels: **A** (alpha), **R** (red), **G** (green), **B** (blue). Each of the values is stored as a **Byte** type with value 0-255.

[Color](color.md) values are used in these features and scenarios:
+ Colors for start screens and general UI (for example [SecondaryTile.BackgroundColor](../windows.ui.startscreen/secondarytile_backgroundcolor.md) and [UISettings.UIElementColor](../windows.ui.viewmanagement/uisettings_uielementcolor.md)). These can be used in JavaScript.
+ Color values for the Windows 8 ink system. Specifically, [InkDrawingAttributes.Color](../windows.ui.input.inking/inkdrawingattributes_color.md). This can be used in JavaScript.
+ Color values for XAML UI and Windows Store app using C++, C#, or Visual Basic, particularly for brushes. These API can't be used in JavaScript.
+ Defining color values that are used for interfaces representing text, in the [Windows.UI.Text](../windows.ui.text/windows_ui_text.md) namespace. These API can't be used in JavaScript.


### Color values and XAML definitions

The most frequent application of [Color](color.md) is to define color-related properties in a UI element as part of a Windows Store app using C++, C#, or Visual Basic and its XAML UI definition.

Various predefined [Color](color.md) values are available as static properties on the [Colors](colors.md) class. These properties are useful for setting [Color](color.md) values in code that match the attribute string form used in XAML to set a named [Color](color.md). For example, the [Colors.AliceBlue](colors_aliceblue.md) property returns a [Color](color.md) that is equal to [Color](color.md) from the XAML usage `<SolidColorBrush Color="AliceBlue" />`. You can also use the [Colors](colors.md) values for equality comparisons against a Color.

In most XAML UI scenarios, a [Color](color.md) isn't used directly as a property value of a [UIElement](../windows.ui.xaml/uielement.md). Instead, a [Color](color.md) is used as a component value of a [Brush](../windows.ui.xaml.media/brush.md) (either [SolidColorBrush](../windows.ui.xaml.media/solidcolorbrush.md) or [LinearGradientBrush](../windows.ui.xaml.media/lineargradientbrush.md)). However, the [Brush](../windows.ui.xaml.media/brush.md) type enables a XAML shorthand that lets you set an attribute value of type [Brush](../windows.ui.xaml.media/brush.md) using a named color string, or a format string that can be parsed into an **ARGB** form. For example, you can set the [Brush](../windows.ui.xaml.media/brush.md)-type value [TextBlock.Foreground](../windows.ui.xaml.controls/textblock_foreground.md) using a syntax such as `<TextBlock Foreground="Cyan" />`. This syntax implicitly creates a new [SolidColorBrush](../windows.ui.xaml.media/solidcolorbrush.md) with a [Color](color.md) value equal to [Cyan](colors_cyan.md) that fills the [Brush](../windows.ui.xaml.media/brush.md)-type value of [TextBlock.Foreground](../windows.ui.xaml.controls/textblock_foreground.md) for that element. For more info on using brushes and colors in XAML, see [Use brushes](http://msdn.microsoft.com/library/02141f86-355e-4046-86ea-2a89d615b7db).

If you use the same color brush often in your XAML, you should define a [SolidColorBrush](../windows.ui.xaml.media/solidcolorbrush.md) as a resource rather than using the inline implicit creation of new values, because that's more efficient. For more info, see [Optimize your XAML markup](http://msdn.microsoft.com/library/569e8c27-fa01-41d8-80b9-1e3e637d5b99) or [ResourceDictionary and XAML resource references](http://msdn.microsoft.com/library/e3cbfa3d-6af5-44e1-b9f9-c3d3ea8a25ce). You might also want to use system colors, which can be accessed as merged-in resources for themes that the system defines. See [XAML theme resources](http://msdn.microsoft.com/library/41b87dbf-e7a2-44e9-beba-af6eebabb81b).

There are also some XAML properties that take a direct [Color](color.md) value. These mostly support animating a [Color](color.md) value that exists on a [Brush](../windows.ui.xaml.media/brush.md). The Windows Runtime supports an interpolation logic so that you can animate from one [Color](color.md) to another in a **From**/**To** animation and the animation will use interpolated [Color](color.md) values as the animation runs. For more info, see [Storyboarded animations](http://msdn.microsoft.com/library/0cbceea0-2b0e-44a1-a09a-f7a939632f3a).

### Notes on XAML syntax

If you use the "#" token to specify color values in hex form, the hex values are stored in the structure as values between 0 and 255, not as the original hex strings. If you use the "sc#" token, the values are also stored as values between 0 and 255, not the original value of 0 to 1.

Strings for named colors are interpreted based on the associated [Colors](colors.md) constants, and the values for **A**, **R**, **G** and **B** are set in the structure as values between 0 and 255 that are representative of that color.

The XAML object element usage (with initialization text) is useful for declaring a [Color](color.md) as a resource in a XAML [ResourceDictionary](../windows.ui.xaml/resourcedictionary.md). For more info, see [ResourceDictionary and XAML resource references](http://msdn.microsoft.com/library/e3cbfa3d-6af5-44e1-b9f9-c3d3ea8a25ce).

### Projection and members of Color

If you are using a Microsoft .NET language (C# or Microsoft Visual Basic) then [Color](color.md) has a static method [FromArgb](color_fromargb.md) that acts as a [Color](color.md) value generator. Also, the data members of [Color](color.md) are exposed as read-write properties.

If you are programming with C++, either Visual C++ component extensions (C++/CX) or WRL, then only the data member fields exist as members of [Color](color.md), and you cannot use the utility methods or properties listed in the members table. C++ code can use an equivalent [FromArgb](colorhelper_fromargb.md) method on the [ColorHelper](colorhelper.md) class, and the [Platform::Object](XREF:TODO:709e84a8-0bff-471b-bc14-63e424080b5a) methods.

### ToString behavior for Color

For C# and Microsoft Visual Basic, the language support for the [Color](color.md) structure provides a behavior for `ToString` that serializes the values of the **ARGB** data properties into a single string. The string representations of [Color](color.md) values are similar to XAML attribute string syntax for specifying [Color](color.md) values in markup. It is the syntax that is most commonly used by designer tools to specify a (non-named) [Color](color.md). The string is in the form <cmd_line>#AARRGGBB</cmd_line>, where each letter pair represents one of the color channels as a value between <cmd_line>00</cmd_line> and <cmd_line>FF</cmd_line>. Each letter pair is interpreted as if it were a hex value and thus represents a value between 0 and 255. The string always starts with a hash (**#**). For example, the string form of the color where `A=255, R=0, G=128, B=255` is "#FF0080FF". For named colors you get the serialized string and not the constant name; for example calling `ToString` on [Colors.Blue](colors_blue.md) gives "#FF0000FF".

> [!NOTE]
> Visual C++ component extensions (C++/CX) doesn't use nondata members of [Color](color.md), and doesn't enable this form of string returned from `ToString()`. The `ToString()` value returned from Visual C++ component extensions (C++/CX) for a [Color](color.md) is the unmodified [Platform::Object::ToString](XREF:TODO:229dbf1c-cb43-4ed2-a1c5-a1f36b22a7ea) behavior, which gives a representation of the type (boxed by [IReference](../windows.foundation/ireference_1.md)) and does not indicate the value.

## -examples
Here's the syntax for defining a [Color](color.md) value as a resource in a XAML [ResourceDictionary](../windows.ui.xaml/resourcedictionary.md). You'd typically only need this if you are defining a color that is not already one of the 250+ colors provided as the values in the [Colors](colors.md) class, and you want to use the XAML resource system as enforcement that you're using the same color in multiple areas of your app UI. Note the [x:Key attribute](http://msdn.microsoft.com/library/141fc5af-80ee-4401-8a1b-17cb22c2277a), required when you define a XAML resource.

```xaml
  <Application.Resources>
    ...
    <Color x:Key="SlightlyOffBlue">#FF0000E8</Color>
  </Application.Resources>
```

```xaml
<!-- example reference to the resource, make sure is a property that is really Color not Brush-->
      <ColorAnimation Storyboard.TargetName="mySolidColorBrush"
        Storyboard.TargetProperty="Color" To="{StaticResource SlightlyOffBlue}" Duration="0:0:4"/>

```

This code shows a two-way converter for [SolidColorBrush](../windows.ui.xaml.media/solidcolorbrush.md) and [Color](color.md) values. This can be useful for databinding scenarios, because it implements the [IValueConverter](../windows.ui.xaml.data/ivalueconverter.md) pattern that the [Converter](../windows.ui.xaml.data/binding_converter.md) property of a data binding can use, and you can then bind a [SolidColorBrush](../windows.ui.xaml.media/solidcolorbrush.md) source to a [Color](color.md) target and vice versa. To see this code in context, see the source for the [SwapChainPanel sample](http://go.microsoft.com/fwlink/p/?LinkID=309155).

```csharp
    class BrushConverter : IValueConverter
    {
        public object Convert(object value, Type targetType, object parameter, string language)
        {
            return new SolidColorBrush((value is Color) ? (Color)value : Colors.Black);
        }

        public object ConvertBack(object value, Type targetType, object parameter, string language)
        {
            return (value is SolidColorBrush) ? (value as SolidColorBrush).Color : Colors.Black;
        }
    }
```



## -see-also
[Use brushes](http://msdn.microsoft.com/library/02141f86-355e-4046-86ea-2a89d615b7db), [Colors](colors.md), [ColorHelper](colorhelper.md), [SolidColorBrush](../windows.ui.xaml.media/solidcolorbrush.md), [LinearGradientBrush](../windows.ui.xaml.media/lineargradientbrush.md), [ResourceDictionary and XAML resource references](http://msdn.microsoft.com/library/e3cbfa3d-6af5-44e1-b9f9-c3d3ea8a25ce)