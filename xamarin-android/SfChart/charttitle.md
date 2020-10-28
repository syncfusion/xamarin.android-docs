---
layout: post
title: Xamarin.Android | Chart Title | Syncfusion
description: This section explains how to add the chart title and customize the appearance of the chart title in Xamarin.Android Chart
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Title in Xamarin.Android Chart (SfChart)

You can define and customize the Chart title using [`Title`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html#Com_Syncfusion_Charts_ChartBase_Title) property of [`SfChart`](http://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html). The [`Text`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartTitle.html) property of [`ChartTitle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartTitle.html) is used to set the text for the title. 

Following properties are used to customize its appearance.

* [`Text`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartTitle.html) – used to set the chart title.
* [`TextColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartTitle.html) – used to change the color of the title.
* [`TextSize`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartTitle.html) – used to change the text size.
* [`Typeface`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartTitle.html) – used to change the font family and font weight.
* [`Alpha`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartTitle.html) - used to set the alpha value of title. It's range from 0.0 to 1.0
* [`SetBackgroundColor(Color)`]() – used to change the title background color.
* [`SetPadding(Left, Top, Right, Bottom)`]() - used to change the padding value for title.

{% highlight c# %}
[C#]

SfChart sfChart = new SfChart(this);

sfChart.Title.Text = "Efficiency of oil-fired power production";

sfChart.Title.SetTextColor( Color.Blue);

{% endhighlight %}

![Title for Xamarin.Android Chart](charttitle_images/charttitle_img1.png)

## Text Alignment

You can align the title text content to the Start, [`Center`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.TextAlignment.html) or End of the title using the [`TextAlignment`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartTitle.html) property of the [`ChartTitle`](http://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartTitle.html).

{% highlight c# %}
[C#]

SfChart sfChart = new SfChart(this);

sfChart.Title.Text = "Efficiency of oil-fired power production";

sfChart.Title.TextAlignment = TextAlignment.TextStart;

sfChart.Title.SetTextColor( Color.Blue);

{% endhighlight %}

![Text alignment support for title in Xamarin.Android Chart](charttitle_images/charttitle_img2.png)

## Text Wrap

By using the [`LineBreakMode`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartTitle.html#Com_Syncfusion_Charts_ChartTitle_LineBreakMode) property, You can wrap the chart title text content. The default value of this property is `NoWrap`.

{% highlight c# %}
[C#]

SfChart sfChart = new SfChart(this);

sfChart.Title.Text = "Percentage change in efficiency of oil-fired power production in Russia for six months;

sfChart.Title.SetTextColor( Color.Blue);

sfChart.Title.LineBreakMode = LineBreakMode.TailTruncation;

{% endhighlight %}

![Text wrap support for title in Xamarin.Android Chart](charttitle_images/charttitle_img3.png)