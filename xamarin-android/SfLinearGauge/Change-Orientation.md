---
layout: post
title: Orientation in LinearGauge
description: Learn how to set Orientation in LinearGauge
platform: Xamarin.Android
control: LinearGauge
documentation: ug
---
# Change Orientation

[`SfLinearGauge`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Gauges.SfLinearGauge.SfLinearGauge.html) supports horizontal and vertical orientations. By default, [`SfLinearGauge`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Gauges.SfLinearGauge.SfLinearGauge.html) is rendered with horizontal orientation. You can the change the orientation by using the `Orientation` property. 

{% highlight C# %}

           SfLinearGauge linearGauge = new SfLinearGauge(this);
            linearGauge.SetBackgroundColor(Color.White);
            linearGauge.SetOrientation(SfLinearGauge.Orientation.Vertical);
            LinearScale linearScale = new LinearScale();
            linearScale.Interval = 10;
            linearScale.ScaleBarLength = 350;
            linearScale.ScaleBarColor = Color.ParseColor("#e0e0e0");
            linearScale.LabelColor = Color.ParseColor("#424242");
            linearScale.MajorTickSettings.StrokeWidth = 1;
            linearScale.MinorTickSettings.StrokeWidth = 1;
            linearScale.MajorTickSettings.Length = 20;
            linearScale.MajorTickSettings.Color = Color.Gray;
            linearScale.MinorTickSettings.Color = Color.Gray;
            linearScale.MinorTickSettings.Length = 10;
            linearGauge.Scales.Add(linearScale);


{% endhighlight %}

![](change_orientation/orientaion.png)
