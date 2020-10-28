---
layout: post
title: Getting Started for Essential Xamarin.Android Chart | Syncfusion
description: A quick tour to create a chart with title, series, legend, data labels, tooltip, and multiple Y axis in Xamarin.Android Chart.
platform: Xamarin.Android
control: SfChart
documentation: ug
---

# Getting Started of Xamarin.Android Chart(SfChart)

This section explains you the steps required to populate the Chart with data, title, add data labels and tooltips to the Chart. This section covers only the minimal features that you need to know to get started with the Chart.

## Adding Chart Reference

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, 

{Syncfusion Installed location}\Essential Studio\15.3.0.26\lib

N> Assemblies are available in unzipped package location in Mac.

Add the following assembly references to the Android project,

android\Syncfusion.SfChart.Android.dll

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to this [`link`](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Initialize Chart

You can add [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html) to the Xamarin.Android designer from toolbox and customize some basic properties from the property window.

![SfChart Designer support in Xamarin.Android](Getting-Started_images/designer.gif)

You can get the chart instance from axml page in MainActivity using the following code.

{% highlight C# %}

SfChart chart = FindViewById<SfChart>(Resource.Id.sfChart1);

{% endhighlight %}

You can create chart using code behind also. The following steps help to add chart using code behind.

Import the [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html) namespace as shown below in your respective Page,

{% highlight C# %}

using Com.Syncfusion.Charts;

{% endhighlight %}

Then initialize an empty chart with [`PrimaryAxis`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html#Com_Syncfusion_Charts_ChartBase_PrimaryAxis) and [`SecondaryAxis`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html#Com_Syncfusion_Charts_ChartBase_SecondaryAxis) as shown below,

{% highlight C# %} 

SfChart chart = new SfChart (this);

//Initializing Primary Axis
CategoryAxis primaryAxis = new CategoryAxis ();

chart.PrimaryAxis = primaryAxis;

//Initializing Secondary Axis
NumericalAxis secondaryAxis = new NumericalAxis ();

chart.SecondaryAxis = secondaryAxis;

SetContentView(chart);

{% endhighlight %}

Run the project and check if you get following output to make sure you have configured your project properly to add [`SfChart`.](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html)

![SfChart Axis support in Xamarin.Android](Getting-Started_images/Chart-Axis-Image.png)

## Populate Chart with data

To visualize the comparison of person heights in chart data, create an instance of [`ColumnSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ColumnSeries.html), add it to the [`Series`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html#Com_Syncfusion_Charts_ChartBase_Series) collection property of [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html), and then set the actual `Data` collection to the [`ItemsSource`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_ItemsSource) property of [`ChartSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html) as demonstrated in the following code snippet.

N> You need to get the `Name` and `Height` values in `Data` collection to the [`ColumnSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ColumnSeries.html) by setting [`XBindingPath`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_XBindingPath) and [`YBindingPath`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.XyDataSeries.html#Com_Syncfusion_Charts_XyDataSeries_YBindingPath) with the respective field names to plot the series. 

{% highlight C# %}
//Initializing primary axis
CategoryAxis primaryAxis = new CategoryAxis();

primaryAxis.Title.Text = "Name";

chart.PrimaryAxis = primaryAxis;

//Initializing secondary Axis
NumericalAxis secondaryAxis = new NumericalAxis();

secondaryAxis.Title.Text = "Height (in cm)";

chart.SecondaryAxis = secondaryAxis;

ObservableCollection<ChartData> Data = new ObservableCollection<ChartData>()
{
    new ChartData { Name = "David", Height = 180 },
    new ChartData { Name = "Michael", Height = 170 },
    new ChartData { Name = "Steve", Height = 160 },
    new ChartData { Name = "Joel", Height = 182 }
};

//Initializing column series
ColumnSeries series = new ColumnSeries();

series.ItemsSource = Data;

series.XBindingPath = "Name";

series.YBindingPath = "Height";

chart.Series.Add(series);
{% endhighlight %}

{% highlight C# %}
public class ChartData   
{   
    public string Name { get; set; }

    public double Height { get; set; }
}
{% endhighlight %} 

## Add Title

You can add title to chart to provide quick information to the user about the data being plotted in the chart. You can set title using [`SfChart.Title`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html#Com_Syncfusion_Charts_ChartBase_Title) property as shown below.

{% highlight C# %}
 
chart.Title.Text = "Chart";

{% endhighlight %}

Refer this [link](https://help.syncfusion.com/xamarin-android/sfchart/charttitle) to learn more about the options available in [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html) to customize chart title.

## Enable data labels

You can add data labels to improve the readability of the chart. This can be achieved using [`ChartSeries.DataMarker.ShowLabel`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartDataMarker.html#Com_Syncfusion_Charts_ChartDataMarker_ShowLabel) property as shown below.

{% highlight C# %} 

series.DataMarker.ShowLabel = true;

{% endhighlight %}

Refer this [link](https://help.syncfusion.com/xamarin-android/sfchart/datamarker) to learn more about the options available in [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html) to customize data markers.

## Enable legend

You can enable legend using [`SfChart.Legend`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html#Com_Syncfusion_Charts_SfChart_Legend) property as shown below,

{% highlight C# %} 

chart.Legend.Visibility = Visibility.Visible; 

{% endhighlight %}

Additionally, you need to set label for each series using [`ChartSeries.Label`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Label) property, which will be displayed in corresponding legend.

{% highlight C# %} 

series.Label = "Heights";

{% endhighlight %}

Refer this [link](https://help.syncfusion.com/xamarin-android/sfchart/legend) to learn more about the options available in [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html) to customize legend.

## Enable tooltip

Tooltips are used to show information about the segment, when you tap on the segment. You can enable tooltip by setting [`ChartSeries.TooltipEnabled `](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_TooltipEnabled) property to true.

{% highlight C# %} 

series.TooltipEnabled = true;

{% endhighlight %}

Refer this [link](https://help.syncfusion.com/xamarin-android/sfchart/tooltip) to learn more about the options available in [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html) to customize tooltip.

The following code example gives you the complete code of above configurations.

{% highlight C# %} 

using Com.Syncfusion.Charts;

namespace Chart_GettingStarted
{
    [Activity( MainLauncher = true, Icon = "@drawable/icon")]
    public class MainActivity : Activity
    {
        protected override void OnCreate(Bundle bundle)
        {
            base.OnCreate(bundle);

            SfChart chart = new SfChart(this);
            chart.Title.Text = "Chart";
            chart.SetBackgroundColor(Color.White);
	
            //Initializing primary axis
            CategoryAxis primaryAxis = new CategoryAxis();
            primaryAxis.Title.Text = "Name";
            chart.PrimaryAxis = primaryAxis;

            //Initializing secondary Axis
            NumericalAxis secondaryAxis = new NumericalAxis();
            secondaryAxis.Title.Text = "Height (in cm)";
            chart.SecondaryAxis = secondaryAxis;
            
            ObservableCollection<ChartData> data = new ObservableCollection<ChartData>()
            {
                new ChartData { Name = "David", Height = 180 },
                new ChartData { Name = "Michael", Height = 170 },
                new ChartData { Name = "Steve", Height = 160 },
                new ChartData { Name = "Joel", Height = 182 }
            };

            //Initializing column series
            ColumnSeries series = new ColumnSeries();
            series.ItemsSource = data;
            series.XBindingPath = "Name";
            series.YBindingPath = "Height";
          
            series.DataMarker.ShowLabel = true;
            series.Label = "Heights";
            series.TooltipEnabled = true;

            chart.Series.Add(series);
            chart.Legend.Visibility = Visibility.Visible;    
            SetContentView(chart);
        }
    }
}

{% endhighlight %}

The following chart is created as a result of the above codes.

![Chart output in Xamarin.Android Chart](Getting-Started_images/ChartSample-Output.png)

You can find the complete getting started sample from this [link.](https://github.com/SyncfusionExamples/Chart-GettingStarted-in-Xamarin-Android)

## See also

[How to export chart as an image in Xamarin.Android](https://www.syncfusion.com/kb/11930/how-to-export-the-charts-in-xamarin-android)