---
layout: post
title: Performance tips
description: How to improve the performance of Essential Android Chart
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Performance

Following are the key points that can be used to boost the performance of the chart when there is a need to plot high volume data.

* When there are large number of points to load in line series, you can use [`FastLineSeries`](http://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FastLineSeries.html) series instead of [`LineSeries`](http://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.LineSeries.html). To renderer a fast line chart, create an instance of [`FastLineSeries`](http://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FastLineSeries.html) and add to the series using [`Series`](http://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html) property of [`SfChart`](http://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html).

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

FastLineSeries fastLineSeries = new FastLineSeries();
fastLineSeries.ItemsSource = Data;
fastLineSeries.XBindingPath = "XValue";
fastLineSeries.YBindingPath = "YValue;

chart.Series.Add(fastLineSeries);

{% endhighlight %}

N>If you have minimal set of data points, the recommended approach is to use normal line series to visualize those data using line chart. Because the normal line series has provisions to customize the color and shape of individual line.

* Instead of enabling data markers and labels when there are large number of data points, you can use **Trackball** to view the point information.

* The default stroke width of the [`FastLineSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FastLineSeries.html) is 2, reducing this to 1 will improve the performance. Refer the following code snippet to configure the stroke width of FastLineSeries.

{% highlight c# %} 
[C#]

SfChart chart = new SfChart();
...

FastLineSeries fastLineSeries = new FastLineSeries();
fastLineSeries.ItemsSource = Data;
fastLineSeries.XBindingPath = "XValue";
fastLineSeries.YBindingPath = "YValue;
fastLineSeries.StrokeWidth = 1;

chart.Series.Add(fastLineSeries);

{% endhighlight %}

* When the underlying data object implements INotifyPropertyChanged, you need to enable the [`ListenPropertyChange`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_ListenPropertyChange) property of the series, to make the chart listen to the property changes of your data object. However enabling this property registers PropertyChanged event of every object in the data source. Due to this, chart’s loading time is affected when there are a large number of points. By default, ListenPropertyChange is set to false in order to avoid the event registration unnecessarily.

* Whenever there is a new data point is added to the [`ItemsSource`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_ItemsSource) property of [`ChartSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html), the chart will be refreshed with new data point if the [`ItemsSource`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_ItemsSource) property contains `ObservableCollection`. In order to avoid the chart rendering for each update in [`ItemsSource`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_ItemsSource), you can suspend the chart using [`SuspendSeriesNotification`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html#Com_Syncfusion_Charts_ChartBase_SuspendSeriesNotification) method of chart and the  [`ResumeSeriesNotification`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html#Com_Syncfusion_Charts_ChartBase_ResumeSeriesNotification) should be called once the required data points are added to the collection and the chart should be refreshed with data points that have been added between these two method calls.

{% highlight c# %}

Chart.SuspendSeriesNotification();

// ...

// Add the data points to ItemsSource property.

// ...

Chart.ResumeSeriesNotification();

{% endhighlight %}

Similarly, you can use [`SuspendNotification`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_SuspendNotification) and [`ResumeNotification`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_ResumeNotification) methods of [`ChartSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html) to suspend and resume the update of the respective series.

{% highlight c# %}

series.SuspendNotification();

// ...

// Add the data points to ItemsSource property.

// ...

series.ResumeNotification();

{% endhighlight %}

