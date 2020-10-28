---
layout: post
title: Getting Started with syncfusion rangeslider control for Xamarin.Android 
description:  A quick tour to initial users on Syncfusion rangeSlider control for Xamarin.Android platform
platform: Xamarin.Android 
control: RangeSlider
documentation: ug
---

# Getting Started

This section explains you the steps to configure a SfRangeSlider control in a real-time scenario and also provides a walk-through on some of the customization features available in SfRangeSlider control.

## Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

Add the following assembly references to the Android project,

android\Syncfusion.SfRangeSlider.Android.dll

## Add SfRangeSlider

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight c# %}

	using Com.Syncfusion.RangeSlider; 

{% endhighlight %}

{% endtabs %}

* Now instantiate and add the SfRangeSlider control with a required optimal name.

{% tabs %}

{% highlight c# %}		

	SfRangeSlider rangeSlider = new SfRangeSlider(this);
	SetContentView(rangeSlider);

{% endhighlight %}

{% endtabs %}



## Restricting Values

SfRangeSlider provides option to restrict slider range between minimum and maximum values. Following code explains how to set the range using `Minimum` and `Maximum` properties in the SfRangeSlider.

{% tabs %}

{% highlight c# %}

	rangeSlider.Minimum=0; 
	rangeSlider.Maximum=24; 
	rangeSlider.DirectionReversed=false; 

{% endhighlight %}

{% endtabs %}

## Set Range

SfRangeSlider provides option to set single thumb and double thumb. While setting the double thumb, each thumb value can be set using `RangeStart` and `RangeEnd` properties.

N> The `ShowRange` property is used to switch between a single thumb and double thumb. The `Orientation` property sets the type of orientation.


{% tabs %}

{% highlight c# %}

	rangeSlider.Minimum=0; 
	rangeSlider.Maximum=24; 
	rangeSlider.DirectionReversed=false; 
	rangeSlider.RangeEnd=20; 
	rangeSlider.RangeStart=4;
	rangeSlider.ShowRange=true; 
	rangeSlider.Orientation=Orientation.Horizontal;

{% endhighlight %}

{% endtabs %}

## Ticks and Labels Customization

The ticks can be set by setting the `TickFrequency` and `TickPlacement`. Likewise, value labels can be set by setting the `ShowValueLabel` property to true. The position of label can be varied by the `LabelPlacement` property.

{% tabs %}

{% highlight c# %}

	rangeSlider.TickFrequency=4; 
	rangeSlider.ShowValueLabel=true; 
	rangeSlider.ValuePlacement=ValuePlacement.TopLeft; 
	rangeSlider.TickPlacement=TickPlacement.BottomRight;

{% endhighlight %}

{% endtabs %}

N> The TickFrequency determines the interval between the ticks.

## Adding Snapping Mode

The movement of the thumb can be varied in different ways. This is achieved by setting the SnapsTo property.

{% tabs %}

{% highlight c# %}

rangeSlider.SnapsTo=SnapsTo.Ticks; 
rangeSlider.StepFrequency=6;

{% endhighlight %}

{% endtabs %}

![](images/RangeSlider.png)