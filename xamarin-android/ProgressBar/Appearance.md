---
layout: post
title: Appearance
platform: xamarin
control: ProgressBar
documentation: ug
---
# Appearance

## Angle

The appearance of the circular progress bar can be customized to semi-circle, arc, etc. The start and end angles can be customized using the [`StartAngle`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.ProgressBar.SfCircularProgressBar.html#Syncfusion_Android_ProgressBar_SfCircularProgressBar_StartAngle) and [`EndAngle`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.ProgressBar.SfCircularProgressBar.html#Syncfusion_Android_ProgressBar_SfCircularProgressBar_EndAngle) properties. 

The following code example explains how to change the appearance of the circular progress bar to semi-circle.

{% highlight c# %}

SfCircularProgressBar circularProgressBar = new SfCircularProgressBar(this);

circularProgressBar.Progress = 75;

circularProgressBar.StartAngle = 180;

circularProgressBar.EndAngle = 360;

{% endhighlight %} 

![](overview_images/angle.png)


## Range colors

You can also visualize multiple ranges with different colors that are mapped to each range to enhance readability of progress.Currently, it is applicable only for linear progress bar.

The colors can be mapped to the specific ranges using the [`RangeColors`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.ProgressBar.SfLinearProgressBar.html) property in the linear progress bar, which holds a collection of [`RangeColor`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.ProgressBar.RangeColor.html). 

The following properties in [`RangeColor`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.ProgressBar.RangeColor.html) are used to map the colors to range:

* [`Color`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.ProgressBar.RangeColor.html#Syncfusion_Android_ProgressBar_RangeColor_Color): Represents the color to the specified range.
* [`Start`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.ProgressBar.RangeColor.html#Syncfusion_Android_ProgressBar_RangeColor_Start): Represents the start range of the color.
* [`End`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.ProgressBar.RangeColor.html#Syncfusion_Android_ProgressBar_RangeColor_End): Represents the end range of the color.
* [`IsGradient`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.ProgressBar.RangeColor.html#Syncfusion_Android_ProgressBar_RangeColor_IsGradient): Represents whether the gradient effect is applied to the color.

The following code example shows mapping the solid color range in the linear progress bar.

{% highlight c# %}

SfLinearProgressBar linearProgressBar = new SfLinearProgressBar(this);

linearProgressBar.Progress = 100;

linearProgressBar.RangeColors.Add(new RangeColor() { Color = Android.Graphics.Color.ParseColor("#00bdaf"), Start = 0, End = 25 });

linearProgressBar.RangeColors.Add(new RangeColor() { Color = Android.Graphics.Color.ParseColor("#2f7ecc"), Start = 25, End = 50 });

linearProgressBar.RangeColors.Add(new RangeColor() { Color = Android.Graphics.Color.ParseColor("#e9648e"), Start = 50, End = 75 });

linearProgressBar.RangeColors.Add(new RangeColor() { Color = Android.Graphics.Color.ParseColor ("#fbb78a"), Start = 75, End = 100 });

{% endhighlight %} 

![](overview_images/rangecolors.png)

The following code example shows how to apply gradient transition effect to the range colors in the linear progress bar.

{% highlight c# %}

SfLinearProgressBar linearProgressBar = new SfLinearProgressBar(this);

linearProgressBar.Progress = 100;

linearProgressBar.RangeColors.Add(

new RangeColor() { Color = Android.Graphics.Color.ParseColor("#88A0D9EF"), IsGradient = true, Start = 0 , End = 25 });

linearProgressBar.RangeColors.Add(

new RangeColor() { Color = Android.Graphics.Color.ParseColor("#AA62C1E5"), IsGradient = true, Start = 25, End = 50 });

linearProgressBar.RangeColors.Add(

new RangeColor() { Color = Android.Graphics.Color.ParseColor("#DD20A7DB"), IsGradient = true, Start = 50, End = 75 });

linearProgressBar.RangeColors.Add(

new RangeColor() { Color = Android.Graphics.Color.ParseColor("#FF1C96C5"), IsGradient = true, Start = 75, End = 100 });

{% endhighlight %} 

![](overview_images/gradient.png)

## Thickness

**Linear** **progress** **bar**

In the linear progress bar, the height of the track and padding of the progress indicator can be customized using the [`TrackHeight`]() and [`Padding`]() properties, respectively.

{% highlight c# %}

SfLinearProgressBar linearProgressBar = new SfLinearProgressBar(this);

linearProgressBar.Progress = 100;

linearProgressBar.TrackHeight = 10;

linearProgressBar.Padding = 2;

{% endhighlight %}

![](overview_images/thickness_linear.png)


**Circular** **progress** **bar**

The following properties are used to customize the appearance of the circular progress bar:

* [`IndicatorOuterRadius`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.ProgressBar.SfCircularProgressBar.html#Syncfusion_Android_ProgressBar_SfCircularProgressBar_IndicatorInnerRadius): Defines the outer radius of the progress indicator.
* [`IndicatorInnerRadius`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.ProgressBar.SfCircularProgressBar.html#Syncfusion_Android_ProgressBar_SfCircularProgressBar_IndicatorOuterRadius): Defines the inner radius of the progress indicator.
* [`TrackOuterRadius`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.ProgressBar.SfCircularProgressBar.html#Syncfusion_Android_ProgressBar_SfCircularProgressBar_TrackOuterRadius): Defines the outer radius of the track indicator.
* [`TrackInnerRadius`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.ProgressBar.SfCircularProgressBar.html#Syncfusion_Android_ProgressBar_SfCircularProgressBar_TrackOuterRadius): Defines the inner radius of the track indicator.

The following code example shows how to customize the appearance of circular progress bar.

{% highlight c# %}

SfCircularProgressBar trackOutsideProgressBar = new SfCircularProgressBar(this);

trackOutsideProgressBar.Progress = 75;

trackOutsideProgressBar.IndicatorOuterRadius = 0.7;

trackOutsideProgressBar.IndicatorInnerRadius = 0.65;

trackOutsideProgressBar.ShowProgressValue = false;

{% endhighlight %} 

![](overview_images/appearance.png)


## Corner radius

The [`CornerRadius`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.ProgressBar.SfLinearProgressBar.html#Syncfusion_Android_ProgressBar_SfLinearProgressBar_CornerRadius) property is used to customize the rounded edges in the linear progress bar, as shown in the following code example.

{% highlight c# %}

SfLinearProgressBar linearProgressBar = new SfLinearProgressBar(this);

linearProgressBar.Progress = 50;

linearProgressBar.CornerRadius = 10;

{% endhighlight %} 

![](overview_images/cornerradius.png)


## Color customization

The following properties are used to customize the color in the progress bar:

* [`ProgressColor`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.ProgressBar.SfLinearProgressBar.html#Syncfusion_Android_ProgressBar_SfLinearProgressBar_CornerRadius): Represents the color of the progress indicator.
* [`TrackColor`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.ProgressBar.ProgressBarBase.html#Syncfusion_Android_ProgressBar_ProgressBarBase_TrackColor): Represents the color of the track indicator.

The following code example shows the color customization in progress and track indicator.

{% highlight c# %}

SfLinearProgressBar linearProgressBar = new SfLinearProgressBar(this);

linearProgressBar.Progress = 75;

linearProgressBar.ProgressColor = Android.Graphics.Color.ParseColor("#FF51483a");

linearProgressBar.TrackColor = Android.Graphics.Color.ParseColor("#3351483a");

{% endhighlight %} 

![](overview_images/color1.png)


The linear progress bar provides support to customize the color for the secondary progress bar using the [`SecondaryProgressColor`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.ProgressBar.SfLinearProgressBar.html#Syncfusion_Android_ProgressBar_SfLinearProgressBar_SecondaryProgressColor) property, as shown in the following code example.

{% highlight c# %}
SfLinearProgressBar linearProgressBar = new SfLinearProgressBar(this);

linearProgressBar.Progress = 25;

linearProgressBar.SecondaryProgress = 75;

linearProgressBar.SecondaryProgressColor = Android.Graphics.Color.CornflowerBlue;

{% endhighlight %} 

![](overview_images/color2.png)


