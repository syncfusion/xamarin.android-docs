---
layout: post
title: Sizing support in Syncfusion BusyIndicator control for Xamarin.Android
description: Learn how to customize the size of the animation type
platform: Xamarin.Android
control: SfBusyIndicator
documentation: ug
---

# Sizing

Drawing size can be customized in SfBusyIndicator. `ViewBoxHeight` and `ViewBoxWidth` properties can be used to set height and width of the SfBusyIndicator.

{% tabs %}

{% highlight c# %}

SfBusyIndicator sfBusyIndicator = new SfBusyIndicator(this);
busyIndicator.AnimationType=AnimationTypes.SlicedCircle;
busyIndicator.ViewBoxWidth=200;
busyIndicator.ViewBoxHeight=200;
	
{% endhighlight %}

{% endtabs %}

![](images/Sizing_img1.png)                                                                              

ViewBox height and width
{:.caption}
