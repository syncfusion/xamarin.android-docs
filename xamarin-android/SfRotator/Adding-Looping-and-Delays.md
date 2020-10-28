---
layout: post
title: Various features in Syncfusion Rotator control for Xamarin.Android 
description: Learn how to set the autoplay option, loop the items, enable Text Area  and choose the navigation direction in Rotator control for Xamarin.Android 
platform: Xamarin.Android 
control: Rotator
documentation: ug
---

# Adding Looping and Delays

Looping and delay can be enabled in SfRotator control and also we can customize the Text and Navigation direction.

## Toggle AutoPlay

The `EnableAutoPlay` property specifies whether the items should navigate automatically based on `NavigationDelay` property, when the property value is set to true.

N> By default, the property value is set to false.

{% highlight C# %}

SfRotator rotator = new SfRotator(this);
rotator.EnableAutoPlay = true;

{% endhighlight %}

## Setting Navigation Delay

The `NavigationDelay` property specifies the delay duration while switching to next navigation item, when `EnableAutoPlay` property is enabled.

N> The property value should be in milliseconds.

{% highlight C# %}

SfRotator rotator = new SfRotator(this);
rotator.NavigationDelay = 3000;

{% endhighlight %}

## Looping Items

The `EnableLooping` property specifies whether the items should navigate to first item once it reaches the last item and vice-versa.

N> Default value of `EnableLooping` in Rotator is true.

{% highlight C# %}

SfRotator rotator = new SfRotator(this);
rotator.EnableLooping = false;

{% endhighlight %}

## Restrict the Swiping

Using `EnableSwiping` property , we can restrict the swiping gesture on Rotator's Item. By enabling the EnableSwiping property , we can't move the Rotator's Item by swipe gesture.

N> By default , this property is set to true. 

{% highlight C# %}

SfRotator rotator = new SfRotator(this);
rotator.EnableSwiping = false;

{% endhighlight %}


