---
layout: post
title: IsBusy support in Syncfusion BusyIndicator control for Xamarin.Android
description: Learn how to enable and disable animation in BusyIndicator
platform: Xamarin.Android
control: SfBusyIndicator
documentation: ug
---

# Make Busy Animation Idle

SfBusyIndicator control provides support to determine whether an animation needs to be executed or not. Setting the `IsBusy` property to false will stop the animation and removes the control from view.

{% tabs %}

{% highlight c# %}

	SfBusyIndicator busyIndicator = new SfBusyIndicator(this);
	busyIndicator.AnimationType=AnimationTypes.SingleCircle;
	busyIndicator.IsBusy=true;

{% endhighlight %}

{% endtabs %}

![](images/IsBusy_img1.png)                                                                                                   

BusyIndicator
{:.caption}


