---
layout: post
title: Chart legend | SfChart | Xamarin.Android | Syncfusion
description: How to customize the legend's border, background, labels, icons, title, orientation and position in Xamarin.Android Chart
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Legend

Legend contains list of chart series/data points in the chart. The information provided in each legend item helps in identifying the corresponding data series in chart. The [`Visibility`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_Visibility) property is used to control the visibility of legend.

Following code example shows how to enable legend in a chart,

{% highlight c# %} 
[C#]

chart.Legend.Visibility = Visibility.Visible;

{% endhighlight %}

![Legend support in Xamarin.Android Chart](legend_images/legend_img1.png)

## Customizing background & border

The [`Legend`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html) provides following properties to customize the legend area border and background. 

* [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_BackgroundColor) - used to change legend background color.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_StrokeColor) - used to change legend border color.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_StrokeWidth) - used to change legend border width. 
* [`PathEffect`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_PathEffect) - used to render legend border line with dashes.
* [`MarginTop`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_MarginTop) - used to change the top margin of the legend.
* [`MarginBottom`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_MarginBottom) - used to change the bottom margin of the legend.
* [`MarginLeft`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_MarginLeft) - used to change the left margin of the legend.
* [`MarginRight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_MarginRight) - used to change the right margin of the legend.
* [`CornerRadius`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_CornerRadius) - used to add the rounded corners to the legend border rectangle. The TopLeft, TopRight, BottomLeft and BottomRight of ChartCornerRadius properties are used to set the radius value for each corner.

{% highlight c# %} 
[C#]

chart.Legend.BackgroundColor = Color.Argb(255, 245, 245, 240);
chart.Legend.StrokeColor = Color.Black;
chart.Legend.StrokeWidth = 2;
chart.Legend.MarginTop = 5;
chart.Legend.MarginBottom = 5;
chart.Legend.MarginLeft = 5;
chart.Legend.MarginRight = 5;
chart.Legend.CornerRadius = new ChartCornerRadius(5);
chart.Legend.PathEffect = new DashPathEffect(new float[] { 3, 3 }, 4);          

{% endhighlight %}

![Legend background and border customization support in Xamarin.Android Chart](legend_images/legend_background.jpg)

## Customizing Labels

[`Label`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Label) property of [`ChartSeries`](http://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html) is used to define the label for the corresponding series legend item. The [`LabelStyle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_LabelStyle) property can be used to customize the legend items label appearance.

