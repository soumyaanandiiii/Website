# Custom Themes

Files has a selection of built-in themes but you can also create your own theme by adding a resource file to the themes directory in the `LocalState` folder.

## How to create a custom theme

1. Navigate to the themes directory, you can open find this folder by clicking the information icon in the appearance page. Create a new file with the `xaml` extension, this file will contain the resources for your custom theme.
2. Open the file in the text editor of your choice.
3. Copy and paste the template below

Default template
```xml
<ResourceDictionary
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:BelowWindows10version1809="http://schemas.microsoft.com/winfx/2006/xaml/presentation?IsApiContractNotPresent(Windows.Foundation.UniversalApiContract, 7)"
    xmlns:Windows10version1809="http://schemas.microsoft.com/winfx/2006/xaml/presentation?IsApiContractPresent(Windows.Foundation.UniversalApiContract, 7)">
    <ResourceDictionary.ThemeDictionaries>
        <ResourceDictionary x:Key="Default">
        </ResourceDictionary>
        <ResourceDictionary x:Key="Light">
        </ResourceDictionary>
    </ResourceDictionary.ThemeDictionaries>
</ResourceDictionary>
```

## Available resources

The themeing system in Files allows y=![Hazy-Night 1](https://user-images.githubusercontent.com/106103136/169866677-48e1e2c9-5bca-4ffc-b5b5-5c5390708805.png)
![screen-1](https://user-images.githubusercontent.com/106103136/169867075-5a507a59-a6f0-47c2-a3b6-6b3bb6e88737.jpg)
u to override any resource that's included in the WinUI library but most themes including the built-in themes only override a couple of brushes.

| Key | Example | Default value |
| --------- | ----------- | ---------- |
| `ContentControlThemeFontFamily` | `<FontFamily x:Key="ContentControlThemeFontFamily">Comic Sans</FontFamily>` | `Segoe UI Variable` |
| `RootBackgroundBrush` | `<SolidColorBrush x:Key="RootBackgroundBrush" Color="#AA845a2b" />` | `Transparent` | 
| `SolidBackgroundFillColorBase` | `<Color x:Key="SolidBackgroundFillColorBase">#A26829</Color>` |  |
| `SolidBackgroundFillColorSecondary` | `<Color x:Key="SolidBackgroundFillColorSecondary">#845a2b</Color>` |  |
| `SolidBackgroundFillColorTertiary` | `<Color x:Key="SolidBackgroundFillColorTertiary">#A26829</Color>` |  |
| `SolidBackgroundFillColorQuarternary` | `<Color x:Key="SolidBackgroundFillColorQuarternary">#A26829</Color>` |  |
| `SolidBackgroundAcrylic` | `<Color x:Key="SolidBackgroundAcrylic">#A26829</Color>` | Light theme: `#FFFFFF` Dark theme: `#2C2C2C` |
| `NavigationToolbarBackgroundBrush` | `<SolidColorBrush x:Key="NavigationToolbarBackgroundBrush" Color="#A26829" />` | `#00000000` |
| `TitlebarContentBackgroundBrush` | `<SolidColorBrush x:Key="TitlebarContentBackgroundBrush" Color="#A26829" />` | `Transparent` |
