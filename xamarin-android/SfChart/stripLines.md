---
layout: post
title: Chart StripLines
description: Learn how to add horizontal or vertical lines in Chart.
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Strip Lines

## What is strip line?

Strip lines are used to shade the different ranges in plot area in different colors to improve the readability of the chart. You can annotate it with text to indicate what that particular region indicates. You can also enable the strip lines to be drawn repeatedly at regular intervals – this will be useful when you want to mark an event that occurs recursively along the timeline of the chart.

## How to add strip lines?

Strip line is classified into **NumericalStripLine** and **DateTimeStripLine** based on the type of input you provide to draw the strip line. Since [`StripLines`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.LogarithmicAxis.html#Com_Syncfusion_Charts_LogarithmicAxis_StripLines) are drawn based on the axis, you have to add strip line instance using [`StripLines`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CategoryAxis.html#Com_Syncfusion_Charts_CategoryAxis_StripLines) property of the respective axis. You can also add multiple [`StripLines`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DateTimeCategoryAxis.html#Com_Syncfusion_Charts_DateTimeCategoryAxis_StripLines) to an axis.

Following properties are used to configure the strip line.

* [`Start`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.NumericalStripLine.html#Com_Syncfusion_Charts_NumericalStripLine_Start) – used to change the start position of the strip line.
* [`Width`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLine.html#Com_Syncfusion_Charts_ChartStripLine_Width) – used to change how long strip line should expand.
* [`WidthType`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DateTimeStripLine.html#Com_Syncfusion_Charts_DateTimeStripLine_WidthType) - used to change the date time unit of the value specified in the width property.
* [`PixelWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLine.html#Com_Syncfusion_Charts_ChartStripLine_PixelWidth) - used to specify the unit type for Width property, whether it is screen point or chart value.
* [`Text`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLine.html#Com_Syncfusion_Charts_ChartStripLine_Text) – used to change the text of the strip line.
* [`FillColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLine.html#Com_Syncfusion_Charts_ChartStripLine_FillColor) – used to change the fill color of the strip line.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLine.html#Com_Syncfusion_Charts_ChartStripLine_StrokeWidth) – used to change the stroke width of the strip line.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLine.html#Com_Syncfusion_Charts_ChartStripLine_StrokeColor) – used to change the stroke color of the strip line.
* [`StrokePathEffect`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLine.html#Com_Syncfusion_Charts_ChartStripLine_StrokePathEffect) - used to render the strip line with dashes.
* [`CornerRadius`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLine.html#Com_Syncfusion_Charts_ChartStripLine_CornerRadius) - used to add the rounded corners to the rectangle. The [`TopLeft`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_TopLeft), [`TopRight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_TopRight), [`BottomLeft`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_BottomLeft) and [`BottomRight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_BottomRight) of [`ChartCornerRadius`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html) properties are used to set the radius value for each corner.
* [`Visibility`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLine.html#Com_Syncfusion_Charts_ChartStripLine_Visibility) - used to change the visibility of the strip line.

**NumericalStripLine**

[`NumericalStripLine`](http://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.NumericalStripLine.html) are used to draw strip lines for [`NumericalAxis`](http://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.NumericalAxis.html) and [`CategoryAxis`](http://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CategoryAxis.html). To add a strip line, create an instance of [`NumericalStripLine`](http://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.NumericalStripLine.html) and add to the axis using [`StripLines`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.NumericalAxis.html#Com_Syncfusion_Charts_NumericalAxis_StripLines) property of the respective axis.

{% highlight c# %}
[C#]
 
SfChart chart = new SfChart();
...

NumericalAxis numericalAxis = new NumericalAxis();

numericalAxis.Minimum = 28;

numericalAxis.Maximum = 52;

NumericalStripLine numericalStripLines = new NumericalStripLine();

numericalStripLines.Start = 36;

numericalStripLines.Width = 8;

numericalStripLines.Text = "Average Temperature";

numericalStripLines.FillColor = Color.ParseColor("#F4C762");

numericalAxis.StripLines.Add(numericalStripLines);

chart.SecondaryAxis = numericalAxis;

{% endhighlight %}

![Numerical strip lines support in Xamarin.Android Chart](striplines_images/stripline_img1.png)

**DateTimeStripLine**

As the name indicates, [`DateTimeStripLine`](http://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DateTimeStripLine.html) are used to draw strip lines for [`DateTimeAxis`](http://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DateTimeAxis.html). To add a strip line for [`DateTimeAxis`](http://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DateTimeAxis.html), create an instance of [`DateTimeStripLine`](http://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DateTimeStripLine.html) and add to the axis using [`StripLines`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DateTimeAxis.html#Com_Syncfusion_Charts_DateTimeAxis_StripLines) property of [`DateTimeAxis`](http://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DateTimeAxis.html).

{% highlight c# %}
[C#]

SfChart chart = new SfChart();
...

DateTimeAxis dateTimeAxis = new DateTimeAxis()
{
    EdgeLabelsDrawingMode = EdgeLabelsDrawingMode.Shift,
    Interval = 3,
    IntervalType = DateTimeIntervalType.Months
};

Calendar calendar = new GregorianCalendar(2000, 0, 1);
dateTimeAxis.Minimum = calendar.Time;
calendar.Set(2000, 11, 30);
dateTimeAxis.Maximum = calendar.Time;

DateTimeStripLine dateTimeStripLine = new DateTimeStripLine()
{
    WidthType = DateTimeIntervalType.Months,              
    Width = 3,
    Text = "Quarter-2",
    FillColor = Color.ParseColor("#3FAA38")
};


calendar.Set(2000, 4, 1);
dateTimeStripLine.Start = calendar.Time;
dateTimeAxis.StripLines.Add(dateTimeStripLine);

chart.PrimaryAxis = dateTimeAxis;

{% endhighlight %}

![DateTime strip lines support in Xamarin.Android Chart](striplines_images/stripline_img2.png)

## Strip Line Recurrence

This feature is used to enable the strip lines to be drawn repeatedly at the regular intervals – this will be useful when you want to mark an event that occurs recursively along the timeline of the chart. Following properties are used to configure this feature.

* [`RepeatEvery`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLine.html#Com_Syncfusion_Charts_ChartStripLine_RepeatEvery) – used to change the frequency of the strip line being repeated.
* [`RepeatUntil`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.NumericalStripLine.html#Com_Syncfusion_Charts_NumericalStripLine_RepeatUntil) – specifies the end value at which point strip line has to stop repeating.
* [`RepeatEveryType`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DateTimeStripLine.html#Com_Syncfusion_Charts_DateTimeStripLine_RepeatEveryType) - used to represents the date time unit of value specified in the [`RepeatEvery`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLine.html#Com_Syncfusion_Charts_ChartStripLine_RepeatEvery) property and [`RepeatUntil`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DateTimeStripLine.html#Com_Syncfusion_Charts_DateTimeStripLine_RepeatUntil) property.
  
Following code snippet and screenshot demonstrates this feature by highlighting weekends. 

{% highlight c# %} 
[C#]

NumericalStripLine numericalStripLines = new NumericalStripLine();

numericalStripLines.Start = 6;

numericalStripLines.Width = 1;

numericalStripLines.Text = "Weekend";

numericalStripLines.FillColor = Color.ParseColor("#ECE6F1");

numericalStripLines.RepeatEvery = 7;

numericalStripLines.LabelStyle.Angle = 270;

numericalStripLines.LabelStyle.TextColor = Color.Red;

{% endhighlight %}

![Strip lines recurrence support in Xamarin.Android Chart](striplines_images/stripline_img3.png)

## Customize Text

The [`LabelStyle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLine.html#Com_Syncfusion_Charts_ChartStripLine_LabelStyle) property provide options to customize the font-family, color, size and font-weight of strip line text. Following are the options available,

* [`TextColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLabelStyle.html#Com_Syncfusion_Charts_ChartLabelStyle_TextColor) – used to change the color of the text.
* [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLabelStyle.html#Com_Syncfusion_Charts_ChartLabelStyle_BackgroundColor) – used to change the label background color.
* [`BorderColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLabelStyle.html#Com_Syncfusion_Charts_ChartLabelStyle_StrokeColor) – used to change the border color.
* [`BorderThickness`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLabelStyle.html#Com_Syncfusion_Charts_ChartLabelStyle_StrokeWidth) – used to change the thickness of the border.
* [`Font`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLabelStyle.html#Com_Syncfusion_Charts_ChartLabelStyle_Typeface) – used to change the text size, font family and font weight.
* [`Margin`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLabelStyle.html#Com_Syncfusion_Charts_ChartLabelStyle_MarginBottom) - used to change the margin size for text.
* [`Angle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLineLabelStyle.html#Com_Syncfusion_Charts_ChartStripLineLabelStyle_Angle) – used to rotate the text.
* [`HorizontalAlignment`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLineLabelStyle.html#Com_Syncfusion_Charts_ChartStripLineLabelStyle_HorizontalLabelAlignment) – used to change the horizontal alignment of text.
* [`VerticalAlignment`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLineLabelStyle.html#Com_Syncfusion_Charts_ChartStripLineLabelStyle_VerticalLabelAlignment)  - used to change the vertical alignment of text.

{% highlight c# %} 
[C#]

NumericalAxis numericalAxis = new NumericalAxis()
{
    Minimum = 30,
    Maximum = 48
};

NumericalStripLine numericalStripLines = new NumericalStripLine()
{
    Start = 42,
    Width = 6,
    Text = "High Temperature",
    FillColor = Color.ParseColor("#EF7878")                
};

numericalStripLines.LabelStyle.TextSize = 20;
numericalStripLines.LabelStyle.TextColor = Color.Blue;

numericalAxis.StripLines.Add(numericalStripLines);

{% endhighlight %}

![Strip lines text customization support in Xamarin.Android Chart](striplines_images/stripline_img4.png)

## Segmented Strip Line

Typically, if you draw a strip line for a vertical axis, the height of the strip line is determined by the [`Start`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.NumericalStripLine.html#Com_Syncfusion_Charts_NumericalStripLine_Start) and [`Width`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLine.html#Com_Syncfusion_Charts_ChartStripLine_Width) properties and width of the strip line is equivalent to the width of its associated horizontal axis i.e., strip line is drawn horizontally to the entire stretch of its associated horizontal axis. Similarly, for horizontal axis, width is determined by [`Start`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DateTimeStripLine.html#Com_Syncfusion_Charts_DateTimeStripLine_Start) and [`Width`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLine.html#Com_Syncfusion_Charts_ChartStripLine_Width) properties, and vertically, it is drawn to the entire stretch of the associated vertical axis.

Suppose, you want to draw a strip line that should not stretch along its associated axis, you can customize using [`SegmentStart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLine.html#Com_Syncfusion_Charts_ChartStripLine_SegmentStart) and [`SegmentEnd`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLine.html#Com_Syncfusion_Charts_ChartStripLine_SegmentEnd) properties. Values provided in these two properties correspond to its associated axis specified using [`SegmentAxisName`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLine.html#Com_Syncfusion_Charts_ChartStripLine_SegmentAxisName) property. Finally, you need to set [`Segmented`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLine.html#Com_Syncfusion_Charts_ChartStripLine_Segmented) property to true to indicate that strip line should be drawn as a segment.

* [`Segmented`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLine.html#Com_Syncfusion_Charts_ChartStripLine_Segmented) – Used to enable / disable the segmented strip line.
* [`SegmentStart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLine.html#Com_Syncfusion_Charts_ChartStripLine_SegmentStart) – Used to change the segment start value. Value correspond to associated axis.
* [`SegmentEnd`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLine.html#Com_Syncfusion_Charts_ChartStripLine_SegmentEnd) – Used to change the segment end value. Value correspond to associated axis.
* [`SegmentAxisName`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLine.html#Com_Syncfusion_Charts_ChartStripLine_SegmentAxisName) – Specify the name of the associated axis name.

N> You can set the double or DateTime value for [`SegmentStart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLine.html#Com_Syncfusion_Charts_ChartStripLine_SegmentStart) and [`SegmentEnd`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartStripLine.html#Com_Syncfusion_Charts_ChartStripLine_SegmentEnd) properties based on the associated axis type.

Following code snippet shows how to set the segment start and end value if the associated axis type is numerical.

{% highlight c# %}
[C#]
 
SfChart chart = new SfChart();
...

CategoryAxis categoryAxis = new CategoryAxis()
{
    EdgeLabelsDrawingMode = EdgeLabelsDrawingMode.Shift,
    Interval = 3
};

NumericalStripLine numericalStripLines = new NumericalStripLine()
{
    Segmented = true,
    SegmentStart = 40,
    SegmentEnd = 46,
    SegmentAxisName = "Amount",
    Start = 3,
    Width = 3,
    Text = "Quarter-2",
    FillColor = Color.ParseColor("#EF7878")
};

categoryAxis.StripLines.Add(numericalStripLines);
chart.PrimaryAxis = categoryAxis;

chart.SecondaryAxis = new NumericalAxis()
{
    Minimum = 30,
    Maximum = 48,
    Name = "Amount"
};

{% endhighlight %}

![Segmented strip lines support in Xamarin.Android Chart](striplines_images/stripline_img5.png)

Following code snippet shows how to set the segment start and end value if the associated axis type is date time. 

{% highlight c# %}
[C#]

SfChart chart = new SfChart();
...

chart.PrimaryAxis = new DateTimeAxis()
{

    EdgeLabelsDrawingMode = EdgeLabelsDrawingMode.Shift,
    Name = "Period"

};

NumericalStripLine stripLine = new NumericalStripLine()
{

    Start = 42,
    Width = 4,
    Text = "Quarter-2",
    FillColor = Color.ParseColor("#3FAA38"),
    Segmented = true,
    SegmentAxisName = "Period"             
};

Calendar calendar = new GregorianCalendar(2000, 3, 1);
stripLine.SegmentStart = calendar;
calendar.Set(2000, 5, 30);
stripLine.SegmentEnd = calendar;

NumericalAxis numericalAxis = new NumericalAxis()
{

    Minimum = 30,
    Maximum = 48

};

numericalAxis.StripLines.Add(stripLine);

chart.SecondaryAxis = numericalAxis;

{% endhighlight %}

![Segmented support for DateTime strip lines in Xamarin.Android Chart](striplines_images/stripline_img6.png)
