---
layout: post
title: Markers and data labels in Xamarin.Android Syncfusion Chart
description: This section explains how to add markers and data point labels to a Xamarin.Android Syncfusion Chart series and explains how to customize the labels
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Data Markers in Xamarin.Android Chart(SfChart)

Data markers are used to provide information about the data points to the user. You can add a shape and label to adorn each data point. [`DataMarker`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_DataMarker) can be enabled using following code snippet,

{% highlight c# %} 
[C#]

lineSeries.DataMarker.ShowLabel = true;

{% endhighlight %}

![Data markers support in Xamarin.Android Chart](datamarker_images/datamarker_img1.png)

## Customizing Labels

The [`DataMarkerLabel`](https://help.syncfusion.com/cr/xamarin-android/) appearance can be customized using [`LabelStyle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataMarker.html#Com_Syncfusion_Charts_ChartDataMarker_LabelStyle) property.

* [`TextColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLabelStyle.html#Com_Syncfusion_Charts_ChartLabelStyle_TextColor) – used to change the color of the label.
* [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLabelStyle.html#Com_Syncfusion_Charts_ChartLabelStyle_BackgroundColor) – used to change the label background color.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLabelStyle.html#Com_Syncfusion_Charts_ChartLabelStyle_StrokeColor) – used to change the border color.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLabelStyle.html#Com_Syncfusion_Charts_ChartLabelStyle_StrokeWidth) – used to change the width of the border.
* [`TextSize`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLabelStyle.html#Com_Syncfusion_Charts_ChartLabelStyle_TextSize) – used to change the text size.
* [`Typeface`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLabelStyle.html#Com_Syncfusion_Charts_ChartLabelStyle_Typeface) – used to change the font family and font weight.
* [`MarginTop`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLabelStyle.html#Com_Syncfusion_Charts_ChartLabelStyle_MarginTop) - used to change the top margin of the labels.
* [`MarginBottom`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLabelStyle.html#Com_Syncfusion_Charts_ChartLabelStyle_MarginBottom) - used to change the bottom margin of the labels.
* [`MarginLeft`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLabelStyle.html#Com_Syncfusion_Charts_ChartLabelStyle_MarginLeft) - used to change the left margin of the labels.
* [`MarginRight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLabelStyle.html#Com_Syncfusion_Charts_ChartLabelStyle_MarginRight) - used to change the right margin of the labels.
* [`Angle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataMarkerLabelStyle.html#Com_Syncfusion_Charts_ChartDataMarkerLabelStyle_Angle) – used to rotate the labels.
* [`LabelPadding`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataMarkerLabelStyle.html#Com_Syncfusion_Charts_ChartDataMarkerLabelStyle_LabelPadding) - used to change the padding value of label.
* [`OffsetX`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataMarkerLabelStyle.html#Com_Syncfusion_Charts_ChartDataMarkerLabelStyle_OffsetX) - used to set the offset value of X.
* [`OffsetY`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataMarkerLabelStyle.html#Com_Syncfusion_Charts_ChartDataMarkerLabelStyle_OffsetY) - used to set the offset value of Y.
* [`UseSeriesPalette`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataMarker.html#Com_Syncfusion_Charts_ChartDataMarker_UseSeriesPalette) - used to bind the series color to the background color of data marker labels.

Following code snippet illustrates the customization of label and its background,

{% highlight c# %} 
[C#]

lineSeries.DataMarker.ShowLabel = true;
lineSeries.DataMarker.LabelStyle.TextColor = Color.Blue;
lineSeries.DataMarker.LabelStyle.BackgroundColor = Color.Cyan;
lineSeries.DataMarker.LabelStyle.StrokeColor = Color.Red;
lineSeries.DataMarker.LabelStyle.StrokeWidth = 2;
lineSeries.DataMarker.LabelStyle.TextSize = 18;
lineSeries.DataMarker.LabelStyle.Typeface = Typeface.DefaultFromStyle(TypefaceStyle.Italic);
lineSeries.DataMarker.LabelStyle.Angle = 315;
lineSeries.DataMarker.LabelStyle.MarginLeft = 5;
lineSeries.DataMarker.LabelStyle.MarginTop = 5;
lineSeries.DataMarker.LabelStyle.MarginRight = 5;
lineSeries.DataMarker.LabelStyle.MarginBottom = 5;

{% endhighlight %}

![Customizing the labels of data markers in Xamarin.Android Chart](datamarker_images/datamarker_img2.png)

## Formatting Label Content

You can customize the content of the label using [`LabelContent`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataMarker.html#Com_Syncfusion_Charts_ChartDataMarker_LabelContent) property. Following are the two options that are supported now,

* [`Percentage`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.LabelContent.html) – This will show the percentage value of corresponding data point Y value, this is often used in pie, doughnut, funnel and pyramid series types.
* [`YValue`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.LabelContent.html) – This will show the corresponding Y value.

{% highlight c# %} 
[C#]

pieSeries.DataMarker.LabelContent = LabelContent.Percentage;

{% endhighlight %}

![Formatting the label content of data markers in Xamarin.Android Chart](datamarker_images/datamarker_img3.png)

## Label Position

The [`LabelPosition`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataMarkerLabelStyle.html#Com_Syncfusion_Charts_ChartDataMarkerLabelStyle_LabelPosition) property is used to position the data marker labels at the [`Center`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DataMarkerLabelPosition.html), [`Inner`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DataMarkerLabelPosition.html) and [`Outer`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DataMarkerLabelPosition.html) positions.

The following screenshot illustrates the default position of data marker labels,

![Positioning the data marker labels support in Xamarin.Android Chart](datamarker_images/datamarker_img4.png)


The following code sample illustrates the center position of data marker labels,

{% highlight c# %} 
[C#]

columnSeries.DataMarker.LabelStyle.LabelPosition = DataMarkerLabelPosition.Center;

{% endhighlight %}

![Positioning the data marker labels support in Xamarin.Android Chart](datamarker_images/datamarker_img5.png)

The following code sample illustrates the Inner position of data marker labels,

{% highlight c# %} 
[C#]

columnSeries.DataMarker.LabelStyle.LabelPosition = DataMarkerLabelPosition.Inner;

{% endhighlight %}

![Positioning the data marker labels support in Xamarin.Android Chart](datamarker_images/datamarker_img6.png)


The following code sample illustrates the outer position of data marker labels, 

{% highlight c# %} 
[C#]

columnSeries.DataMarker.LabelStyle.LabelPosition = DataMarkerLabelPosition.Outer;

{% endhighlight %}

![Positioning the data marker labels support in Xamarin.Android Chart](datamarker_images/datamarker_img7.png)

## Smart Labels

In Pie and Doughnut series, overlapping of data labels can be avoided by setting [`SmartLabelsEnabled`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CircularSeries.html#Com_Syncfusion_Charts_CircularSeries_SmartLabelsEnabled) property to true.

{% highlight c# %}
[C#]

SfChart chart = new SfChart();

PieSeries pieSeries = new PieSeries()
{

    DataSource = Data,
    StartAngle = 45,
    EndAngle = 405,
    SmartLabelsEnabled = true,
    ConnectorType = ConnectorType.Bezier,
    DataMarkerPosition = CircularSeriesDataMarkerPosition.OutsideExtended,

};

pieSeries.DataMarker.ShowLabel = true;

chart.Series.Add(pieSeries);

{% endhighlight %}

![Smart labels support for data markers in Xamarin.Android Chart](datamarker_images/datamarker_img10.png)

## Customizing Marker Shapes

Shapes can be added to chart data marker by setting the [`ShowMarker`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataMarker.html#Com_Syncfusion_Charts_ChartDataMarker_ShowMarker) property to true. There are different shapes you can set to the chart using [`MarkerType`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataMarker.html#Com_Syncfusion_Charts_ChartDataMarker_MarkerType) property such as [`Cross`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DataMarkerType.html), [`Ellipse`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DataMarkerType.html), [`Diamond`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DataMarkerType.html) etc. Following properties are used to customize marker appearance,

* [`MarkerWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataMarker.html#Com_Syncfusion_Charts_ChartDataMarker_MarkerWidth) - used to change the width of the marker.
* [`MarkerHeight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataMarker.html#Com_Syncfusion_Charts_ChartDataMarker_MarkerHeight) - used to change the height of the marker.
* [`MarkerColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataMarker.html#Com_Syncfusion_Charts_ChartDataMarker_MarkerColor) - used to change the color of the marker.
* [`MarkerStrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataMarker.html#Com_Syncfusion_Charts_ChartDataMarker_MarkerStrokeColor) - used to change the border color of the shape.
* [`MarkerStrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataMarker.html#Com_Syncfusion_Charts_ChartDataMarker_MarkerStrokeWidth) – used to change the marker border width.

The following code example shows how to enable marker and specify its types,

{% highlight c# %} 
[C#]

lineSeries.DataMarker.ShowLabel = false;
lineSeries.DataMarker.ShowMarker = true;
lineSeries.DataMarker.MarkerType = DataMarkerType.Hexagon;
lineSeries.DataMarker.MarkerWidth = 20;
lineSeries.DataMarker.MarkerHeight = 20;
lineSeries.DataMarker.MarkerColor = Color.Cyan;
lineSeries.DataMarker.MarkerStrokeColor = Color.Red;
lineSeries.DataMarker.MarkerStrokeWidth = 2;

{% endhighlight %}

![Data markers shape customization support in Xamarin.Android Chart](datamarker_images/datamarker_img8.png)


## Connector Line

This feature is used to connect label and data point using a line. It can be enabled for any chart types but this is often used with Pie and Doughnut chart types. The [`ConnectorLineStyle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataMarker.html#Com_Syncfusion_Charts_ChartDataMarker_ConnectorLineStyle) property is used to customize the connector line.


* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLineStyle.html#Com_Syncfusion_Charts_ChartLineStyle_StrokeColor) – used to change the color of the line.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLineStyle.html#Com_Syncfusion_Charts_ChartLineStyle_StrokeWidth) – used to change the stroke thickness of the line.
* [`PathEffect`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartLineStyle.html#Com_Syncfusion_Charts_ChartLineStyle_PathEffect) – used to set the dashes for the line.
* [`ConnectorHeight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ConnectorLineStyle.html#Com_Syncfusion_Charts_ConnectorLineStyle_ConnectorHeight) – used to change the connector line height.
* [`ConnectorRotationAngle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ConnectorLineStyle.html#Com_Syncfusion_Charts_ConnectorLineStyle_ConnectorRotationAngle) – used to change the connector line rotation angle.

The following code illustrates how to specify the connector height and its angle,

{% highlight c# %} 
[C#]

lineSeries.DataMarker.ShowLabel = true;
lineSeries.DataMarker.ConnectorLineStyle.ConnectorHeight = 50;
lineSeries.DataMarker.ConnectorLineStyle.ConnectorRotationAngle = 175;
lineSeries.DataMarker.ConnectorLineStyle.StrokeColor = Color.Blue;
lineSeries.DataMarker.ConnectorLineStyle.StrokeWidth = 3;
lineSeries.DataMarker.ConnectorLineStyle.PathEffect = new DashPathEffect(new float[] { 3, 3 }, 3);

{% endhighlight %}

![Connector line support for data markers in Xamarin.Android Chart](datamarker_images/datamarker_img9.png)

N> For Pie and Doughnut series, you can set the [`Bezier`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ConnectorType.html) curve for connector line using [`ConnectorType`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.CircularSeries.html#Com_Syncfusion_Charts_CircularSeries_ConnectorType) property of Pie and Doughnut series.

## Event

### DataMarkerLabelCreated

The [`DataMarkerLabelCreated`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html) event occurs when the data marker label is created. This argument contains object of the [`DataMarkerLabel`](https://help.syncfusion.com/cr/xamarin-android/). The following properties are available in [`DataMarkerLabel`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DataMarkerLabel.html) to customize the appearance of data markers based on condition.

* [`Label`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DataMarkerLabel.html#Com_Syncfusion_Charts_DataMarkerLabel_Label) – Gets or sets the text of data marker.
* [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DataMarkerLabel.html#Com_Syncfusion_Charts_DataMarkerLabel_BackgroundColor) – Gets or sets the background color of data marker label.
* [`Index`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DataMarkerLabel.html#Com_Syncfusion_Charts_DataMarkerLabel_Index) – Gets the data point index of data marker label.
* [`XPosition`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DataMarkerLabel.html#Com_Syncfusion_Charts_DataMarkerLabel_XPosition) – Gets the x-position of data marker label.
* [`YPosition`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DataMarkerLabel.html#Com_Syncfusion_Charts_DataMarkerLabel_YPosition) – Gets the y-position of data marker label.
* [`LabelStyle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DataMarkerLabel.html#Com_Syncfusion_Charts_DataMarkerLabel_LabelStyle) – Gets or sets the label style to customize the appearance of individual data marker label.
* [`MarkerWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DataMarkerLabel.html#Com_Syncfusion_Charts_DataMarkerLabel_MarkerWidth) – Gets or sets the marker width.
* [`MarkerHeight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DataMarkerLabel.html#Com_Syncfusion_Charts_DataMarkerLabel_MarkerHeight) – Gets or sets the marker height.
* [`MarkerBorderWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DataMarkerLabel.html#Com_Syncfusion_Charts_DataMarkerLabel_MarkerBorderWidth) – Gets or sets the border width of marker symbol.
* [`MarkerBorderColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DataMarkerLabel.html#Com_Syncfusion_Charts_DataMarkerLabel_MarkerBorderColor) – Gets or sets the border color of marker symbol.
* [`MarkerColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DataMarkerLabel.html#Com_Syncfusion_Charts_DataMarkerLabel_MarkerColor) – Gets or sets the marker color.
* [`MarkerType`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DataMarkerLabel.html#Com_Syncfusion_Charts_DataMarkerLabel_MarkerType) – Gets or sets the shape type of marker. The available shapes are [`Ellipse`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DataMarkerType.html), diamond, hexagon, cross, HorizontalLine, VerticalLine, InvertedTriangle, triangle, pentagon, plus, and square.
* [`View`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.DataMarkerLabel.html#Com_Syncfusion_Charts_DataMarkerLabel_View) Gets or sets the view.

## See also

[How to customize the data marker of charts in Xamarin.Android](https://www.syncfusion.com/kb/11926/how-to-customize-the-data-marker-of-charts-in-xamarin-android)