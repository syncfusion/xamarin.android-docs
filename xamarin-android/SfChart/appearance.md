---
layout: post
title: Customizing the appearance of Essential Xamarin.Android Chart
description: Learn how to customize the appearance of Chart using palettes.
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Color Palette

## Apply palette for Series

[`ColorModel`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html#Com_Syncfusion_Charts_ChartBase_ColorModel) property of [`SfChart`](http://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html) is used to define the colors for each series. [`ColorModel`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html#Com_Syncfusion_Charts_ChartBase_ColorModel) contains the following color palettes.

**Predefined Palettes**

Currently, Chart supports three types of palette and [`Metro`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartColorPalette.html) palette is the default palette for [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html).

These predefined palettes are

* Metro
* Pineapple
* TomatoSpectrum

 The following screenshot shows the default appearance of multiple series.

![Predefined palettes support in Xamarin.Android Chart](appearance_images/appearance_img1.png)

**Custom Palette**

You can apply the custom colors by setting the palette as [`Custom`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartColorPalette.html) using [`ColorPalette`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartColorModel.html#Com_Syncfusion_Charts_ChartColorModel_ColorPalette) and provide the custom colors using [`CustomColors`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartColorModel.html#Com_Syncfusion_Charts_ChartColorModel_CustomColors) property.

Following code illustrates how to set the custom colors.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart(this);
...

var colors = new List<Color>();
colors.Add(Color.ParseColor("#FFEAE018"));
colors.Add(Color.ParseColor("#FFB3B1AD"));
colors.Add(Color.ParseColor("#FF8C0707"));

chart.ColorModel.ColorPalette = ChartColorPalette.Custom;
chart.ColorModel.CustomColors = colors;

{% endhighlight %}

![Custom palette support in Xamarin.Android Chart](appearance_images/appearance_img2.png)

**None Palette**

None palette will not apply any color to the series. So in order to define the color for any series, you can use the [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) property or the [`ColorModel`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_ColorModel) property of [`ChartSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html) (The ColorModel of Series will be explained later in this document).

## Apply palette for data points

[`ColorModel`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_ColorModel) property of ChartSeries is used to define the colors for each data point. Following palettes are used to define the colors.

**Predefined Palettes**

Currently, Chart supports three types of palette. These predefined palettes are

* Metro
* Pineapple
* TomatoSpectrum

{% highlight c# %} 
[C#]

ColumnSeries columnSeries = new ColumnSeries();
columnSeries.ColorModel.ColorPalette = ChartColorPalette.Metro;

{% endhighlight %}

![Predefined palettes support in Xamarin.Android Chart](appearance_images/appearance_img3.png)

**Custom Palette**

You can apply the custom colors by setting the palette as `Custom` using [`ColorPalette`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartColorModel.html#Com_Syncfusion_Charts_ChartColorModel_ColorPalette) and provide the custom colors using [`CustomColors`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartColorModel.html#Com_Syncfusion_Charts_ChartColorModel_CustomColors) property.

Following code illustrates how to set the custom colors.

{% highlight c# %} 
[C#]

var colors = new List<Color>();
colors.Add(Color.Red);
colors.Add(Color.Gray);
colors.Add(Color.Blue);
colors.Add(Color.Maroon);
colors.Add(Color.Pink);

ColumnSeries columnSeries = new ColumnSeries();
columnSeries.ColorModel.ColorPalette = ChartColorPalette.Custom;
columnSeries.ColorModel.CustomColors = colors;

{% endhighlight %}

![Custom palette support in Xamarin.Android Chart](appearance_images/appearance_img4.png)

**None Palette**

None palette will not apply any color to the data points. So in order to define the color for the data points, you can use the [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) property of [`ChartSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html).

## Gradient Colors

The [`CustomGradientColors`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartColorModel.html#Com_Syncfusion_Charts_ChartColorModel_CustomGradientColors) property of [`ChartColorModel`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartColorModel.html) is used to define the gradient colors, the colors from this property is used for series or chart if the [`Palette`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartColorModel.html#Com_Syncfusion_Charts_ChartColorModel_ColorPalette) property of ChartColorModel is [`Custom`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartColorPalette.html) and the [`CustomColors`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartColorModel.html#Com_Syncfusion_Charts_ChartColorModel_CustomColors) property is null. The following properties are used to define the gradient color for the chart.

The [`StartPoint`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartGradientColor.html#Com_Syncfusion_Charts_ChartGradientColor_StartPoint) and [`EndPoint`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartGradientColor.html#Com_Syncfusion_Charts_ChartGradientColor_EndPoint)  properties of [`ChartGradientColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartGradientColor.html) is used to configure the direction of gradient color, [`GradientStops`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartGradientColor.html#Com_Syncfusion_Charts_ChartGradientColor_GradientStops)  property is used to set the color based on the offset.

The [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartGradientStop.html#Com_Syncfusion_Charts_ChartGradientStop_Color) and [`Offset`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartGradientStop.html#Com_Syncfusion_Charts_ChartGradientStop_Offset) properties of [`ChartGradientStop`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartGradientStop.html) is used to configure the color and offset position of each color. 

Following code snippets and screenshot illustrates how to apply the gradient color to the chart series.

{% highlight c# %} 
[C#]

            series.ColorModel.ColorPalette = ChartColorPalette.Custom;

            ChartGradientColor gradientColor1 = new ChartGradientColor() { StartPoint = new PointF(0.5f, 1), EndPoint = new PointF(0.5f, 0) };
            ChartGradientStop stop11 = new ChartGradientStop() { Color = Color.ParseColor("#FFE7C7"), Offset = 0 };
            ChartGradientStop stop12 = new ChartGradientStop() { Color = Color.ParseColor("#FCB69F"), Offset = 1 };
            gradientColor1.GradientStops.Add(stop11);
            gradientColor1.GradientStops.Add(stop12);

            ChartGradientColor gradientColor2 = new ChartGradientColor() { StartPoint = new PointF(0.5f, 1), EndPoint = new PointF(0.5f, 0) };
            ChartGradientStop stop21 = new ChartGradientStop() { Color = Color.ParseColor("#DCFA97"), Offset = 0 };
            ChartGradientStop stop22 = new ChartGradientStop() { Color = Color.ParseColor("#96E6A1"), Offset = 1 };
            gradientColor2.GradientStops.Add(stop21);
            gradientColor2.GradientStops.Add(stop22);

            ChartGradientColor gradientColor3 = new ChartGradientColor() { StartPoint = new PointF(0.5f, 1), EndPoint = new PointF(0.5f, 0) };
            ChartGradientStop stop31 = new ChartGradientStop() { Color = Color.ParseColor("#DDD6F3"), Offset = 0 };
            ChartGradientStop stop32 = new ChartGradientStop() { Color = Color.ParseColor("#FAACA8"), Offset = 1 };
            gradientColor3.GradientStops.Add(stop31);
            gradientColor3.GradientStops.Add(stop32);

            ChartGradientColor gradientColor4 = new ChartGradientColor() { StartPoint = new PointF(0.5f, 1), EndPoint = new PointF(0.5f, 0) };
            ChartGradientStop stop41 = new ChartGradientStop() { Color = Color.ParseColor("#A8EAEE"), Offset = 0 };
            ChartGradientStop stop42 = new ChartGradientStop() { Color = Color.ParseColor("#7BB0F9"), Offset = 1 };
            gradientColor4.GradientStops.Add(stop41);
            gradientColor4.GradientStops.Add(stop42);

            ChartGradientColorCollection gradientColors = new ChartGradientColorCollection()
            {
                gradientColor1,
                gradientColor2,
                gradientColor3,
                gradientColor4
            };

        series.ColorModel.CustomGradientColors = gradientColors;

{% endhighlight %}

![Gradient support in Xamarin.Android Chart](appearance_images/gradient_series.png)

Following code snippet and screenshot illustrates how to apply the gradient color to the chart area.

{% highlight c# %} 
[C#]

           chart.ColorModel.ColorPalette = ChartColorPalette.Custom;

            ChartGradientColor gradientColor = new ChartGradientColor() { StartPoint = new PointF(0.5f, 1), EndPoint = new PointF(0.5f, 0) };
            ChartGradientStop stop1 = new ChartGradientStop() { Color = Color.ParseColor("#FFE7C7"), Offset = 0 };
            ChartGradientStop stop2 = new ChartGradientStop() { Color = Color.ParseColor("#FCB69F"), Offset = 1 };
            gradientColor.GradientStops.Add(stop1);
            gradientColor.GradientStops.Add(stop2);

             ChartGradientColorCollection gradientColors = new ChartGradientColorCollection()
            {
                gradientColor
            };

            chart.ColorModel.CustomGradientColors = gradientColors;

{% endhighlight %}

![Gradient support in Xamarin.Android Chart](appearance_images/gradient_chart.png)

## Plotting Area Customization

[`SfChart`](http://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html) provides the [`AreaBorderColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html#Com_Syncfusion_Charts_ChartBase_AreaBorderColor), [`AreaBorderWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html#Com_Syncfusion_Charts_ChartBase_AreaBorderWidth), and [`AreaBackgroundColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html#Com_Syncfusion_Charts_ChartBase_AreaBackgroundColor) properties to customize the plot area.

The following code samples demonstrate the usage of these properties:

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
chart.AreaBackgroundColor = Color.Cyan;
chart.AreaBorderColor = Color.Gray;
chart.AreaBorderWidth = 3;

{% endhighlight %}

## Methods

The following methods are available in chart to get the brushes

* [`GetColor(int colorIndex)`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartColorModel.html#Com_Syncfusion_Charts_ChartColorModel_GetColor_System_Int32_) - Returns the brush at the specified index for current palette.
* [`GetColors(ChartColorPalette palette)`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartColorModel.html#Com_Syncfusion_Charts_ChartColorModel_GetColors_Com_Syncfusion_Charts_ChartColorPalette_) - Returns a collection of brushes for specified palette.
