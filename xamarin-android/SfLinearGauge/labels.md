---

layout: post
title: Labels in Syncfusion LinearGauge control for Xamarin.Android
description:  This section explains how the color, font and position of the labels in linear gauge scales can be applied and customized.
platform: Xamarin.Android
control: LinearGauge
documentation: ug

---

# Labels in SfLinearGauge 

[`LinearScale`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Gauges.SfLinearGauge.LinearScale.html) labels associate a numeric value with major scale tick marks.

## Label color customization

The label color can be changed using the [`LabelColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Gauges.SfLinearGauge.LinearScale.html#Com_Syncfusion_Gauges_SfLinearGauge_LinearScale_LabelColor) property.

{% highlight c# %}

            SfLinearGauge linearGauge = new SfLinearGauge(this);
            linearGauge.SetBackgroundColor(Color.White);
            linearGauge.SetOrientation(SfLinearGauge.Orientation.Horizontal);
            LinearScale linearScale = new LinearScale();
            linearScale.ScaleBarColor = Color.ParseColor("#e0e0e0");
            linearScale.MajorTickSettings.StrokeWidth = 1;
            linearScale.MinorTickSettings.StrokeWidth = 1;
            linearScale.MajorTickSettings.Length = 20;
            linearScale.MajorTickSettings.Color = Color.Gray;
            linearScale.MinorTickSettings.Color = Color.Gray;
            linearScale.MinorTickSettings.Length = 10;
            linearScale.LabelColor = Color.Purple;
            linearGauge.Scales.Add(linearScale);
    
{% endhighlight %}

![Label color customization image](labels_images/label1.png)

## Label font customization

The label font can be customized by using the [`LabelFontSize`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Gauges.SfLinearGauge.LinearScale.html#Com_Syncfusion_Gauges_SfLinearGauge_LinearScale_LabelFontSize) and [`LabelFontStyle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Gauges.SfLinearGauge.LinearScale.html#Com_Syncfusion_Gauges_SfLinearGauge_LinearScale_LabelFontStyle) properties.

{% highlight c# %}

           SfLinearGauge linearGauge = new SfLinearGauge(this);
            linearGauge.SetBackgroundColor(Color.White);
            linearGauge.SetOrientation(SfLinearGauge.Orientation.Horizontal);
            LinearScale linearScale = new LinearScale();
            linearScale.LabelFontSize = 15;
            linearScale.ScaleBarColor = Color.ParseColor("#e0e0e0");
            linearScale.LabelFontStyle = Typeface.Create("Chiller", TypefaceStyle.Italic);
            linearScale.MajorTickSettings.StrokeWidth = 1;
            linearScale.MinorTickSettings.StrokeWidth = 1;
            linearScale.MajorTickSettings.Length = 20;
            linearScale.MajorTickSettings.Color = Color.Gray;
            linearScale.MinorTickSettings.Color = Color.Gray;
            linearScale.MinorTickSettings.Length = 10;
            linearScale.LabelColor = Color.ParseColor("#424242");
            linearGauge.Scales.Add(linearScale);
    
{% endhighlight %}

![Label-font-customization image](labels_images/label2.png)

## Setting position for labels

The labels can be positioned far away from the ticks by using the [`LabelOffset`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Gauges.SfLinearGauge.LinearScale.html#Com_Syncfusion_Gauges_SfLinearGauge_LinearScale_LabelOffset) property in pixel.

{% highlight c# %}

            SfLinearGauge linearGauge = new SfLinearGauge(this);
            linearGauge.SetBackgroundColor(Color.White);
            linearGauge.SetOrientation(SfLinearGauge.Orientation.Horizontal);
            LinearScale linearScale = new LinearScale();
            linearScale.ScaleBarColor = Color.ParseColor("#e0e0e0");
            linearScale.MajorTickSettings.StrokeWidth = 1;
            linearScale.MinorTickSettings.StrokeWidth = 1;
            linearScale.MajorTickSettings.Length = 20;
            linearScale.MajorTickSettings.Color = Color.Gray;
            linearScale.MinorTickSettings.Color = Color.Gray;
            linearScale.MinorTickSettings.Length = 10;
            linearScale.LabelColor = Color.ParseColor("#424242");
            linearScale.LabelOffset = 5;
            linearGauge.Scales.Add(linearScale);
   
{% endhighlight %}

![Label-offset image](labels_images/label3.png)

### Setting postfix and prefix for labels

You can  postfix/prefix values to the scale labels using the [`LabelPostfix`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Gauges.SfLinearGauge.LinearScale.html#Com_Syncfusion_Gauges_SfLinearGauge_LinearScale_LabelPostfix) and [`LabelPrefix`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Gauges.SfLinearGauge.LinearScale.html#Com_Syncfusion_Gauges_SfLinearGauge_LinearScale_LabelPrefix) properties, respectively.

### Setting label postfix

The [`LabelPostfix`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Gauges.SfLinearGauge.LinearScale.html#Com_Syncfusion_Gauges_SfLinearGauge_LinearScale_LabelPostfix) property allows you to postfix the values to scale labels.

{% highlight c# %}

             SfLinearGauge linearGauge = new SfLinearGauge(this);
            linearGauge.SetBackgroundColor(Color.White);
            linearGauge.SetOrientation(SfLinearGauge.Orientation.Horizontal);
            LinearScale linearScale = new LinearScale();
            linearScale.Minimum = 0;
            linearScale.Maximum = 1000;
            linearScale.Interval = 200;
            linearScale.ScaleBarColor = Color.ParseColor("#e0e0e0");
            linearScale.MajorTickSettings.StrokeWidth = 1;
            linearScale.MinorTickSettings.StrokeWidth = 1;
            linearScale.MajorTickSettings.Length = 20;
            linearScale.MajorTickSettings.Color = Color.Gray;
            linearScale.MinorTickSettings.Color = Color.Gray;
            linearScale.MinorTickSettings.Length = 10;
            linearScale.LabelColor = Color.ParseColor("#424242");
            linearScale.LabelPostfix = "K";
            linearGauge.Scales.Add(linearScale);
    
{% endhighlight %}

![Label-postfix image](labels_images/label4.png)

### Setting label prefix

The [`LabelPrefix`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Gauges.SfLinearGauge.LinearScale.html#Com_Syncfusion_Gauges_SfLinearGauge_LinearScale_LabelPrefix) property allows you to prefix the values to scale labels.

{% highlight c# %}

            SfLinearGauge linearGauge = new SfLinearGauge(this);
            linearGauge.SetBackgroundColor(Color.White);
            linearGauge.SetOrientation(SfLinearGauge.Orientation.Horizontal);
            LinearScale linearScale = new LinearScale();
            linearScale.ScaleBarColor = Color.ParseColor("#e0e0e0");
            linearScale.LabelColor = Color.ParseColor("#424242");
            linearScale.LabelPrefix = "$";
            linearScale.MajorTickSettings.StrokeWidth = 1;
            linearScale.MinorTickSettings.StrokeWidth = 1;
            linearScale.MajorTickSettings.Length = 20;
            linearScale.MajorTickSettings.Color = Color.Gray;
            linearScale.MinorTickSettings.Color = Color.Gray;
            linearScale.MinorTickSettings.Length = 10;
            linearGauge.Scales.Add(linearScale);
    
{% endhighlight %}

![Label-prefix image](labels_images/label5.png)

## Labels visibility

Labels visibility can be customized using the [`ShowLabels`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Gauges.SfLinearGauge.LinearScale.html#Com_Syncfusion_Gauges_SfLinearGauge_LinearScale_ShowLabels) property of linear scale.

{% highlight c# %}

           SfLinearGauge linearGauge = new SfLinearGauge(this);
            linearGauge.SetBackgroundColor(Color.White);
            linearGauge.SetOrientation(SfLinearGauge.Orientation.Horizontal);
            LinearScale linearScale = new LinearScale();
            linearScale.ScaleBarSize = 40;
            linearScale.ScaleBarColor = Color.ParseColor("#e0e0e0");
            linearScale.MajorTickSettings.Color = Color.Black;
            linearScale.MinorTickSettings.Color = Color.Black;
            linearScale.MajorTickSettings.Length = 40;
            linearScale.MinorTickSettings.Offset = -20;
            linearScale.MajorTickSettings.Offset = -40;
            linearScale.MajorTickSettings.StrokeWidth = 1;
            linearScale.MinorTickSettings.StrokeWidth = 1;
            linearScale.MinorTickSettings.Length = 20;
            linearScale.MinorTicksPerInterval = 4;
            linearScale.ShowLabels = false;
            linearGauge.Scales.Add(linearScale);
   
{% endhighlight %}

![Labels visibility image](labels_images/label6.png)


## Customize the scale labels
 
The scale label are customized by using `LabelFormat` and `Culture` properties of linear scale.

`LabelFormat` property is used to change the format of labels by setting a formatting string on the `LabelFormat` property.
`Culture` property is used to format the group separator of the value based on the respective culture.

{% highlight c# %}

            SfLinearGauge linearGauge = new SfLinearGauge(this);
            ObservableCollection<LinearScale> scales = new ObservableCollection<LinearScale>();
            LinearScale linearScale = new LinearScale();
            linearScale.MaximumLabels = 4;
            linearScale.ScaleOffset = 50;
            linearScale.Minimum = 10;
            linearScale.Maximum = 50;
            linearScale.Interval = 10;
            linearScale.ScaleBarColor = Color.LightGray;
            linearScale.MinorTicksPerInterval = 1;
            linearScale.LabelFontSize = 15;
            linearScale.LabelFormat = "{0:c}";
            linearScale.LabelOffset = 10;
            linearScale.ScaleBarSize = 10;
            linearScale.LabelColor = Color.Black;
            BarPointer barPointer = new BarPointer();
            barPointer.Value = 35;
            barPointer.Color = Color.Red;
            barPointer.StrokeWidth = 10;
            linearScale.Pointers.Add(barPointer);
            LinearRange linearRange = new LinearRange();
            linearRange.StartValue = 0;
            linearRange.EndValue = 60;
            linearRange.Color = Color.Blue;
            linearRange.Offset = -25;
            linearRange.StartWidth = 10;
            linearRange.EndWidth = 10;
            linearScale.Ranges.Add(linearRange);
            linearScale.Culture = new System.Globalization.CultureInfo("fr-FR");
            scales.Add(linearScale);
            linearGauge.Scales = scales;
            SetContentView(linearGauge);
   
{% endhighlight %}

![Label format Image](labels_images/labelFormat.png)