* [`TextColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendLabelStyle.html#Com_Syncfusion_Charts_ChartLegendLabelStyle_TextColor) – used to change the color of the label.
* [`TextSize`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendLabelStyle.html#Com_Syncfusion_Charts_ChartLegendLabelStyle_TextSize) – used to change the text size.
* [`Typeface`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendLabelStyle.html#Com_Syncfusion_Charts_ChartLegendLabelStyle_Typeface) – used to change the font family and font weight.
* [`MarginTop`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLabelStyle.html#Com_Syncfusion_Charts_ChartLabelStyle_MarginTop) - used to change the top margin of the labels.
* [`MarginBottom`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLabelStyle.html#Com_Syncfusion_Charts_ChartLabelStyle_MarginBottom) - used to change the bottom margin of the labels.
* [`MarginLeft`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLabelStyle.html#Com_Syncfusion_Charts_ChartLabelStyle_MarginLeft) - used to change the left margin of the labels.
* [`MarginRight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLabelStyle.html#Com_Syncfusion_Charts_ChartLabelStyle_MarginRight) - used to change the right margin of the labels.

{% highlight c# %} 
[C#]

chart.Legend.LabelStyle.TextSize = 18;
chart.Legend.LabelStyle.TextColor = Color.Blue;
chart.Legend.LabelStyle.Typeface = Typeface.DefaultBold;
chart.Legend.LabelStyle.MarginBottom = 5;
chart.Legend.LabelStyle.MarginLeft = 5;
chart.Legend.LabelStyle.MarginRight = 5;
chart.Legend.LabelStyle.MarginTop = 5;            

{% endhighlight %}

![Legend labels customization support in Xamarin.Android Chart](legend_images/legend_img2.png)

## Legend Icons

Legend icons are enabled by default, however, you can control its visibility using [`IconVisibility`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_IconVisibility) property. Also you can specify the icon type using [`LegendIcon`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_LegendIcon) property in ChartSeries. Default legend icon is [`Circle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendIcon.html). [`IconWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_IconWidth) and [`IconHeight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_IconHeight) properties are used to adjust the width and height of the legend icons respectively.

{% highlight c# %} 
[C#]

chart.Legend.IconVisibility = Visibility.Visible;
chart.Legend.IconHeight = 20;
chart.Legend.IconWidth = 20;
pieSeries.LegendIcon = ChartLegendIcon.SeriesType;

{% endhighlight %}

![Legend icons in Xamarin.Android Chart](legend_images/legend_img3.png)

## Legend Title

Following properties are used to define and customize the legend [`Title`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_Title).

* [`Text`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendTitleView.html) – used to set the title for legend.
* [`TextColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendTitleView.html) – used to change the color of the title text.
* [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendTitleView.html) – used to change the title background color.
* [`TextSize`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendTitleView.html) – used to change the text size of the title.
* [`Typeface`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendTitleView.html) – used to change the font family and font weight.
* [`MarginTop`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendLabelStyle.html#Com_Syncfusion_Charts_ChartLegendLabelStyle_MarginTop) - used to change the top margin of the title.
* [`MarginBottom`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendLabelStyle.html#Com_Syncfusion_Charts_ChartLegendLabelStyle_MarginBottom) - used to change the bottom margin of the title.
* [`MarginLeft`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendLabelStyle.html#Com_Syncfusion_Charts_ChartLegendLabelStyle_MarginLeft) - used to change the left margin of the title.
* [`MarginRight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendLabelStyle.html#Com_Syncfusion_Charts_ChartLegendLabelStyle_MarginRight) - used to change the right margin of the title.
* [`TextAlignment`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendTitleView.html) – used to change the alignment of the title text, it can be start, end and center.

{% highlight c# %} 
[C#]

chart.Legend.Title.Text = "Year";
chart.Legend.Title.SetTextColor(Color.Red);
chart.Legend.Title.TextSize = 20;
chart.Legend.Title.Typeface = Typeface.DefaultBold;
chart.Legend.Title.SetBackgroundColor(Color.Gray);
chart.Legend.Title.TextAlignment = TextAlignment.Center; 

{% endhighlight %}

![Title for legend in Xamarin.Android Chart](legend_images/legend_img4.png)

## Toggle the series visibility

You can control the visibility of the series by tapping on the legend item. You can enable this feature by enabling [`ToggleSeriesVisibility`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_ToggleSeriesVisibility) property.

{% highlight c# %} 
[C#]

chart.Legend.ToggleSeriesVisibility = true;

{% endhighlight %}

## Legend item visibility

You can control the visibility of particular series legend item by using the [`VisibilityOnLegend`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_VisibilityOnLegend) property of series. Default value of VisibilityOnLegend property is Visible.

{% highlight c# %} 
[C#]

ColumnSeries series = new ColumnSeries();
series.VisibilityOnLegend = Visibility.Gone;

{% endhighlight %}

## Legend Wrap

The legend items can be placed in multiple rows by using [`OverflowMode`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_OverflowMode) property if size of the total legend exceeds the available size. The default value of [`OverflowMode`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_OverflowMode) property is [`Scroll`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendOverflowMode.html).

{% highlight c# %}
[C#]

    chart.Legend.Visibility = Com.Syncfusion.Charts.Visibility.Visible;

    chart.Legend.OverflowMode = ChartLegendOverflowMode.Wrap;

{% endhighlight %}

![Legend wrapping support in Xamarin.Android Chart](legend_images/legendwrap_img1.png)

### Legend Width

The legend width can be specified by using [`MaxWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_MaxWidth) property. This property works only when the [`OverflowMode`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_OverflowMode) is [`Wrap`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendOverflowMode.html). The default value of [`MaxWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_MaxWidth) property is double.NAN.

{% highlight c# %}
[C#]

    chart.Legend.Visibility = Com.Syncfusion.Charts.Visibility.Visible;

    chart.Legend.OverflowMode = ChartLegendOverflowMode.Wrap;

    chart.Legend.MaxWidth = 420;

{% endhighlight %}

![Providing width for legend in Xamarin.Android Chart](legend_images/legendwrap_img2.png)

## Positioning the Legend

You can position the legend anywhere inside the chart. Following properties are used to customize the legend positions.

* [`DockPosition`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_DockPosition)– used to position the legend relatively. Options available are:  [`Left`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDock.html), Right, Top, Bottom and Floating. If the DockPosition is Floating, you can position the legend using x and y coordinates.
* [`OffsetX`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_OffsetX) – used to move the legend on x coordinate by the given offset value, this will work only if the dock position is Floating.
* [`OffsetY`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_OffsetY) - used to move the legend on y coordinate by the given offset value, this will work only if the dock position is Floating.
* [`LegendPosition`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_LegendPosition) - used to position the legend items [`Inside`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.LegendPosition.html) or [`Outside`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.LegendPosition.html) of the chart series. The default position is Outside.
* [`ItemMarginTop`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_ItemMarginTop) - used to change the top margin of the legend item.
* [`ItemMarginBottom`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_ItemMarginBottom) - used to change the bottom margin of the legend item.
* [`ItemMarginLeft`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_ItemMarginLeft) - used to change the left margin of the legend item.
* [`ItemMarginRight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_ItemMarginRight) - used to change the right margin of the legend item.

{% highlight c# %} 
[C#]

chart.Legend.DockPosition = ChartDock.Floating;
chart.Legend.OffsetX = 160;
chart.Legend.OffsetY = 30;

{% endhighlight %}

![Legend positioning support in Xamarin.Android Chart](legend_images/legend_img5.png)

## Legend Orientation

By default, the legend items will be oriented based on the legend dock position for better readability of the legend. However, you can change the [`Horizontal`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartOrientation.html) or [`Vertical`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartOrientation.html) orientation of the legend items using [`Orientation`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegend.html#Com_Syncfusion_Charts_ChartLegend_Orientation) property.

{% highlight c# %} 
[C#]

chart.Legend.Orientation = ChartOrientation.Horizontal;

{% endhighlight %}

## Event

 **LegendItemClicked**

The [`LegendItemClicked`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html) event is triggered when the chart legend item is clicked. This argument contains the following information.

* [`LegendItem`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendItemClickedEventArgs.html#Com_Syncfusion_Charts_ChartLegendItemClickedEventArgs_LegendItem) – Used to customize the label and appearance of individual legend item. 

**LegendItemCreated**

The [`LegendItemCreated`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html) event is triggered when the chart legend item is created. This argument contains the following information.

* [`LegendItem`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendItemCreatedEventArgs.html#Com_Syncfusion_Charts_ChartLegendItemCreatedEventArgs_LegendItem) – Used to customize the label and appearance of individual legend item.

You can customize the legend item by using following properties of [`ChartLegendItem`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendItem.html).

* [`Label`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendItem.html#Com_Syncfusion_Charts_ChartLegendItem_Label) – Used to get or set the legend item label.
* [`LabelStyle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendItem.html#Com_Syncfusion_Charts_ChartLegendItem_LabelStyle) – Used to customize the appearance of legend labels. The properties listed in [`customizing label`](https://help.syncfusion.com/xamarin-android/sfchart/legend#customizing-labels) can be customized using LabelStyle property.
* [`IconColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendItem.html#Com_Syncfusion_Charts_ChartLegendItem_IconColor) – Used to get or set the legend icon color.
* [`Index`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendItem.html#Com_Syncfusion_Charts_ChartLegendItem_Index) – Used to get the legend item index.
* [`IsEnabled`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendItem.html#Com_Syncfusion_Charts_ChartLegendItem_IsEnabled) – Used to get the visibility of the series if the series is the type of [`CartesianSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CartesianSeries.html) and get the visibility of the data point if the series is type of [`AccumulationSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AccumulationSeries.html).
* [`DataPoint`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendItem.html#Com_Syncfusion_Charts_ChartLegendItem_DataPoint) – Used to get the legend item data point for accumulation series only.
* [`Series`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendItem.html#Com_Syncfusion_Charts_ChartLegendItem_Series) – Used to get respective chart series.
* [`View`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLegendItem.html#Com_Syncfusion_Charts_ChartLegendItem_View) – Used to get or set the legend item view.
