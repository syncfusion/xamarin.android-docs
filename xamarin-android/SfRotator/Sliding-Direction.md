---
layout: post
title: Various features in Syncfusion Rotator control for Xamarin.Android 
description: Learn how to set the autoplay option, loop the items, enable Text Area  and choose the navigation direction in Rotator control for Xamarin.Android 
platform: Xamarin.Android 
control: Rotator
documentation: ug
---

# Sliding Direction

The `NavigationDirection` property specifies the direction in which items should be navigated in SfRotator control.

## Horizontal

Items can be navigated in horizontal direction.

{% highlight C# %}

SfRotator rotator = new SfRotator(this);
rotator.NavigationDirection = NavigationDirection.Horizontal;

{% endhighlight %}

## Vertical

Items can be navigated in vertical direction.

{% highlight C# %}

SfRotator rotator = new SfRotator(this);
rotator.NavigationDirection = NavigationDirection.Vertical;

{% endhighlight %}

## LeftToRight

Items can be navigated from Left to Right Only.

{% highlight C# %}

SfRotator rotator = new SfRotator(this);
rotator.NavigationDirection = NavigationDirection.LeftToRight;

{% endhighlight %}

## RightToLeft

Items can be navigated from Right to Left Only.

{% highlight C# %}

SfRotator rotator = new SfRotator(this);
rotator.NavigationDirection = NavigationDirection.RightToLeft;

{% endhighlight %}

## TopToBottom

Items can be navigated from Top to Bottom Only.

{% highlight C# %}

SfRotator rotator = new SfRotator(this);
rotator.NavigationDirection = NavigationDirection.TopToBottom;

{% endhighlight %}

## BottomToTop

Items can be navigated from Bottom to Top Only.

{% highlight C# %}

SfRotator rotator = new SfRotator(this);
rotator.NavigationDirection = NavigationDirection.BottomToTop;

{% endhighlight %}