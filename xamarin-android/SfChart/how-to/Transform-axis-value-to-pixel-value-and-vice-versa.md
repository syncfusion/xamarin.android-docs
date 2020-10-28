---
layout: post
title: Transform axis value to pixel value and vice-versa | Syncfusion
description: Transform axis value to pixel value and vice-versa in SfChart
platform: Android
control: Chart
documentation: ug
---

# Transform axis value to pixel value and vice-versa

[`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html) offers two utility methods to transform the pixel to chart point and vice-versa.

* [`ValueToPoint(ChartAxis axis, double value)`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html#Com_Syncfusion_Charts_ChartBase_ValueToPoint_Com_Syncfusion_Charts_ChartAxis_System_Double_) - Converts the data point value to screen point.
* [`PointToValue(ChartAxis axis, PointF point)`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html#Com_Syncfusion_Charts_SfChart_PointToValue_Com_Syncfusion_Charts_ChartAxis_Android_Graphics_PointF_) - Converts the screen point to chart value.

{% highlight c# %}

double xValue = Chart.PointToValue(Chart.PrimaryAxis, screenPoint);

double yValue = Chart.PointToValue(Chart.SecondaryAxis, screenPoint);

double chartPointX = Chart.ValueToPoint(Chart.PrimaryAxis, xValue);

double chartPointY = Chart.ValueToPoint(Chart.SecondaryAxis, yValue);

{% endhighlight  %}

Use the [`ValueToPoint`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartAxis.html#Com_Syncfusion_Charts_ChartAxis_ValueToPoint_System_Double_) and [`PointToValue`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartAxis.html#Com_Syncfusion_Charts_ChartAxis_PointToValue_Android_Graphics_PointF_) methods, which are available in [`ChartAxis`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartAxis.html), to convert the screen point within the rendered area of the series.

N> You can convert the actual axis value to 0 to 1 coefficient using the [`ValueToCoefficient(double value)`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartAxis.html#Com_Syncfusion_Charts_ChartAxis_ValueToCoefficient_System_Double_) and [`CoefficientToValue(double value)`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartAxis.html#Com_Syncfusion_Charts_ChartAxis_CoefficientToValue_System_Double_) methods of [`ChartAxis`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartAxis.html).
