---
layout: post
title: Adding duplicate axis in Syncfusion SfChart
description: Adding the duplicate axis in SfChart. Duplicate axis can be added using the SfChart Axes Collection property.
platform: Android
control: Chart
documentation: ug
---

# Adding duplicate axis in SfChart

Duplicate axis can be added in the [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html) using the chart [`Axes`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html#Com_Syncfusion_Charts_ChartBase_Axes) collection property. The axis added in the [`Axes`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html#Com_Syncfusion_Charts_ChartBase_Axes) collection will be aligned to the horizontal position by default. The axis position can be changed by using the [`IsVertical`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartAxis.html#Com_Syncfusion_Charts_ChartAxis_IsVertical) bool property of [`ChartAxis`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartAxis.html). When the [`IsVertical`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartAxis.html#Com_Syncfusion_Charts_ChartAxis_IsVertical) property is set true, the axis will be placed vertically and vice versa.

The following code sample demonstrates this.

{% highlight c# %}

SfChart chart = new SfChart();

. . .

chart.Axes.Add(new NumericalAxis()
{
    Minimum = 0,
    Maximum = 70,
    IsVertical = true,
    OpposedPosition = true
});

{% endhighlight  %}

![Duplicate axis support in Xamarin.Android Chart](images/duplicate_axis.png)

N> 
- The [`ChartAxis`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartAxis.html) added in the [`Axes`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html#Com_Syncfusion_Charts_ChartBase_Axes) collection will not be removed until removing it from the [`Axes`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html#Com_Syncfusion_Charts_ChartBase_Axes) collection. 
- The [`Axes`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html#Com_Syncfusion_Charts_ChartBase_Axes) collection does not support the clear method. 
- Same axis cannot be added more than once in [`Axes`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html#Com_Syncfusion_Charts_ChartBase_Axes); only distinct axis will be added to the [`Axes`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html#Com_Syncfusion_Charts_ChartBase_Axes) collection.
