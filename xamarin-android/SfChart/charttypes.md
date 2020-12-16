---
layout: post
title: Chart Types | SFChart | Xamarin.Android | Syncfusion
description: This section explains the different types of charts, including Cartesian, Financial, Accumulation, PolarRadar and its properties.
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Types of Syncfusion SfChart

## Line Chart

To render a line chart, create an instance of [`LineSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.LineSeries.html) and add to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). The [`Visibility`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Visibility) property represents the series visibility in SfChart. You can use the following properties to customize the appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the line.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the line.
* [`Alpha`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Alpha) - Controls the transparency of the chart series.

{% highlight c# %}
[C#] 

SfChart chart = new SfChart();
...

LineSeries lineSeries = new LineSeries()
{
	ItemsSource = Data,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(lineSeries);

{% endhighlight %}

![Line chart type in Xamarin.Android](charttypes_images/charttypes_img1.png)

### Dashed Lines

[`PathEffect`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.LineSeries.html#Com_Syncfusion_Charts_LineSeries_PathEffect) property of the [`LineSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.LineSeries.html) is used to render line series with dashes.

{% highlight c# %} 
[C#]

LineSeries lineSeries = new lineSeries()
{
	ItemsSource = Data,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};

lineSeries.PathEffect = new DashPathEffect(new float[] {5, 6}, 2);
chart.Series.Add(lineSeries);

{% endhighlight %}

## Stacked Line Chart

To render a stacked line chart, create an instance of `StackingLineSeries` and add to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). You can use the following properties to customize the stacked line appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the line.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the line.
* [`Alpha`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Alpha) - controls the transparency of the chart series.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

StackingLineSeries stackingLineSeries1 = new StackingLineSeries()
{
	ItemsSource = Data1,
	XBindingPath = "XValue",
	YBindingPath = "YValue"
};
chart.Series.Add(stackingLineSeries1);

StackingLineSeries stackingLineSeries2 = new StackingLineSeries()
{
	ItemsSource = Data2,
	XBindingPath = "XValue",
	YBindingPath = "YValue"
};
chart.Series.Add(stackingLineSeries2);

StackingLineSeries stackingLineSeries3 = new StackingLineSeries()
{
	ItemsSource = Data3,
	XBindingPath = "XValue",
	YBindingPath = "YValue"
};
chart.Series.Add(stackingLineSeries3);

StackingLineSeries stackingLineSeries4 = new StackingLineSeries()
{
	ItemsSource = Data4,
	XBindingPath = "XValue",
	YBindingPath = "YValue"
};
chart.Series.Add(stackingLineSeries4);

{% endhighlight %}

![StackedLine chart type in Xamarin.Android](charttypes_images/StackedLine.png)

### Dashed Stacked Lines

`PathEffect` property of the `StackingLineSeries` is used to render stacked line series with dashes.

{% highlight c# %}
[C#]

StackedLineSeries stackingLineSeries1 = new StackedLineSeries()
{ 
	ItemsSource = Data1,
	XBindingPath = "XValue",
    YBindingPath = "YValue" 
};
stackingLineSeries1.PathEffect = new DashPathEffect(new float[]{6,6}, 4);
chart.Series.Add(stackingLineSeries1);

StackedLineSeries stackingLineSeries2 = new StackedLineSeries()
{ 
	ItemsSource = Data2,
	XBindingPath = "XValue",
    YBindingPath = "YValue" 
};
stackingLineSeries2.PathEffect = new DashPathEffect(new float[]{6,6}, 4);
chart.Series.Add(stackingLineSeries2);

StackedLineSeries stackingLineSeries3 = new StackedLineSeries() 
{ 
	ItemsSource = Data3,
	XBindingPath = "XValue",
    YBindingPath = "YValue" 
};
stackingLineSeries3.PathEffect = new DashPathEffect(new float[]{6,6}, 4);
chart.Series.Add(stackingLineSeries3);

StackedLineSeries stackingLineSeries4 = new StackedLineSeries() 
{ 
	ItemsSource = Data3,
	XBindingPath = "XValue",
    YBindingPath = "YValue" 
};
stackingLineSeries4.PathEffect = new DashPathEffect(new float[]{6,6}, 4);
chart.Series.Add(stackingLineSeries4);

{% endhighlight %}


## 100% Stacked Line Chart

To render a 100% stacked Line chart, create an instance of [`StackingLine100Series`]() and add to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). You can use the following properties to customize the 100% stacked line appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the line.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the line.
* [`Alpha`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Alpha) - controls the transparency of the chart series.
* `PathEffect` - used to changed the dashes of the  stacked line series.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

StackingLine100Series stackingLine100Series1 = new StackingLine100Series()
{
	ItemsSource = Data1,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(stackingLine100Series1);

StackingLine100Series stackingLine100Series2 = new StackingLine100Series()
{
	ItemsSource = Data2,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(stackingLine100Series2);

StackingLine100Series stackingLine100Series3 = new StackingLine100Series()
{
	ItemsSource = Data3,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(stackingLine100Series3);

StackingLine100Series stackingLine100Series4 = new StackingLine100Series()
{
	ItemsSource = Data4,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(stackingLine100Series4);

{% endhighlight %}

![StackingLine100 chart type in Xamarin.Android](charttypes_images/StackingLine100.png)

## Area Chart

To render an area chart, create an instance of `AreaSeries` and add to the series collection of `SfChart`. You can use the following properties to customize the appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AreaSeries.html#Com_Syncfusion_Charts_AreaSeries_StrokeColor) – used to change the stroke color of the series.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

AreaSeries areaSeries = new AreaSeries()
{
	ItemsSource = Data,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(areaSeries);

{% endhighlight %}

![Area chart type in Xamarin.Android](charttypes_images/charttypes_img2.png)

## Spline Area Chart

To render a spline area chart, create an instance of [`SplineAreaSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SplineAreaSeries.html) and add to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). You can use the following properties to customize the spline area appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AreaSeries.html#Com_Syncfusion_Charts_AreaSeries_StrokeColor) – used to change the stroke color of the series.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

SplineAreaSeries splineAreaSeries = new SplineAreaSeries()
{
	ItemsSource = Data,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(splineAreaSeries);

{% endhighlight %}

![SplineArea chart type in Xamarin.Android](charttypes_images/charttypes_img3.png)

### Spline Rendering Types

[`SplineType`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SplineAreaSeries.html#Com_Syncfusion_Charts_SplineAreaSeries_SplineType) allows you to change the spline area curve in series. 

The following types are used in [`SplineAreaSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SplineAreaSeries.html) as

* Natural
* Monotonic
* Cardinal
* Clamped

By default [`SplineType`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SplineAreaSeries.html#Com_Syncfusion_Charts_SplineAreaSeries_SplineType) value is [`Natural`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SplineType.html). 

The following code shows how to set the [`SplineType`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SplineAreaSeries.html#Com_Syncfusion_Charts_SplineAreaSeries_SplineType) value as [`Cardinal`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SplineType.html)

{% highlight c# %} 
[C#]

SplineAreaSeries splineAreaSeries = new SplineAreaSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Month", 
	YBindingPath = "Value",
	SplineType = SplineType.Cardinal
};
chart.Series.Add(splineAreaSeries);

{% endhighlight %}

## Step Area Chart

To render a step area chart, create an instance of [`StepAreaSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StepAreaSeries.html) and add to the Series collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). You can use the following properties to customize the step area appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AreaSeries.html#Com_Syncfusion_Charts_AreaSeries_StrokeColor) – used to change the stroke color of the series.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

StepAreaSeries stepAreaSeries = new StepAreaSeries();
{
	ItemsSource = Data,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(stepAreaSeries);

{% endhighlight %}

## Range Area Chart

To render a range area chart, create an instance of [`RangeAreaSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.RangeAreaSeries.html) and add to the Series collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html).

Since the [`RangeAreaSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.RangeAreaSeries.html)  requires two Y values for a point, your data should contain [`HighValues`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.RangeAreaSegment.html#Com_Syncfusion_Charts_RangeAreaSegment_HighValues) and [`LowValues`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.RangeAreaSegment.html#Com_Syncfusion_Charts_RangeAreaSegment_LowValues). [`High`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.RangeSeriesBase.html#Com_Syncfusion_Charts_RangeSeriesBase_High) and [`low`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.RangeSeriesBase.html#Com_Syncfusion_Charts_RangeSeriesBase_Low) value specifies the maximum and minimum range of the point.

{% highlight c# %}
[C#] 

SfChart chart = new SfChart();
...
	
RangeAreaSeries rangeAreaSeries = new RangeAreaSeries();
{
	ItemsSource = Data,
	XBindingPath = "XValue",
    High = "High",
	Low = "Low"
};
chart.Series.Add(rangeAreaSeries);

{% endhighlight %}

Following properties are used to customize the range area  segment appearance,

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.RangeAreaSeries.html#Com_Syncfusion_Charts_RangeAreaSeries_StrokeColor) – used to change the stroke color of the series.

## Stacked Area Chart

To render a stacked area chart, create an instance of [`StackingAreaSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingAreaSeries.html) and add to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). You can use the following properties to customize the stacked area appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingSeriesBase.html#Com_Syncfusion_Charts_StackingSeriesBase_StrokeColor) – used to change the stroke color of the series.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

StackingAreaSeries stackingAreaSeries1 = new StackingAreaSeries()
{
	ItemsSource = Data1,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(stackingAreaSeries1);

StackingAreaSeries stackingAreaSeries2 = new StackingAreaSeries()
{
	ItemsSource = Data2,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(stackingAreaSeries2);

StackingAreaSeries stackingAreaSeries3 = new StackingAreaSeries()
{
	ItemsSource = Data3,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(stackingAreaSeries3);

{% endhighlight %}

![StackedArea chart type in Xamarin.Android](charttypes_images/charttypes_img4.png)

## 100% Stacked Area Chart

To render a 100% stacked area chart, create an instance of [`StackingArea100Series`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingArea100Series.html) and add to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). You can use the following properties to customize the 100% stacked area appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingSeriesBase.html#Com_Syncfusion_Charts_StackingSeriesBase_StrokeColor) – used to change the stroke color of the series.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

StackingArea100Series stackingArea100Series1 = new StackingArea100Series()
{
	ItemsSource = Data1,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(stackingArea100Series1);

StackingArea100Series stackingArea100Series2 = new StackingArea100Series()
{
	ItemsSource = Data2,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(stackingArea100Series2);

StackingArea100Series stackingArea100Series3 = new StackingArea100Series()
{
	ItemsSource = Data3,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(stackingArea100Series3);

{% endhighlight %}

![StackingArea100 chart type in Xamarin.Android](charttypes_images/charttypes_img5.png)

## Spline Range Area Chart

To render a Spline range Area chart, create an instance of [`SplineRangeAreaSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SplineRangeAreaSeries.html) and add to the series collection of SfChart.

Since the SplineRangeAreaSeries requires two Y values for a point, your data should contain [`HighValues`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.RangeAreaSegment.html#Com_Syncfusion_Charts_RangeAreaSegment_HighValues) and [`LowValues`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.RangeAreaSegment.html#Com_Syncfusion_Charts_RangeAreaSegment_LowValues) values. [`High`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.RangeSeriesBase.html#Com_Syncfusion_Charts_RangeSeriesBase_High) and [`low`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.RangeSeriesBase.html#Com_Syncfusion_Charts_RangeSeriesBase_Low) value specifies the maximum and minimum range of the point.

Following properties are used to customize the spline range area segment appearance,

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingSeriesBase.html#Com_Syncfusion_Charts_StackingSeriesBase_StrokeColor) – used to change the stroke color of the series.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

SplineRangeAreaSeries splineRangeAreaSeries = new SplineRangeAreaSeries() 
{ 
	ItemsSource = Data,
	XBindingPath = "XValue", 
	High = "High", 
	Low = "Low" 
};
chart.Series.Add(splineRangeAreaSeries);

{% endhighlight %}

### Spline Rendering Types

[`SplineType`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SplineRangeAreaSeries.html#Com_Syncfusion_Charts_SplineRangeAreaSeries_SplineType) property allows you to change the spline range area curve in series.

The following types can be used for [`SplineRangeAreaSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SplineRangeAreaSeries.html)

* Natural 
* Monotonic
* Cardinal
* Clamped

By default SplineType value is [`Natural`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SplineType.html).

The following code shows how to set the [`SplineType`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SplineRangeAreaSeries.html#Com_Syncfusion_Charts_SplineRangeAreaSeries_SplineType) value as [`Cardinal`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SplineType.html)

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

SplineRangeAreaSeries splineRangeAreaSeries = new SplineRangeAreaSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Month", 
	YBindingPath = "Value",
	SplineType = SplineType.Cardinal
};
chart.Series.Add(splineRangeAreaSeries);

{% endhighlight %}

## Column Chart

To render a column chart, create an instance of [`ColumnSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ColumnSeries.html) and add to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). You can use the following properties to configure the column segment.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ColumnSeries.html#Com_Syncfusion_Charts_ColumnSeries_StrokeColor) – used to change the stroke color of the series. 
* [`Spacing`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ColumnSeries.html#Com_Syncfusion_Charts_ColumnSeries_Spacing) - used to change the spacing between two segments. The default value of spacing is 0, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available space, respectively.
* [`Width`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ColumnSeries.html#Com_Syncfusion_Charts_ColumnSeries_Width) - used to change the width of the rectangle. The default value of the width is 0.8, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available width, respectively. 
* [`DataMarkerPosition`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ColumnSeries.html#Com_Syncfusion_Charts_ColumnSeries_DataMarkerPosition) - used to change the position of data marker. 
* [`CornerRadius`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ColumnSeries.html#Com_Syncfusion_Charts_ColumnSeries_CornerRadius) -  used to add the rounded corners to the rectangle. The [`TopLeft`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_TopLeft), [`TopRight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_TopRight), [`BottomLeft`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_BottomLeft) and [`BottomRight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_BottomRight) of [`ChartCornerRadius`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html) properties are used to set the radius value for each corner.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

ColumnSeries columnSeries = new ColumnSeries()
{
	ItemsSource = Data,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(columnSeries);

{% endhighlight %}

![Column chart type in Xamarin.Android](charttypes_images/charttypes_img6.png)

### Overlapped placement

By default, all the column series which has the same x and y axes are placed side by side in a chart. If you want place the series one over the other (overlapped), set the [`SideBySideSeriesPlacement`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html#Com_Syncfusion_Charts_ChartBase_SideBySideSeriesPlacement) property of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html) to false and configure the Width property to differentiate the series. The following code snippet and screenshot illustrate the overlapped placement of column series.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart()
  {
      SideBySideSeriesPlacement = false
  };
 chart.PrimaryAxis = new CategoryAxis();
 chart.SecondaryAxis = new NumericalAxis();
 ColumnSeries series1 = new ColumnSeries()
 {
                ItemsSource = view.Data1,
                XBindingPath = "Month",
                YBindingPath = "Year2014"
 };
 ColumnSeries series2 = new ColumnSeries()
 {
                ItemsSource = view.Data2,
                XBindingPath = "Month",
                YBindingPath = "Year2015",
                 Width="0.5"
 };

chart.Series.Add(series1);
chart.Series.Add(series2);

{% endhighlight %}

![Overlapped placement support in Xamarin.Android Chart](charttypes_images/SideBySide-false.png)

## Histogram Chart

To render a histogram chart, create an instance of [`HistogramSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.HistogramSeries.html), and add it to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html).

Histogram chart provides a visual display of large amount of data that are difficult to understand in a tabular or data grid form.

You can customize intervals using the [`Interval`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.HistogramSeries.html#Com_Syncfusion_Charts_HistogramSeries_Interval) property and collapse the normal distribution curve using the [`ShowNormalDistributionCurve`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.HistogramSeries.html#Com_Syncfusion_Charts_HistogramSeries_ShowNormalDistributionCurve) property.  You can use the following properties to customize the appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.HistogramSeries.html#Com_Syncfusion_Charts_HistogramSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.HistogramSeries.html#Com_Syncfusion_Charts_HistogramSeries_StrokeColor) – used to change the stroke color of the series.
* [`CurveColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.HistogramSeries.html#Com_Syncfusion_Charts_HistogramSeries_CurveColor) – used to change the color of the normal distribution curve.
* [`DataMarkerPosition`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.HistogramSeries.html#Com_Syncfusion_Charts_HistogramSeries_DataMarkerPosition) - used to position the data marker at [`Bottom`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DataMarkerPosition.html), Top and Center of the rectangle.
{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

HistogramSeries histogramSeries = new HistogramSeries()
{
	ItemsSource = Data,
	XBindingPath = "XValue",
	YBindingPath = "YValue",   
	Interval = 20
};
chart.Series.Add(histogramSeries);

{% endhighlight %}

![Histogram chart type in Xamarin.Android](charttypes_images/charttypes_img49.png)

## Range Column Chart

To render a range column chart, create an instance of [`RangeColumnSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.RangeColumnSeries.html) and add to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). 

Since the [`RangeColumnSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.RangeColumnSeries.html) requires two Y values for a point, your data should contain high and low values. [`High`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.RangeSeriesBase.html#Com_Syncfusion_Charts_RangeSeriesBase_High) and [`Low`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.RangeSeriesBase.html#Com_Syncfusion_Charts_RangeSeriesBase_Low) value specifies the maximum and minimum range of the point. 

{% highlight c# %}
[C#] 

SfChart chart = new SfChart();
...
	
RangeColumnSeries rangeColumnSeries = new RangeColumnSeries()
{
	ItemsSource = Data,
	XBindingPath = "XValue",
    High = "High",
	Low = "Low"
}
	
chart.Series.Add(rangeColumnSeries);

{% endhighlight %}

Following properties are used to customize the range column segment appearance,

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.RangeColumnSeries.html#Com_Syncfusion_Charts_RangeColumnSeries_StrokeColor) – used to change the stroke color of the series.
* [`Spacing`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.RangeColumnSeries.html#Com_Syncfusion_Charts_RangeColumnSeries_Spacing) - used to change the spacing between two segments. The default value of spacing is 0, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available space, respectively.
* [`Width`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.RangeColumnSeries.html#Com_Syncfusion_Charts_RangeColumnSeries_Width) - used to change the width of the rectangle. The default value of the width is 0.8, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available width, respectively. 
* [`CornerRadius`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.RangeColumnSeries.html#Com_Syncfusion_Charts_RangeColumnSeries_CornerRadius) - used to add the rounded corners to the rectangle. The [`TopLeft`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_TopLeft), [`TopRight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_TopRight), [`BottomLeft`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_BottomLeft) and [`BottomRight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_BottomRight) of [`ChartCornerRadius`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html) properties are used to set the radius value for each corner.


![RangeColumn chart type in Xamarin.Android](charttypes_images/charttypes_img7.png)

## Stacked Column Chart

To render a stacked column chart, create an instance of [`StackingColumnSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingColumnSeries.html) and add to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). You can use the following properties to configure the stacked column segment.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingSeriesBase.html#Com_Syncfusion_Charts_StackingSeriesBase_StrokeColor) – used to change the stroke color of the series.
* [`Spacing`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingColumnSeries.html#Com_Syncfusion_Charts_StackingColumnSeries_Spacing) -  used to change the spacing between two segments. The default value of spacing is 0, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available space, respectively.
* [`Width`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingColumnSeries.html#Com_Syncfusion_Charts_StackingColumnSeries_Width) - used to change the width of the rectangle. The default value of the width is 0.8, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available width, respectively. 
* [`DataMarkerPosition`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingColumnSeries.html#Com_Syncfusion_Charts_StackingColumnSeries_DataMarkerPosition) - used to change the position of data marker.
* [`CornerRadius`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingColumnSeries.html#Com_Syncfusion_Charts_StackingColumnSeries_CornerRadius) - used to add the rounded corners to the rectangle. The [`TopLeft`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_TopLeft), [`TopRight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_TopRight), [`BottomLeft`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_BottomLeft) and [`BottomRight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_BottomRight) of [`ChartCornerRadius`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html) properties are used to set the radius value for each corner.


{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

StackingColumnSeries stackingColumnSeries1 = new StackingColumnSeries()
{
	ItemsSource = Data1,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(stackingColumnSeries1);

StackingColumnSeries stackingColumnSeries2 = new StackingColumnSeries()
{
	ItemsSource = Data2,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(stackingColumnSeries2);

StackingColumnSeries stackingColumnSeries3 = new StackingColumnSeries()
{
	ItemsSource = Data3,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(stackingColumnSeries3);

{% endhighlight %}

![StackingColumn chart type in Xamarin.Android](charttypes_images/charttypes_img8.png)

## 100% Stacked Column Chart

To render a 100% stacked column chart, create an instance of [`StackingColumn100Series`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingColumn100Series.html) and add to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). You can use the following properties to configure the 100% stacked column segment.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingSeriesBase.html#Com_Syncfusion_Charts_StackingSeriesBase_StrokeColor) – used to change the stroke color of the series.
* [`Spacing`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingColumnSeries.html#Com_Syncfusion_Charts_StackingColumnSeries_Spacing) - used to change the spacing between two segments. The default value of spacing is 0, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available space, respectively.
* [`Width`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingColumnSeries.html#Com_Syncfusion_Charts_StackingColumnSeries_Width) - used to change the width of the rectangle. The default value of the width is 0.8, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available width, respectively. 
* [`DataMarkerPosition`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingColumnSeries.html#Com_Syncfusion_Charts_StackingColumnSeries_DataMarkerPosition) - used to change the position of data marker.
* [`CornerRadius`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingColumnSeries.html#Com_Syncfusion_Charts_StackingColumnSeries_CornerRadius) - used to add the rounded corners to the rectangle. The [`TopLeft`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_TopLeft), [`TopRight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_TopRight), [`BottomLeft`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_BottomLeft) and [`BottomRight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_BottomRight) of [`ChartCornerRadius`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html) properties are used to set the radius value for each corner.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

StackingColumn100Series stackingColumn100Series1 = new StackingColumn100Series()
{
	ItemsSource = Data1,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(stackingColumn100Series1);

StackingColumn100Series stackingColumn100Series2 = new StackingColumn100Series()
{
	ItemsSource = Data2,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(stackingColumnSeries2);

StackingColumn100Series stackingColumn100Series3 = new StackingColumn100Series()
{
	ItemsSource = Data3,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(stackingColumn100Series3);

{% endhighlight %}


![StackingColumn100 chart type in Xamarin.Android Chart](charttypes_images/charttypes_img9.png)

## Bar Chart

To render a bar chart, create an instance of [`BarSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BarSeries.html) and add to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). You can use the following properties to configure the bar segment.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BarSeries.html#Com_Syncfusion_Charts_BarSeries_StrokeColor) – used to change the stroke color of the series.
* [`Spacing`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BarSeries.html#Com_Syncfusion_Charts_BarSeries_Spacing) -  used to change the spacing between two segments. The default value of spacing is 0, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available space, respectively.
* [`Width`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BarSeries.html#Com_Syncfusion_Charts_BarSeries_Width) - used to change the width of the rectangle. The default value of the width is 0.8, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available width, respectively. 
* [`DataMarkerPosition`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BarSeries.html#Com_Syncfusion_Charts_BarSeries_DataMarkerPosition) - used to change the position of data marker.
* [`CornerRadius`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BarSeries.html#Com_Syncfusion_Charts_BarSeries_CornerRadius) -used to add the rounded corners to the rectangle. The [`TopLeft`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_TopLeft), [`TopRight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_TopRight), [`BottomLeft`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_BottomLeft) and [`BottomRight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_BottomRight) of [`ChartCornerRadius`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html) properties are used to set the radius value for each corner.


{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

BarSeries barSeries = new BarSeries()
{
	ItemsSource = Data,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(barSeries);

{% endhighlight %}

![Bar chart type in Xamarin.Android](charttypes_images/charttypes_img10.png)

## Stacked Bar Chart

To render a stacked bar chart, create an instance of [`StackingBarSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingBarSeries.html) and add to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). You can use the following properties to configure the stacked bar segment.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingSeriesBase.html#Com_Syncfusion_Charts_StackingSeriesBase_StrokeColor) – used to change the stroke color of the series.
* [`Spacing`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingBarSeries.html#Com_Syncfusion_Charts_StackingBarSeries_Spacing) -  used to change the spacing between two segments. The default value of spacing is 0, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available space, respectively.
* [`Width`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingBarSeries.html#Com_Syncfusion_Charts_StackingBarSeries_Width) -used to change the width of the rectangle. The default value of the width is 0.8, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available width, respectively. 
* [`DataMarkerPosition`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingBarSeries.html#Com_Syncfusion_Charts_StackingBarSeries_DataMarkerPosition) - used to change the position of data marker.
* [`CornerRadius`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingBarSeries.html#Com_Syncfusion_Charts_StackingBarSeries_CornerRadius) - used to add the rounded corners to the rectangle. The [`TopLeft`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_TopLeft), [`TopRight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_TopRight), [`BottomLeft`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_BottomLeft) and [`BottomRight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_BottomRight) of [`ChartCornerRadius`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html) properties are used to set the radius value for each corner.


{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

StackingBarSeries stackingBarSeries1 = new StackingBarSeries()
{
	ItemsSource = Data1,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(stackingBarSeries1);

StackingBarSeries stackingBarSeries2 = new StackingBarSeries()
{
	ItemsSource = Data2,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(stackingBarSeries2);

StackingBarSeries stackingBarSeries3 = new StackingBarSeries()
{
	ItemsSource = Data3,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(stackingBarSeries3);

{% endhighlight %}

![StackingBar chart type in Xamarin.Android](charttypes_images/charttypes_img11.png)

## 100% Stacked Bar Chart

To render a 100% stacked bar chart, create an instance of [`StackingBar100Series`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingBar100Series.html) and add to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). You can use the following properties to configure the 100% stacked bar segment.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingSeriesBase.html#Com_Syncfusion_Charts_StackingSeriesBase_StrokeColor) – used to change the stroke color of the series.
* [`Spacing`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingBarSeries.html#Com_Syncfusion_Charts_StackingBarSeries_Spacing) -  used to change the spacing between two segments. The default value of spacing is 0, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available space, respectively.
* [`Width`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingBarSeries.html#Com_Syncfusion_Charts_StackingBarSeries_Width) - used to change the width of the rectangle. The default value of the width is 0.8, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available width, respectively. 
* [`DataMarkerPosition`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingBarSeries.html#Com_Syncfusion_Charts_StackingBarSeries_DataMarkerPosition) - used to change the position of data marker.
* [`CornerRadius`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StackingBarSeries.html#Com_Syncfusion_Charts_StackingBarSeries_CornerRadius) - used to add the rounded corners to the rectangle. The [`TopLeft`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_TopLeft), [`TopRight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_TopRight), [`BottomLeft`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_BottomLeft) and [`BottomRight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html#Com_Syncfusion_Charts_ChartCornerRadius_BottomRight) of [`ChartCornerRadius`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartCornerRadius.html) properties are used to set the radius value for each corner.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

StackingBar100Series stackingBar100Series1 = new StackingBar100Series()
{
	ItemsSource = Data1,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(stackingBar100Series1);

StackingBar100Series stackingBar100Series2 = new StackingBar100Series()
{
	ItemsSource = Data2,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(stackingBar100Series2);

StackingBar100Series stackingBar100Series3 = new StackingBar100Series()
{
	ItemsSource = Data3,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(stackingBar100Series3);

{% endhighlight %}

![StackingBar100 chart type in Xamarin.Android](charttypes_images/charttypes_img12.png)

## Spline Chart

To render a spline chart, create an instance of [`SplineSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SplineSeries.html) and add to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). You can use the following properties to customize the spline segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

SplineSeries splineSeries = new SplineSeries()
{
	ItemsSource = Data,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(splineSeries);

{% endhighlight %}

![Spline chart type in Xamarin.Android](charttypes_images/charttypes_img13.png)

### Dashed Lines

[`PathEffect`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SplineSeries.html#Com_Syncfusion_Charts_SplineSeries_PathEffect) property of the [`SplineSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SplineSeries.html) is used to render spline series with dashes.

{% highlight c# %} 
[C#]

SplineSeries splineSeries = new SplineSeries()
{
	ItemsSource = Data,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};

splineSeries.PathEffect = new DashPathEffect(new float[] {5, 6}, 2);
chart.Series.Add(splineSeries);

{% endhighlight %}

### Spline Rendering Types

[`SplineType`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SplineSeries.html#Com_Syncfusion_Charts_SplineSeries_SplineType) allows you to change the spline curve in series. 

The following types are used in [`SplineSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SplineSeries.html) as

* Natural
* Monotonic
* Cardinal
* Clamped

By default [`SplineType`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SplineSeries.html#Com_Syncfusion_Charts_SplineSeries_SplineType) value is [`Natural`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SplineType.html).

The following code shows how to set the [`SplineType`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SplineSeries.html#Com_Syncfusion_Charts_SplineSeries_SplineType) value as [`Cardinal`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SplineType.html)

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

SplineSeries splineSeries = new SplineSeries() 
{ 
	ItemsSource = Data, 
	XBindingPath = "Month", 
	YBindingPath = "Value",
	SplineType = SplineType.Cardinal
};
chart.Series.Add(splineSeries);

{% endhighlight %}

## Fast Line Chart

[`FastLineSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FastLineSeries.html) is a line chart, but it loads faster than [`LineSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.LineSeries.html). You can use this when there are large number of points to be loaded in chart. To render a fast line chart, create an instance of [`FastLineSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FastLineSeries.html) and add to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). You can use the following properties to customize the fast line segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

FastLineSeries fastLineSeries = new FastLineSeries()
{
	ItemsSource = Data,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(fastLineSeries);

{% endhighlight %}

![FastLine chart type in Xamarin.Android](charttypes_images/charttypes_img14.png)

### Dashed Lines

[`PathEffect`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FastLineSeries.html#Com_Syncfusion_Charts_FastLineSeries_PathEffect) property of the [`FastLineSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FastLineSeries.html) is used to render fast line series with dashes.

{% highlight c# %}
[C#]

FastLineSeries fastLineSeries = new FastLineSeries() 
{ 
	ItemsSource = Data,
	XBindingPath = "XValue",
    YBindingPath = "YValue" 
};
fastLineSeries.PathEffect = new DashPathEffect(new float[]{6,6}, 4);

{% endhighlight %}

![Dashed lines support for FastLineSeries in Xamarin.Android Chart](charttypes_images/charttypes_img15.png)

### EnableAntiAliasing

Since [`FastLineSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FastLineSeries.html) can be loaded with a large number of points, the rendering of series should be smooth. This requirement can be achieved by setting [`EnableAntiAliasing`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FastLineSeries.html#Com_Syncfusion_Charts_FastLineSeries_EnableAntiAliasing) property of [`FastLineSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FastLineSeries.html) as false.

## Step Line Chart

To render a step line chart, create an instance of [`StepLineSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StepLineSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html#Com_Syncfusion_Charts_ChartBase_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). You can use the following properties to customize the stepline segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

StepLineSeries stepLineSeries = new StepLineSeries()
{
	ItemsSource = Data,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(stepLineSeries);

{% endhighlight %}

![StepLine chart type in Xamarin.Android](charttypes_images/charttypes_img41.png)

## Bubble Chart

To render a bubble chart, create an instance of [`BubbleSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BubbleSeries.html) and add to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). 

Bubble chart requires 3 fields (X, Y and Size) to plot a point. Here [`Size`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BubbleSeries.html#Com_Syncfusion_Charts_BubbleSeries_Size) is used to specify the size of each bubble segment. 

{% highlight c# %}
[C#]

SfChart chart = new SfChart();
...
	   
BubbleSeries bubbleSeries = new BubbleSeries() 
{ 
	ItemsSource = Data,
	XBindingPath = "XValue",
    YBindingPath = "YValue",
	Size = "Size" 
};
chart.Series.Add(bubbleSeries);

{% endhighlight %}

Following properties are used to customize the bubble segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BubbleSeries.html#Com_Syncfusion_Charts_BubbleSeries_StrokeColor) – used to change the stroke color of the series.
* [`MinimumRadius`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BubbleSeries.html#Com_Syncfusion_Charts_BubbleSeries_MinimumRadius) – used to change the minimum size of the series.
* [`MaximumRadius`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BubbleSeries.html#Com_Syncfusion_Charts_BubbleSeries_MaximumRadius) – used to change the maximum size of the series.

![Bubble chart type in Xamarin.Android](charttypes_images/charttypes_img16.png)

## Scatter Chart	

To render a scatter chart, create an instance of [`ScatterSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ScatterSeries.html) and add to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). You can use the following properties to customize the scatter segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ScatterSeries.html#Com_Syncfusion_Charts_ScatterSeries_StrokeColor) – used to change the stroke color of the series.
* [`ScatterWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ScatterSeries.html#Com_Syncfusion_Charts_ScatterSeries_ScatterWidth) – used to change the width of the series.
* [`ScatterHeight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ScatterSeries.html#Com_Syncfusion_Charts_ScatterSeries_ScatterHeight) – used to change the height of the series.
* [`ShapeType`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ScatterSeries.html#Com_Syncfusion_Charts_ScatterSeries_ShapeType) - used to change the rendering shape of scatter series. The available shapes are [`Cross`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartScatterShapeType.html), diamond, ellipse, hexagon, inverted triangle, pentagon, plus, rectangle and triangle.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

ScatterSeries scatterSeries = new ScatterSeries()
{
    ScatterHeight = 15,
    ScatterWidth = 15,
	ShapeType = ChartScatterShapeType.Ellipse,
    ItemsSource = Data,
	XBindingPath = "XValue",
    YBindingPath = "YValue"
};
chart.Series.Add(scatterSeries);

{% endhighlight %}

![Scatter chart type in Xamarin.Android](charttypes_images/charttypes_img17.png)

## Fast Scatter Chart

The [`FastScatterSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FastScatterSeries.html) is a special kind of scatter series that renders a collection with a huge number of data points. You can use the following properties to customize the appearance of a fast scatter point.


* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FastScatterSeries.html#Com_Syncfusion_Charts_FastScatterSeries_StrokeColor) – used to change the stroke color of series.
* [`ScatterWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FastScatterSeries.html#Com_Syncfusion_Charts_FastScatterSeries_ScatterWidth) – used to change the width of series.
* [`ScatterHeight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FastScatterSeries.html#Com_Syncfusion_Charts_FastScatterSeries_ScatterHeight) – used to change the height of series.
* [`ShapeType`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FastScatterSeries.html#Com_Syncfusion_Charts_FastScatterSeries_ShapeType) - used to change the rendering shape of fast scatter series. The available shapes are [`Cross`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartScatterShapeType.html), [`Diamond`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartScatterShapeType.html), [`Ellipse`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartScatterShapeType.html), [`Hexagon`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartScatterShapeType.html), [`InvertedTriangle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartScatterShapeType.html), [`Pentagon`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartScatterShapeType.html), [`Plus`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartScatterShapeType.html), [`Rectangle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartScatterShapeType.html) and [`Triangle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartScatterShapeType.html).
* [`EnableAntiAliasing`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FastScatterSeries.html#Com_Syncfusion_Charts_FastScatterSeries_EnableAntiAliasing) – Enables or disables the smoothness of series. Default value of [`EnableAntiAliasing`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FastScatterSeries.html#Com_Syncfusion_Charts_FastScatterSeries_EnableAntiAliasing) property is true.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

FastScatterSeries fastScatterSeries = new FastScatterSeries()
{
	ScatterHeight = 15,
	ScatterWidth = 15,
	ShapeType = ChartScatterShapeType.Ellipse,
	ItemsSource = Data,	
	XBindingPath = "XValue",
	YBindingPath = "YValue"
};
chart.Series.Add(fastScatterSeries);

{% endhighlight %}

![FastScatter chart type in Xamarin.Android](charttypes_images/charttypes_img17.png)


## OHLC Chart

To render an OHLC chart, create an instance of [`HiLoOpenCloseSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.HiLoOpenCloseSeries.html) and add to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html).

OHLC chart requires [`XValue`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataPoint.html#Com_Syncfusion_Charts_ChartDataPoint_XValue), [`Open`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataPoint.html#Com_Syncfusion_Charts_ChartDataPoint_Open), [`High`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataPoint.html#Com_Syncfusion_Charts_ChartDataPoint_High), [`Low`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataPoint.html#Com_Syncfusion_Charts_ChartDataPoint_Low) and [`Close`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataPoint.html#Com_Syncfusion_Charts_ChartDataPoint_Close) to plot a point. 

{% highlight c# %}
[C#]

SfChart chart = new SfChart();
...
	   
HiLoOpenCloseSeries hiLoOpenCloseSeries = new HiLoOpenCloseSeries() 
{ 
	ItemsSource = Data,
	XBindingPath = "XValue",
    High = "High",
	Low = "Low",
	Open = "Open",
	Close = "Close" 
};
chart.Series.Add(hiLoOpenCloseSeries);

{% endhighlight %}

You can use the following properties to customize the HiLoOpenCloseSeries segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.

![HiLoOpenClose chart type in Xamarin.Android](charttypes_images/charttypes_img18.png)

### Bull and Bear Color	

In OHLC chart, [`BullFillColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FinancialSeriesBase.html#Com_Syncfusion_Charts_FinancialSeriesBase_BullFillColor) property is used to specify a fill color for the segments that indicates an increase in stock price in the measured time interval and [`BearFillColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FinancialSeriesBase.html#Com_Syncfusion_Charts_FinancialSeriesBase_BearFillColor) property is used to specify a fill color for the segments that indicates a decrease in stock price in the measured time interval.

{% highlight c# %}
[C#]

HiLoOpenCloseSeries hiLoOpenCloseSeries = new HiLoOpenCloseSeries()
{
    ItemsSource = Data,
	XBindingPath = "XValue",
    High = "High",
	Low = "Low",
	Open = "Open",
	Close = "Close", 
    BearFillColor = Color.Blue,
    BullFillColor = Color.Purple
};

{% endhighlight %}

![Bull and bear Color support for financial series in Xamarin.Android Chart](charttypes_images/charttypes_img19.png)

## Candle Chart

To render a candle chart, create an instance of [`CandleSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CandleSeries.html) and add to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html).

Candle chart requires [`XValue`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataPoint.html#Com_Syncfusion_Charts_ChartDataPoint_XValue), [`Open`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataPoint.html#Com_Syncfusion_Charts_ChartDataPoint_Open), [`High`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataPoint.html#Com_Syncfusion_Charts_ChartDataPoint_High), [`Low`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataPoint.html#Com_Syncfusion_Charts_ChartDataPoint_Low) and [`Close`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataPoint.html#Com_Syncfusion_Charts_ChartDataPoint_Close) to plot a point. 

{% highlight c# %}
[C#]

SfChart chart = new SfChart();
...
	   
CandleSeries candleSeries = new CandleSeries() 
{ 
	ItemsSource = Data,
	XBindingPath = "XValue",
    High = "High",
	Low = "Low",
	Open = "Open",
	Close = "Close"  
};
chart.Series.Add(candleSeries);

{% endhighlight %}

You can use the following properties to customize the candle segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CandleSeries.html#Com_Syncfusion_Charts_CandleSeries_StrokeColor) – used to change the stroke color of the series.
* [`Spacing`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FinancialSeriesBase.html#Com_Syncfusion_Charts_FinancialSeriesBase_Spacing) -  used to change the spacing between two segments.
* [`Width`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FinancialSeriesBase.html#Com_Syncfusion_Charts_FinancialSeriesBase_Width) - used to change the width of the candle.

![Candle chart type in Xamarin.Android](charttypes_images/charttypes_img20.png)

## EnableSolidCandles

In Candle Series, [`EnableSolidCandles`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CandleSeries.html#Com_Syncfusion_Charts_CandleSeries_EnableSolidCandles) property is used to specify whether the candle segment should be filled or hollow. The default value of this property is false.

{% highlight c# %}
[C#]

CandleSeries series = new CandleSeries();
series.ItemsSource = viewModel.FinancialData;
series.XBindingPath = "Date";
series.High = "High";
series.Low = "Low";
series.Open = "Open";
series.Close = "Close";
series.EnableSolidCandles = true;
chart.Series.Add(series);

{% endhighlight %}

### Bull and Bear Color

In Candle chart, [`BullFillColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FinancialSeriesBase.html#Com_Syncfusion_Charts_FinancialSeriesBase_BullFillColor) property is used to specify a fill color for the segments that indicates an increase in stock price in the measured time interval and [`BearFillColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FinancialSeriesBase.html#Com_Syncfusion_Charts_FinancialSeriesBase_BearFillColor) property is used to specify a fill color for the segments that indicates a decrease in stock price in the measured time interval.

{% highlight c# %}
[C#]

CandleSeries candleSeries = new CandleSeries()
{
    ItemsSource = Data,
	XBindingPath = "XValue",
    High = "High",
	Low = "Low",
	Open = "Open",
	Close = "Close", 
    BearFillColor = Color.Blue,
    BullFillColor = Color.Purple
};

{% endhighlight %}

![Bull and bear Color support for financial series in Xamarin.Android Chart](charttypes_images/charttypes_img21.png)

## Radar Chart

To render a radar chart, create an instance of [`RadarSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.RadarSeries.html) and add to the Series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). 

### Draw type

[`DrawType`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.PolarSeries.html#Com_Syncfusion_Charts_PolarSeries_DrawType) property is used to specify the radar series rendering type. Following are the two options you can set to this property,

* [`Line`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.PolarChartDrawType.html) – data points are visualized using line series.
* [`Area`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.PolarChartDrawType.html) – data points are visualized using area series.

{% highlight c# %}
[C#]

RadarSeries radarSeries = new RadarSeries();

radarSeries.ItemsSource = Data;

radarSeries.XBindingPath = "XValue";

radarSeries.YBindingPath = "YValue";

radarSeries.DrawType = PolarChartDrawType.Line;

{% endhighlight %}

![Draw type support for radar series in Xamarin.Android Chart](charttypes_images/charttypes_img42.png)

### Customize the appearance

You can use the following properties to customize the appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.PolarSeries.html#Com_Syncfusion_Charts_PolarSeries_StrokeColor) – used to change the stroke color of the series, when draw type is set to Area.
* [`PathEffect`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.PolarSeries.html#Com_Syncfusion_Charts_PolarSeries_PathEffect) – used to render lines with dashes when the draw type is set to 'Line'.

{% highlight c# %}
[C#]

RadarSeries radarSeries = new RadarSeries();

radarSeries.ItemsSource = Data;

radarSeries.XBindingPath = "XValue";

radarSeries.YBindingPath = "YValue";

radarSeries.Color = Color.Aqua;

radarSeries.StrokeWidth = 3;

radarSeries.StrokeColor = Color.Blue;

{% endhighlight %}

![Customizing the appearance of radar series in Xamarin.Android Chart](charttypes_images/charttypes_img43.png)

### Closed Series

[`Closed`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.PolarSeries.html#Com_Syncfusion_Charts_PolarSeries_Closed) property is used to determine, whether to connect the first and last data point of the series. By default, value is `true`.

{% highlight c# %}
[C#]

RadarSeries radarSeries = new RadarSeries();

radarSeries.ItemsSource = Data;

radarSeries.XBindingPath = "XValue";

radarSeries.YBindingPath = "YValue";

radarSeries.Closed = false;

{% endhighlight %}

![Closed radar series in Xamarin.Android Chart](charttypes_images/charttypes_img44.png)

### Radar start angle for primary axis

The start position of the radar series can be set by using [`PolarAngle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartAxis.html#Com_Syncfusion_Charts_ChartAxis_PolarAngle) property of axis. Default value of [`PolarAngle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartAxis.html#Com_Syncfusion_Charts_ChartAxis_PolarAngle) property is [`Rotate270`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartPolarAngle.html). [`PolarAngle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartAxis.html#Com_Syncfusion_Charts_ChartAxis_PolarAngle) property can be set for primary axis, secondary axis, or both axes.

{% highlight c# %}
[C#]

chart.PrimaryAxis = new CategoryAxis()
{
    PolarAngle = ChartPolarAngle.Rotate0
};

{% endhighlight %}

![Radar start angle support for primary axis in Xamarin.Android Chart](charttypes_images/radarangle_img1.png)

### Radar start angle for secondary axis

{% highlight c# %}
[C#]

chart.PrimaryAxis  = new CategoryAxis();

chart.SecondaryAxis =  new NumericalAxis() { PolarAngle = ChartPolarAngle.Rotate0 }; 

{% endhighlight %}

![Radar start angle support for secondary axis in Xamarin.Android Chart](charttypes_images/radarangle_img2.png)

### Radar start angle for both axis

{% highlight c# %}
[C#]

chart.PrimaryAxis  = new CategoryAxis(){ PolarAngle = ChartPolarAngle.Rotate0 };

chart.SecondaryAxis =  new NumericalAxis() { PolarAngle = ChartPolarAngle.Rotate0 }; 

{% endhighlight %}

![Radar start angle support for both axes in Xamarin.Android Chart](charttypes_images/radarangle_img3.png)

## Polar Chart

To render a polar chart, create an instance of [`PolarSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.PolarSeries.html) and add to the Series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). 

### Draw type 

[`DrawType`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.PolarSeries.html#Com_Syncfusion_Charts_PolarSeries_DrawType) property is used to specify the polar series rendering type. Following are the two options you can set to this property,

* [`Line`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.PolarChartDrawType.html) – data points are visualized using line series.
* [`Area`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.PolarChartDrawType.html) – data points are visualized using area series.

{% highlight c# %}
[C#]

PolarSeries polarSeries = new PolarSeries();

polarSeries.ItemsSource = Data;

polarSeries.XBindingPath = "XValue";

polarSeries.YBindingPath = "YValue";

polarSeries.DrawType = PolarChartDrawType.Line;

{% endhighlight %}

![Draw type support for polar series in Xamarin.Android Chart](charttypes_images/charttypes_img45.png)

N> You need to set [`XBindingPath`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_XBindingPath) and [`YBindingPath`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.PolarSeries.html#Com_Syncfusion_Charts_PolarSeries_YBindingPath) properties, so that SfChart would fetch values from the respective properties in the data model to plot the series.

### Customize the appearance

You can use the following properties to customize the appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.PolarSeries.html#Com_Syncfusion_Charts_PolarSeries_StrokeColor) – used to change the stroke color of the series, when draw type is set to Area.
* [`PathEffect`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.PolarSeries.html#Com_Syncfusion_Charts_PolarSeries_PathEffect) – used to render lines with dashes when the draw type is set to 'Line'.

{% highlight c# %}
[C#]

PolarSeries polarSeries = new PolarSeries();

polarSeries.ItemsSource = Data;

polarSeries.XBindingPath = "XValue";

polarSeries.YBindingPath = "YValue";

polarSeries.Color = Color.Aqua;

polarSeries.StrokeWidth = 3;

polarSeries.StrokeColor = Color.Blue;

{% endhighlight %}

![Customizing the appearance of polar series in Xamarin.Android Chart](charttypes_images/charttypes_img46.png)

### Closed Series

[`Closed`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.PolarSeries.html#Com_Syncfusion_Charts_PolarSeries_Closed) property is used to determine, whether to connect the first and last data point of the series. By default, value is true.

{% highlight c# %}
[C#]

PolarSeries polarSeries = new PolarSeries();

polarSeries.ItemsSource = Data;

polarSeries.XBindingPath = "XValue";

polarSeries.YBindingPath = "YValue";

polarSeries.Closed = false;

{% endhighlight %}

![Closed polar series in Xamarin.Android Chart](charttypes_images/charttypes_img47.png)

### Polar start angle for primary axis

The start position of the polar series can be set by using [`PolarAngle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartAxis.html#Com_Syncfusion_Charts_ChartAxis_PolarAngle) property of axis. Default value of [`PolarAngle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartAxis.html#Com_Syncfusion_Charts_ChartAxis_PolarAngle) property is [`Rotate270`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartPolarAngle.html). [`PolarAngle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartAxis.html#Com_Syncfusion_Charts_ChartAxis_PolarAngle) property can be set for primary axis, secondary axis, or both axes.

{% highlight c# %}
[C#]

chart.PrimaryAxis  = new CategoryAxis(){ PolarAngle = ChartPolarAngle.Rotate0 };

chart.SecondaryAxis = new NumericalAxis(); 

{% endhighlight %}

![Polar start angle support for primary axis in Xamarin.Android Chart](charttypes_images/polarangle_img1.png)

### Polar start angle for secondary axis

{% highlight c# %}
[C#]

chart.PrimaryAxis  = new CategoryAxis();

chart.SecondaryAxis =  new NumericalAxis() { PolarAngle = ChartPolarAngle.Rotate0 }; 

{% endhighlight %}

![Polar start angle support for secondary axis in Xamarin.Android Chart](charttypes_images/polarangle_img2.png)

### Polar start angle for both axis

{% highlight c# %}
[C#]

chart.PrimaryAxis  = new CategoryAxis(){ PolarAngle = ChartPolarAngle.Rotate0 };

chart.SecondaryAxis =  new NumericalAxis() { PolarAngle = ChartPolarAngle.Rotate0 }; 

{% endhighlight %}

![Polar start angle support for both axes in Xamarin.Android Chart](charttypes_images/polarangle_img3.png)

## Pie Chart

To render a pie chart, create an instance of [`PieSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.PieSeries.html) and add to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). You can use the following properties to customize the pie segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AccumulationSeries.html#Com_Syncfusion_Charts_AccumulationSeries_StrokeColor) – used to change the stroke color of the series.
* [`DataMarkerPosition`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CircularSeries.html#Com_Syncfusion_Charts_CircularSeries_DataMarkerPosition) - used to change the position of data marker.  Default position is [`Inside`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CircularSeriesDataMarkerPosition.html).

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

PieSeries pieSeries = new PieSeries()
{
    ItemsSource = Data,
	XBindingPath = "XValue",
	YBindingPath = "YValue",
};
chart.Series.Add(pieSeries);

{% endhighlight %}

N> You need to set [`XBindingPath`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_XBindingPath) and [`YBindingPath`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AccumulationSeries.html#Com_Syncfusion_Charts_AccumulationSeries_YBindingPath) properties, so that SfChart would fetch values from the respective properties in the data model to plot the series.

![Pie chart type in Xamarin.Android](charttypes_images/charttypes_img22.png)

### Changing the pie size

You can use [`CircularCoefficient`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CircularSeries.html#Com_Syncfusion_Charts_CircularSeries_CircularCoefficient) property to change the diameter of the pie chart with respect to the plot area. It ranges from 0 to 1 and the default value is `0.8`.

{% highlight c# %} 
[C#]

PieSeries pieSeries = new PieSeries()
{
    ItemsSource = Data,
	XBindingPath = "XValue",
	YBindingPath = "YValue",
	CircularCoefficient = 0.5f
};

{% endhighlight %}

![Changing the pie size in Xamarin.Android Chart](charttypes_images/charttypes_img23.png)

### Exploding a pie segment

You can explode a pie segment using [`ExplodeIndex`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AccumulationSeries.html#Com_Syncfusion_Charts_AccumulationSeries_ExplodeIndex) property and specify the explode radius using [`ExplodeRadius`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CircularSeries.html#Com_Syncfusion_Charts_CircularSeries_ExplodeRadius) property of [`PieSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.PieSeries.html).

{% highlight c# %} 
[C#]

PieSeries pieSeries = new PieSeries()
{
    ItemsSource = Data,
	XBindingPath = "XValue",
	YBindingPath = "YValue",
	ExplodeIndex = 1
};

{% endhighlight %}

![Exploding a pie segment support in Xamarin.Android Chart](charttypes_images/charttypes_img24.png)

### Exploding all the segments

Using [`ExplodeAll`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AccumulationSeries.html#Com_Syncfusion_Charts_AccumulationSeries_ExplodeAll) property of [`PieSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.PieSeries.html), you can explode all the pie segments.

{% highlight c# %} 
[C#]

PieSeries pieSeries = new PieSeries()
{
    ItemsSource = Data,
	XBindingPath = "XValue",
	YBindingPath = "YValue",
	ExplodeAll = true
};

{% endhighlight %}

Also, the segments can be exploded by touch using [`ExplodableOnTouch`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AccumulationSeries.html#Com_Syncfusion_Charts_AccumulationSeries_ExplodableOnTouch) property of [`DoughnutSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DoughnutSeries.html). Default value of this property is false.

![Exploding all the segments of pie series in Xamarin.Android Chart](charttypes_images/charttypes_img25.png)

### Sector of Pie

[`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html) allows you to render all the data points/segments in semi-pie, quarter-pie or in any sector using [`StartAngle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CircularSeries.html#Com_Syncfusion_Charts_CircularSeries_StartAngle) and [`EndAngle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CircularSeries.html#Com_Syncfusion_Charts_CircularSeries_EndAngle) properties.

{% highlight c# %} 
[C#]

PieSeries pieSeries = new PieSeries()
{
    ItemsSource = Data,
	XBindingPath = "XValue",
	YBindingPath = "YValue",
	StartAngle = 180,
	EndAngle = 360
};

{% endhighlight %}

![Sector support for pie series in Xamarin.Android Chart](charttypes_images/charttypes_img26.png)

### Group small data points into “others”

The small segments in the pie chart can be grouped into “others” category using the [`GroupTo`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CircularSeries.html#Com_Syncfusion_Charts_CircularSeries_GroupTo) and [`GroupMode`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CircularSeries.html#Com_Syncfusion_Charts_CircularSeries_GroupMode) properties of PieSeries. The [`GroupMode`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CircularSeries.html#Com_Syncfusion_Charts_CircularSeries_GroupMode) property is used to specify the grouping type based on slice [`Angle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.PieGroupMode.html), actual data point value, or [`Percentage`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.PieGroupMode.html), and the [`GroupTo`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CircularSeries.html#Com_Syncfusion_Charts_CircularSeries_GroupTo) property is used to set the limit to group data points into a single slice. The grouped segment is labeled as “Others” in legend and toggled as any other segment. The default value of the [`GroupTo`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CircularSeries.html#Com_Syncfusion_Charts_CircularSeries_GroupTo) property is [`double.NAN`], and [`GroupMode`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CircularSeries.html#Com_Syncfusion_Charts_CircularSeries_GroupMode) property is Value.

## Doughnut Chart

To render a doughnut chart, create an instance of [`DoughnutSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DoughnutSeries.html) and add to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). You can use the following properties to customize the doughnut segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AccumulationSeries.html#Com_Syncfusion_Charts_AccumulationSeries_StrokeColor) – used to change the stroke color of the series.
* [`DataMarkerPosition`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CircularSeries.html#Com_Syncfusion_Charts_CircularSeries_DataMarkerPosition) - used to change the position of data marker.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

DoughnutSeries doughnutSeries = new DoughnutSeries()
{
    ItemsSource = Data,
	XBindingPath = "XValue",
	YBindingPath = "YValue"
};
chart.Series.Add(doughnutSeries);

{% endhighlight %}

![Doughnut chart type in Xamarin.Android](charttypes_images/charttypes_img27.png)

### Stacked doughnut

Doughnut segments can be separated as individual circles using the [`IsStackedDoughnut`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DoughnutSeries.html#Com_Syncfusion_Charts_DoughnutSeries_IsStackedDoughnut) property. The following properties are used to customize the stacked doughnut chart:

* [`CapStyle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DoughnutSeries.html#Com_Syncfusion_Charts_DoughnutSeries_CapStyle) - Specifies the shape of the start and end points of the circular segment. The supported values are [`BothFlat`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DoughnutCapStyle.html), `BothCurve`, `StartCurve`, and `EndCurve`. The default value of the this property is [`BothFlat`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DoughnutCapstyle.html).
* [`Spacing`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DoughnutSeries.html#Com_Syncfusion_Charts_DoughnutSeries_Spacing) - Changes the spacing between two individual segments. The default value of spacing is 0, and the value ranges from 0 to 1. Here, 1 and 0 correspond to 100% and 0% of the available space, respectively.
* [`MaximumValue`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DoughnutSeries.html#Com_Syncfusion_Charts_DoughnutSeries_MaximumValue) - Represents the entire span of an individual circle. The default value of the this property is `double.NaN`.
* [`TrackColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DoughnutSeries.html#Com_Syncfusion_Charts_DoughnutSeries_TrackColor) - Changes the color of the track area.
* [`TrackBorderColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DoughnutSeries.html#Com_Syncfusion_Charts_DoughnutSeries_TrackBorderColor) - Changes the color of the track border.
* [`TrackBorderWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DoughnutSeries.html#Com_Syncfusion_Charts_DoughnutSeries_TrackBorderWidth) - Changes the width of the track border.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

DoughnutSeries doughnutSeries = new DoughnutSeries()
{
    ItemsSource = Data,
    XBindingPath = "XValue",
    YBindingPath = "YValue",
    IsStackedDoughnut = true,
    CapStyle = DoughnutCapStyle.BothCurve,
    Spacing = 0.4,
    MaximumValue = 100
};
chart.Series.Add(doughnutSeries);

{% endhighlight %}

![Stacked doughnut type in Xamarin.Android](charttypes_images/stacked_doughnut.png)

### Changing Doughnut inner radius

You can change the doughnut chart inner radius using [`DoughnutCoefficient`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DoughnutSeries.html#Com_Syncfusion_Charts_DoughnutSeries_DoughnutCoefficient) with respect to the plot area. It ranges from 0 to 1 and the default value is `0.4`.

{% highlight c# %} 
[C#]

DoughnutSeries doughnutSeries = new DoughnutSeries()
{
    ItemsSource = Data,
	XBindingPath = "XValue",
	YBindingPath = "YValue",
	DoughnutCoefficient = 0.6f
};

{% endhighlight %}

![DoughnutCoefficient support for doughnut series in Xamarin.Android Chart](charttypes_images/charttypes_img28.png)

### Changing the doughnut size

You can use the [`CircularCoefficient`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CircularSeries.html#Com_Syncfusion_Charts_CircularSeries_CircularCoefficient) property to change the diameter of the doughnut chart with respect to the plot area. It ranges from 0 to 1 and the default value is 0.8.

{% highlight c# %} 
[C#]

DoughnutSeries doughnutSeries = new DoughnutSeries()
{
    ItemsSource = Data,
	XBindingPath = "XValue",
	YBindingPath = "YValue",
	CircularCoefficient = 0.5f
};

{% endhighlight %}

![CircularCoefficient support for doughnut series in Xamarin.Android Chart](charttypes_images/charttypes_img29.png)

### Exploding a doughnut segment

Exploding a specific doughnut segment, you have to set the index to be exploded using [`ExplodeIndex`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AccumulationSeries.html#Com_Syncfusion_Charts_AccumulationSeries_ExplodeIndex) property of the series.

{% highlight c# %} 
[C#]

DoughnutSeries doughnutSeries = new DoughnutSeries()
{
    ItemsSource = Data,
	XBindingPath = "XValue",
	YBindingPath = "YValue",
	ExplodeIndex = 1
};

{% endhighlight %}

![Exploding a doughnut segment support in Xamarin.Android Chart](charttypes_images/charttypes_img30.png)

### Exploding all the segments

To explode all the segments, you have to enable [`ExplodeAll`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AccumulationSeries.html#Com_Syncfusion_Charts_AccumulationSeries_ExplodeAll) property of the series.

{% highlight c# %} 
[C#]

DoughnutSeries doughnutSeries = new DoughnutSeries()
{
    ItemsSource = Data,
	XBindingPath = "XValue",
	YBindingPath = "YValue",
	ExplodeAll = true
};

{% endhighlight %}

Also, the segments can be exploded by touch using [`ExplodableOnTouch`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AccumulationSeries.html#Com_Syncfusion_Charts_AccumulationSeries_ExplodableOnTouch) property of [`DoughnutSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DoughnutSeries.html). Default value of this property is false.

![Exploding all the segments of doughnut series in Xamarin.Android Chart](charttypes_images/charttypes_img31.png)

### Sector of Doughnut

[`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html) allows you to render all the data points/segments in semi-doughnut, quarter- doughnut or in any sector using [`StartAngle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CircularSeries.html#Com_Syncfusion_Charts_CircularSeries_StartAngle) and [`EndAngle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CircularSeries.html#Com_Syncfusion_Charts_CircularSeries_EndAngle) properties.

{% highlight c# %} 
[C#]

DoughnutSeries doughnutSeries = new DoughnutSeries()
{
    ItemsSource = Data,
	XBindingPath = "XValue",
	YBindingPath = "YValue",
	StartAngle = 180,
	EndAngle = 360
};

{% endhighlight %}

![Sector support for doughnut series in Xamarin.Android Chart](charttypes_images/charttypes_img32.png)

### Group small data points into “others”

The small segments in the doughnut chart can be grouped into “others” category using the [`GroupTo`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CircularSeries.html#Com_Syncfusion_Charts_CircularSeries_GroupTo) and [`GroupMode`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CircularSeries.html#Com_Syncfusion_Charts_CircularSeries_GroupMode) properties of DoughnutSeries. The [`GroupMode`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CircularSeries.html#Com_Syncfusion_Charts_CircularSeries_GroupMode) property is used to specify the grouping type based on slice angle, actual data point value, or percentage, and the [`GroupTo`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CircularSeries.html#Com_Syncfusion_Charts_CircularSeries_GroupTo) property is used to set the limit to group data points into a single slice. The grouped segment is labeled as “Others” in legend and toggled as any other segment. The default value of the [`GroupTo`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CircularSeries.html#Com_Syncfusion_Charts_CircularSeries_GroupTo) property is [`double.NAN`], and [`GroupMode`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CircularSeries.html#Com_Syncfusion_Charts_CircularSeries_GroupMode) property is Value.

### Add view to the center of doughnut chart

Any view can be added to the center of doughnut chart using the [`CenterView`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DoughnutSeries.html#Com_Syncfusion_Charts_DoughnutSeries_CenterView) property of [`DoughnutSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DoughnutSeries.html).

{% highlight C# %}
[C#]

TextView label = new TextView(this);
label.Text = "CenterView";
DoughnutSeries doughnutSeries = new DoughnutSeries()
{
	ItemsSource = Data,
	XBindingPath = "XValue",
	YBindingPath = "YValue",
	CenterView = label
}

{% endhighlight %}

![CenterView support for doughnut series in Xamarin.Android Chart](charttypes_images/charttypes_img48.png)

### InnerRadius

The [`InnerRadius`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DoughnutSeries.html#Com_Syncfusion_Charts_DoughnutSeries_InnerRadius) property of [`DoughnutSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DoughnutSeries.html) is used to get only the inner radius. Using this [`InnerRadius`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DoughnutSeries.html#Com_Syncfusion_Charts_DoughnutSeries_InnerRadius) value, you can provide [`CentreView`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DoughnutSeries.html#Com_Syncfusion_Charts_DoughnutSeries_CenterView) for series to avoid the view from being cropped outside the series.

## Pyramid Chart

To render a pyramid chart, create an instance of [`PyramidSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.PyramidSeries.html) and add to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). You can use the following properties to customize the pyramid segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AccumulationSeries.html#Com_Syncfusion_Charts_AccumulationSeries_StrokeColor) – used to change the stroke color of the series.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

PyramidSeries pyramidSeries = new PyramidSeries()
{
    ItemsSource = Data,
	XBindingPath = "XValue",
	YBindingPath = "YValue"
};
chart.Series.Add(pyramidSeries);

{% endhighlight %}

![Pyramid chart type in Xamarin.Android](charttypes_images/charttypes_img33.png)

### Pyramid Mode

You can render the pyramid series as linear or surface mode. In linear mode, height of the pyramid segment is based on the Y value and in surface mode, area of the pyramid segment is based on the Y values. The default value of [`ChartPyramidMode`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.PyramidSeries.html#Com_Syncfusion_Charts_PyramidSeries_PyramidMode) is [`Linear`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartPyramidMode.html).

{% highlight c# %} 
[C#]

PyramidSeries pyramidSeries = new PyramidSeries()
{
    ItemsSource = Data,
	XBindingPath = "XValue",
	YBindingPath = "YValue",
	PyramidMode = ChartPyramidMode.Surface
};

{% endhighlight %}

![Pyramid mode support in Xamarin.Android Chart](charttypes_images/charttypes_img34.png)

### Gap between the segments

You can control the gap between the two segments using [`GapRatio`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.TriangularSeries.html#Com_Syncfusion_Charts_TriangularSeries_GapRatio) property. Its ranges from 0 to 1.

{% highlight c# %} 
[C#]

PyramidSeries pyramidSeries = new PyramidSeries()
{
    ItemsSource = Data,
	XBindingPath = "XValue",
	YBindingPath = "YValue",
	GapRatio = 0.1f
};

{% endhighlight %}

![Gap between the pyramid segments support in Xamarin.Android Chart](charttypes_images/charttypes_img35.png)

### Exploding a pyramid segment

You can explode a pyramid segment using [`ExplodeIndex`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AccumulationSeries.html#Com_Syncfusion_Charts_AccumulationSeries_ExplodeIndex) property, and [`ExplodeOffset`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.TriangularSeries.html#Com_Syncfusion_Charts_TriangularSeries_ExplodeOffset) property is used to specify the exploded segment’s distance.

{% highlight c# %} 
[C#]

PyramidSeries pyramidSeries = new PyramidSeries()
{
    ItemsSource = Data,
	XBindingPath = "XValue",
	YBindingPath = "YValue",
	ExplodeIndex = 2
};

{% endhighlight %}


Also, the segments can be exploded by touch using [`ExplodableOnTouch`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AccumulationSeries.html#Com_Syncfusion_Charts_AccumulationSeries_ExplodableOnTouch) property of [`PyramidSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.PyramidSeries.html). Default value of this property is false.

![Exploding a pyramid segment support in Xamarin.Android Chart](charttypes_images/charttypes_img36.png)

## Funnel Chart

To render a funnel chart, create an instance of [`FunnelSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FunnelSeries.html) and add to the series collection of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). You can use the following properties to customize the funnel segment appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) – used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) – used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AccumulationSeries.html#Com_Syncfusion_Charts_AccumulationSeries_StrokeColor) – used to change the stroke color of the series.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

FunnelSeries funnelSeries = new FunnelSeries()
{
    ItemsSource = Data,
	XBindingPath = "XValue",
	YBindingPath = "YValue"
};
chart.Series.Add(funnelSeries);

{% endhighlight %}

![Funnel chart type in Xamarin.Android](charttypes_images/charttypes_img37.png)

### Gap between the segments

You can control the gap between the two segments using [`GapRatio`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.TriangularSeries.html#Com_Syncfusion_Charts_TriangularSeries_GapRatio) property. Its ranges from 0 to 1.

{% highlight c# %} 
[C#]

FunnelSeries funnelSeries = new FunnelSeries()
{
    ItemsSource = Data,
	XBindingPath = "XValue",
	YBindingPath = "YValue",
	GapRatio = 0.1f,
};

{% endhighlight %}

![Gap between the funnel segments support in Xamarin.Android Chart](charttypes_images/charttypes_img38.png)

### Exploding a funnel segment

You can explode a pyramid segment using [`ExplodeIndex`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AccumulationSeries.html#Com_Syncfusion_Charts_AccumulationSeries_ExplodeIndex) property and [`ExplodeOffset`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.TriangularSeries.html#Com_Syncfusion_Charts_TriangularSeries_ExplodeOffset) property is used to specify the exploded segment’s distance.

{% highlight c# %} 
[C#]

FunnelSeries funnelSeries = new FunnelSeries()
{
    ItemsSource = Data,
	XBindingPath = "XValue",
	YBindingPath = "YValue",
	ExplodeIndex = 1
};

{% endhighlight %}

Also, the segments can be exploded by touch using [`ExplodableOnTouch`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AccumulationSeries.html#Com_Syncfusion_Charts_AccumulationSeries_ExplodableOnTouch) property of [`FunnelSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FunnelSeries.html). Default value of this property is false.

![Exploding a funnel segment support in Xamarin.Android Chart](charttypes_images/charttypes_img39.png)

### Changing the minimum width of the funnel

You can change the minimum width of the funnel neck using [`MinWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FunnelSeries.html#Com_Syncfusion_Charts_FunnelSeries_MinWidth) property of [`FunnelSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FunnelSeries.html). Default value is `40`.

{% highlight c# %} 

FunnelSeries funnelSeries = new FunnelSeries()
{
    ItemsSource = Data,
	XBindingPath = "XValue",
	YBindingPath = "YValue",
	MinWidth = 160
};

{% endhighlight %}

![Minimum width support for funnel series in Xamarin.Android Chart](charttypes_images/charttypes_img40.png)

## Waterfall Chart

[`WaterfallSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.WaterfallSeries.html) clarifies the cumulative effect of a set of provided positive and negative values. The series is represented by a rectangle and a connector between the rectangles. 

* [`SummaryBindingPath`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.WaterfallSeries.html#Com_Syncfusion_Charts_WaterfallSeries_SummaryBindingPath) – Gets or sets the string value that indicates the sum of previous segments in series.
* [`SummarySegmentColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.WaterfallSeries.html#Com_Syncfusion_Charts_WaterfallSeries_SummarySegmentColor) – Changes the color of summary segment in series.
* [`NegativeSegmentColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.WaterfallSeries.html#Com_Syncfusion_Charts_WaterfallSeries_NegativeSegmentColor) – Changes the color of negative segment in series.
* [`AllowAutoSum`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.WaterfallSeries.html#Com_Syncfusion_Charts_WaterfallSeries_AllowAutoSum) – Enables or disables the segment that has been drawn based on the sum value of previous segments. By default, the value of this property is true. When disabling this property, it renders the segment by using the y-value of provided ItemsSource collection.
* [`ShowConnectorLine`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.WaterfallSeries.html#Com_Syncfusion_Charts_WaterfallSeries_ShowConnectorLine) – Enables or disables the connector line of series. By default, value of this property is true.
* [`ConnectorLineStyle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.WaterfallSeries.html#Com_Syncfusion_Charts_WaterfallSeries_ConnectorLineStyle) – Customizes the appearance of connector line style.

{% highlight c# %}
[C#]

WaterfallSeries waterfallSeries = new WaterfallSeries()
{
	ItemsSource = RevenueDetails,
	XBindingPath = "Category",
	YBindingPath = "Value",
	AllowAutoSum = true,
	SummaryBindingPath = "IsSummary",
	NegativeSegmentColor = Color.Pink,
	SummarySegmentColor = Color.Gray,
	ShowConnectorLine = true
};

chart.Series.Add(waterfallSeries);


{% endhighlight %}

## Box and Whisker Chart

BoxAndWhiskerSeries plots a combination of rectangles and lines to show the distribution of data sets. To render a box and whisker(box plot) chart, create an instance of [`BoxAndWhiskerSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BoxAndWhiskerSeries.html) and add to the series collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). You can use the following properties to customize the appearance.

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Color) - used to change the color of the series.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) - used to change the stroke width of the series.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BoxAndWhiskerSeries.html#Com_Syncfusion_Charts_BoxAndWhiskerSeries_StrokeColor) - used to change the stroke color of the series.
* [`Spacing`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BoxAndWhiskerSeries.html#Com_Syncfusion_Charts_BoxAndWhiskerSeries_Spacing) - used to change the spacing between two segments. The default value of spacing is 0, and the value ranges from 0 to 1. Here, 1 and 0 corresponds to 100% and 0% of the available space, respectively.
* [`Width`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BoxAndWhiskerSeries.html#Com_Syncfusion_Charts_BoxAndWhiskerSeries_Width) - used to change the width of the rectangle. The default value of the width is 0.8, and the value ranges from 0 to 1. Here, 1 and 0 corresponds to 100% and 0% of the available width, respectively.

{% highlight c# %}

[C#]

SfChart chart = new SfChart();
...

BoxAndWhiskerSeries boxPlotSeries = new BoxAndWhiskerSeries() 
{ 
    ItemsSource = Data, 
    XBindingPath = "Department", 
    YBindingPath = "Ages",
    ShowMedian = true
};
chart.Series.Add(boxPlotSeries);

{% endhighlight %}

![BoxAndWhisker chart type in Xamarin.Android Chart](charttypes_images/BoxAndWhisker_Exclusive_Median.png)

### Customize the series box mode

The series box plotting mode can be changed using the [`BoxPlotMode`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BoxAndWhiskerSeries.html#Com_Syncfusion_Charts_BoxAndWhiskerSeries_BoxPlotMode) property of [`BoxAndWhiskerSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BoxAndWhiskerSeries.html). The plotting mode of series can be calculated as follows:

* [`Exclusive`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BoxPlotMode.html) - The quartile values are calculated using the formula (N+1) * P (N count, P percentile), and their index value starts from 1 in the list.
* [`Inclusive`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BoxPlotMode.html) - The quartile values are calculated using the formula (N−1) * P (N count, P percentile), and their index value starts from 0 in the list.
* [`Normal`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BoxPlotMode.html) - The quartile values are calculated by splitting the list and getting the median values.

By default, [`BoxPlotMode`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BoxAndWhiskerSeries.html#Com_Syncfusion_Charts_BoxAndWhiskerSeries_BoxPlotMode) value is [`Exclusive`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BoxPlotMode.html).

The following code shows how to set the [`BoxPlotMode`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BoxAndWhiskerSeries.html#Com_Syncfusion_Charts_BoxAndWhiskerSeries_BoxPlotMode) value as [`Inclusive`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BoxPlotMode.html).

{% highlight c# %}

[C#]

SfChart chart = new SfChart();
...

BoxAndWhiskerSeries boxPlotSeries = new BoxAndWhiskerSeries() 
{ 
    ItemsSource = Data, 
    XBindingPath = "Department", 
    YBindingPath = "Ages",
    ShowMedian = true,
    BoxPlotMode = BoxPlotMode.Inclusive
};
chart.Series.Add(boxPlotSeries);

{% endhighlight %}

![BoxPlotMode support for BoxAndWhiskerSeries in Xamarin.Android Chart](charttypes_images/BoxAndWhisker_Inclusive.png)

### ShowMedian

The Median values of given data set is viewed by enabling the [`ShowMedian`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BoxAndWhiskerSeries.html#Com_Syncfusion_Charts_BoxAndWhiskerSeries_ShowMedian) property of [`BoxAndWhiskerSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BoxAndWhiskerSeries.html). By default, [`ShowMedian`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BoxAndWhiskerSeries.html#Com_Syncfusion_Charts_BoxAndWhiskerSeries_ShowMedian) value is false. The following code demonstrates how to enable the [`ShowMedian`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BoxAndWhiskerSeries.html#Com_Syncfusion_Charts_BoxAndWhiskerSeries_ShowMedian) property.

{% highlight c# %}

[C#]

SfChart chart = new SfChart();
...

BoxAndWhiskerSeries boxPlotSeries = new BoxAndWhiskerSeries()
{
    ItemsSource = Data,
    XBindingPath = "Department",
    YBindingPath = "Ages",
    ShowMedian = true
} 
chart.Series.Add(boxPlotSeries);

{% endhighlight %}

![ShowMedian support for BoxAndWhiskerSeries in Xamarin.Android Chart](charttypes_images/BoxAndWhisker_Exclusive_Median.png)

### Outlier

The outlier is used to display the outlier point that lies either below the lower whisker or above the upper whisker line and it is an observation that is numerically distant from the rest of the data.

#### ShowOutlier

The outlier value in the box plot can be viewed by enabling the [`ShowOutlier`] property of [`BoxAndWhiskerSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BoxAndWhiskerSeries.html). By default, [ShowOutlier] value is true. The following code demonstrates how to disable the [`ShowOutlier`] property.

{% highlight c# %}

[C#]

SfChart chart = new SfChart();
...

BoxAndWhiskerSeries boxPlotSeries = new BoxAndWhiskerSeries()
{
    ItemsSource = Data,
    XBindingPath = "Department",
    YBindingPath = "Ages",
    ShowMedian = true,
    ShowOutlier = false
} 
chart.Series.Add(boxPlotSeries);

{% endhighlight %}

![ShowOutlier support for BoxAndWhiskerSeries in Xamarin.Android Chart](charttypes_images/ShowOutlier.png)

### SymbolType

The [`SymbolType`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BoxAndWhiskerSeries.html#Com_Syncfusion_Charts_BoxAndWhiskerSeries_SymbolType) is used to display the outlier point with different types of symbols. The available symbols are Cross, Diamond, Ellipse, Hexagon, InvertedTriangle, Pentagon, Plus, Rectangle and Triangle. By default, [`SymbolType`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BoxAndWhiskerSeries.html#Com_Syncfusion_Charts_BoxAndWhiskerSeries_SymbolType) value is [`Ellipse`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSymbolType.html).

The following code shows how to set the [`SymbolType`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BoxAndWhiskerSeries.html#Com_Syncfusion_Charts_BoxAndWhiskerSeries_SymbolType) value as [`Cross`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSymbolType.html).

{% highlight c# %}

[C#]

SfChart chart = new SfChart();
...

BoxAndWhiskerSeries boxPlotSeries = new BoxAndWhiskerSeries()
{
    ItemsSource = Data,
    XBindingPath = "Department",
    YBindingPath = "Ages",
    ShowMedian = true,
    SymbolType = ChartSymbolType.Cross
} 
chart.Series.Add(boxPlotSeries);

{% endhighlight %}

![Outlier for BoxAndWhiskerSeries in Xamarin.Android Chart](charttypes_images/BoxAndWhisker_SymbolType.png)

## Error Bar Chart

ErrorBarSeries is graphical representations of the variations of data and used on graphs to indicate the errors or uncertainty in a reported measurement. To render a error bar chart, create an instance of [`ErrorBarSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarSeries.html) and add to the [`Series`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html#Com_Syncfusion_Charts_ChartBase_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html).

{% highlight c# %}
[C#]

SfChart chart = new SfChart();
...

ScatterSeries scatterSeries = new ScatterSeries ()
{ 
	ItemsSource = CarDistributionDetails, 	
	ScatterHeight = 20, 
	ScatterWidth = 20, 
	ShapeType = ChartScatterShapeType.Ellipse,
	XBindingPath = "Country", 
	YBindingPath = "Value" 
};
scatterSeries.ColorModel.Palette = ChartColorPalette.Natural;
chart.Series.Add(scatterSeries);

ErrorBarSeries errorBarSeries = new ErrorBarSeries()
{
	ItemsSource = CarDistributionDetails,
	XBindingPath = "Country",
	YBindingPath = "Value",
        Type = ErrorBarType.Fixed,
	Mode = ErrorBarMode.Both,
	HorizontalErrorValue = 0.5,
	VerticalErrorValue = 4
};
chart.Series.Add(errorBarSeries);

{% endhighlight %}

![ErrorBar chart type in Xamarin.Android](charttypes_images/ErrorBar.png)

### Type

 The [`Type`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarSeries.html#Com_Syncfusion_Charts_ErrorBarSeries_Type) property is used to define the error bar type value in Fixed, Custom, Percentage, StandardDeviation, and StandardErrors. The default value of this property is [`Fixed`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarType.html). For all types, you have to set the values for [`HorizontalErrorValue`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarSeries.html#Com_Syncfusion_Charts_ErrorBarSeries_HorizontalErrorValue) and [`VerticalErrorValue`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarSeries.html#Com_Syncfusion_Charts_ErrorBarSeries_VerticalErrorValue) except [`Custom`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarType.html).

#### Fixed

{% highlight c# %}
[C#]

ErrorBarSeries errorBarSeries = new ErrorBarSeries()
{
	ItemsSource = CarDistributionDetails,
	XBindingPath = "Country",
	YBindingPath = "Value",
        Type = ErrorBarType.Fixed,
	Mode = ErrorBarMode.Both,
	HorizontalErrorValue = 0.5,
	VerticalErrorValue = 4
};
chart.Series.Add(errorBarSeries);

{% endhighlight %}

![Fixed type for ErrorBarSeries in Xamarin.Android Chart](charttypes_images/ErrorBar_Fixed.png)

#### Percentage

{% highlight c# %}
[C#]

ErrorBarSeries errorBarSeries = new ErrorBarSeries()
{
	ItemsSource = CarDistributionDetails,
	XBindingPath = "Country",
	YBindingPath = "Value",
        Type = ErrorBarType.Percentage,
	Mode = ErrorBarMode.Both,
	HorizontalErrorValue = 1,
	VerticalErrorValue = 8
};
chart.Series.Add(errorBarSeries);

{% endhighlight %}

![Percentage type for ErrorBarSeries in Xamarin.Android Chart](charttypes_images/ErrorBar_Percentage.png)

#### Standard Deviation

{% highlight c# %}
[C#]

ErrorBarSeries errorBarSeries = new ErrorBarSeries()
{
	ItemsSource = CarDistributionDetails,
	XBindingPath = "Country",
	YBindingPath = "Value",
        Type = ErrorBarType.StandardDeviation,
	Mode = ErrorBarMode.Both,
	HorizontalErrorValue = 1,
	VerticalErrorValue = 4
};
chart.Series.Add(errorBarSeries);

{% endhighlight %}

![StandardDeviation type for ErrorBarSeries in Xamarin.Android Chart](charttypes_images/ErrorBar_StandardDeviation.png)

#### Standard Errors

{% highlight c# %}
[C#]

ErrorBarSeries errorBarSeries = new ErrorBarSeries()
{
	ItemsSource = CarDistributionDetails,
	XBindingPath = "Country",
	YBindingPath = "Value",
        Type = ErrorBarType.StandardErrors,
	Mode = ErrorBarMode.Both,
	HorizontalErrorValue = 1,
	VerticalErrorValue = 4
};
chart.Series.Add(errorBarSeries);

{% endhighlight %}

![StandardErrors type For ErrorBarSeries in Xamarin.Android Chart](charttypes_images/ErrorBar_StandardErrors.png)

#### Custom

If [`Type`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarSeries.html#Com_Syncfusion_Charts_ErrorBarSeries_Type) is [`Custom`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarType.html), you have to set values for [`HorizontalErrorPath`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarSeries.html#Com_Syncfusion_Charts_ErrorBarSeries_HorizontalErrorPath) and [`VerticalErrorPath`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarSeries.html#Com_Syncfusion_Charts_ErrorBarSeries_VerticalErrorPath) as shown in the following code snippet.

{% highlight c# %}
[C#]

ErrorBarSeries errorBarSeries = new ErrorBarSeries()
{
	ItemsSource = CarDistributionDetails,
	XBindingPath = "Country",
	YBindingPath = "Value",
        Type = ErrorBarType.Custom,
	Mode = ErrorBarMode.Both,
	HorizontalErrorPath = "HorizontalErrorValues",
	VerticalErrorValue = "VerticalErrorValues"
};
chart.Series.Add(errorBarSeries);

{% endhighlight %}

![Custom type for ErrorBarSeries in Xamarin.Android Chart](charttypes_images/ErrorBar_Custom.png)

### Mode

The error value shown on the chart is based on the [`Mode`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarSeries.html#Com_Syncfusion_Charts_ErrorBarSeries_Mode) property. It have the values of [`Both`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarMode.html), [`Horizontal`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarMode.html), and [`Vertical`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarMode.html). The default value of this property is [`Both`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarMode.html). 

#### Both

To display horizontal and vertical error values, you can set the [`Mode`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarSeries.html#Com_Syncfusion_Charts_ErrorBarSeries_Mode) as [`Both`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarMode.html) as shown in the following code.

{% highlight c# %}
[C#]

ErrorBarSeries errorBarSeries = new ErrorBarSeries()
{
	ItemsSource = CarDistributionDetails,
	XBindingPath = "Country",
	YBindingPath = "Value",
        Type = ErrorBarType.Fixed,
	Mode = ErrorBarMode.Horizontal,
	HorizontalErrorValue = 0.5,
	VerticalErrorValue = 4
};
chart.Series.Add(errorBarSeries);

{% endhighlight %}

![ErrorBarMode support for ErrorBarSeries in Xamarin.Android Chart](charttypes_images/ErrorBar_Mode_Both.png)

#### Horizontal

To display horizontal error value only, you can set the [`Mode`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarSeries.html#Com_Syncfusion_Charts_ErrorBarSeries_Mode) as [`Horizontal`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarMode.html) as shown in the following code.

{% highlight c# %}
[C#]

ErrorBarSeries errorBarSeries = new ErrorBarSeries()
{
	ItemsSource = CarDistributionDetails,
	XBindingPath = "Country",
	YBindingPath = "Value",
        Type = ErrorBarType.Fixed,
	Mode = ErrorBarMode.Horizontal,
	HorizontalErrorValue = 0.5,
	VerticalErrorValue = 4
};
chart.Series.Add(errorBarSeries);

{% endhighlight %}

![ErrorBarMode Horizontal support for ErrorBarSeries in Xamarin.Android Chart](charttypes_images/ErrorBar_Mode_Horizontal.png)

#### Vertical

To display vertical error value only, you can set the [`Mode`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarSeries.html#Com_Syncfusion_Charts_ErrorBarSeries_Mode) as [`Vertical`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarMode.html) as shown in the following code.

{% highlight c# %}
[C#]

ErrorBarSeries errorBarSeries = new ErrorBarSeries()
{
	ItemsSource = CarDistributionDetails,
	XBindingPath = "Country",
	YBindingPath = "Value",
        Type = ErrorBarType.Fixed,
	Mode = ErrorBarMode.Vertical,
	HorizontalErrorValue = 0.5,
	VerticalErrorValue = 4
};
chart.Series.Add(errorBarSeries);

{% endhighlight %}

![ErrorBarMode Vertical support for ErrorBarSeries in Xamarin.Android Chart](charttypes_images/ErrorBar_Mode_Vertical.png)

### Direction

The [`HorizontalDirection`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarSeries.html#Com_Syncfusion_Charts_ErrorBarSeries_HorizontalDirection) and [`VerticalDirection`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarSeries.html#Com_Syncfusion_Charts_ErrorBarSeries_VerticalDirection) properties are used to set the direction of error bar lines. The default value is [`Both`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarDirection.html).

* [`Both`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarDirection.html) - used to set error value in positive and negative directions.
* [`Minus`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarDirection.html) - used to set error value in a negative direction.
* [`Plus`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarDirection.html) - used to set error value in a positive direction.	

{% highlight c# %}
[C#]

ErrorBarSeries errorBarSeries = new ErrorBarSeries()
{
	ItemsSource = CarDistributionDetails,
	XBindingPath = "Country",
	YBindingPath = "Value",
        Type = ErrorBarType.Fixed,
	Mode = ErrorBarMode.Both,
	HorizontalDirection = ErrorBarDirection.Both,
        VerticalDirection = ErrorBarDirection.Both,
	HorizontalErrorValue = 0.5,
	VerticalErrorValue = 4
};
chart.Series.Add(errorBarSeries);

{% endhighlight %}

![ErrorBarDirection support for ErrorBarSeries in Xamarin.Android Chart](charttypes_images/ErrorBar_Direction.png)

### Customization

You can customize the [`ErrorBarSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarSeries.html) with the following style properties.

* [`HorizontalLineStyle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarSeries.html#Com_Syncfusion_Charts_ErrorBarSeries_HorizontalLineStyle) – used to customizes the appearance of horizontal error bar line.
* [`VerticalLineStyle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarSeries.html#Com_Syncfusion_Charts_ErrorBarSeries_VerticalLineStyle) – used to customizes the appearance of vertical error bar line.
* [`HorizontalCapLineStyle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarSeries.html#Com_Syncfusion_Charts_ErrorBarSeries_HorizontalCapLineStyle) – used to customizes the appearance of horizontal error bar cap line.
* [`VerticalCapLineStyle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ErrorBarSeries.html#Com_Syncfusion_Charts_ErrorBarSeries_VerticalCapLineStyle) – used to customizes the appearance of vertical error bar cap line.

{% highlight c# %}
[C#]

 errorBarSeries.HorizontalLineStyle = new ErrorBarLineStyle();
 errorBarSeries.HorizontalLineStyle.StrokeColor = Color.Cyan;
 errorBarSeries.HorizontalLineStyle.StrokeWidth = 4;
 
 errorBarSeries.VerticalLineStyle = new ErrorBarLineStyle();
 errorBarSeries.VerticalLineStyle.StrokeColor = Color.Cyan;
 errorBarSeries.VerticalLineStyle.StrokeWidth = 4;
 
 errorBarSeries.HorizontalCapLineStyle = new ErrorBarCapLineStyle();
 errorBarSeries.HorizontalCapLineStyle.StrokeColor = Color.Green;
 errorBarSeries.HorizontalCapLineStyle.StrokeWidth = 4;
 errorBarSeries.HorizontalCapLineStyle.Visibility = Visibility.Visible;
 
 errorBarSeries.VerticalCapLineStyle = new ErrorBarCapLineStyle();
 errorBarSeries.VerticalCapLineStyle.StrokeColor = Color.Green;
 errorBarSeries.VerticalCapLineStyle.StrokeWidth = 4;
 errorBarSeries.VerticalCapLineStyle.Visibility =  Visibility.Visible;

{% endhighlight %}

![Customization of ErrorBarSeries in Xamarin.Android Chart](charttypes_images/ErrorBar_LineStyle.png)

