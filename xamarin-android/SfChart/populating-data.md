---
layout: post
title: Populating data | Syncfusion
description: How to add data point to series in  Essential Xamarin.Android Chart.
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Populating Data

[`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html) control can be configured with data points using [`ItemsSource`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_ItemsSource) property of [`ChartSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html). You can assign a collection of custom objects to the [`ItemsSource`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_ItemsSource) property. In this case, you need to set the [`XBindingPath`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_XBindingPath) and [`YBindingPath`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.XyDataSeries.html#Com_Syncfusion_Charts_XyDataSeries_YBindingPath) properties of chart series with the property names of the custom object which contains the x-value/category and y-value respectively.

N> While using custom objects, [`XBindingPath`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_XBindingPath) property is required for all types of chart series. You need to set [`YBindingPath`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.XyDataSeries.html#Com_Syncfusion_Charts_XyDataSeries_YBindingPath) property only for the [`XYDataSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.XyDataSeries.html) types which needs single y-value for a data point. For example, Line, Spline, Column, Bar, Pie etc.  For [`BubbleSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BubbleSeries.html) type, you need to set both [`YBindingPath`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.XyDataSeries.html#Com_Syncfusion_Charts_XyDataSeries_YBindingPath) and [`Size`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BubbleSeries.html#Com_Syncfusion_Charts_BubbleSeries_Size) properties since it requires two y-values to plot a single bubble data point. In the case of financial series types like Candle and HiLoOpenClose, which requires four y-values for a single data point, you need to set [`High`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FinancialSeriesBase.html#Com_Syncfusion_Charts_FinancialSeriesBase_High), [`Low`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FinancialSeriesBase.html#Com_Syncfusion_Charts_FinancialSeriesBase_Low), [`Open`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FinancialSeriesBase.html#Com_Syncfusion_Charts_FinancialSeriesBase_Open) and [`Close`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FinancialSeriesBase.html#Com_Syncfusion_Charts_FinancialSeriesBase_Close) properties with the property names of a custom object which contains respective values.

Following code snippet illustrates this,

{% highlight c# %}
[C#]

public class ChartData

{

	public ChartData(string demand, double year2010, double year2011)
	{

		this.Demand = demand;

		this.Year2010 = year2010;

		this.Year2011 = year2011;

	}

	public string Demand { get; set; }

	public double Year2010 { get; set; }

	public double Year2011 { get; set; }

}

{% endhighlight %}

{% highlight c# %}
[C#]

ObservableCollection<ChartData> demands = new ObservableCollection<ChartData>(); 
demands.Add(new ChartData("Jan", 42, 27));
demands.Add(new ChartData("Feb", 44, 28));
demands.Add(new ChartData("Mar", 53, 35));
demands.Add(new ChartData("Apr", 64, 44));
demands.Add(new ChartData("May", 75, 54));

chart.Series.Add (new ColumnSeries () {
	
	ItemsSource = demands,

	XBindingPath = "Demand",

	YBindingPath = "Year2010"

});

{% endhighlight %}
