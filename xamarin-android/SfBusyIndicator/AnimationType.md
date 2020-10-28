---
layout: post
title: AnimationTypes in Syncfusion BusyIndicator control for Xamarin.Android
description: Learn various animation types in SfBusyIndicator
platform: Xamarin.Android
control: SfBusyIndicator
documentation: ug
---

# AnimationType

The `AnimationType` property of SfBusyIndicator allows to set anyone of the animation from the built-in animations as a SfBusyIndicator.

{% tabs %}

{% highlight c# %}

	SfBusyIndicator busyIndicator = new SfBusyIndicator(this);
	busyIndicator.AnimationType=AnimationTypes.Ball;
	
{% endhighlight %}

{% endtabs %}

N> For getting animation types of SfBusyIndicator, need to add the `using Com.Syncfusion.Sfbusyindicator.Enums` namespace.

![](images/Ball.png)
                                          
