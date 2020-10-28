---
layout: post
title: Select the Range of SfDateTimeRangeNavigator
description: Selecting Range
platform: Xamarin.Android
control: SfDateTimeRangeNavigator
documentation: ug
---

# Selecting Range

The left and right thumb of `SfDateTimeRangeNavigator` are used to indicate the selected range in the large collection of data. Following are the ways you can select a range.

* By dragging the thumbs.
* By tapping on the minor and major labels.
* By setting the [`ViewRangeStart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator.html#Com_Syncfusion_Rangenavigator_SfDateTimeRangeNavigator_ViewRangeStart) and [`ViewRangeEnd`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator.html#Com_Syncfusion_Rangenavigator_SfDateTimeRangeNavigator_ViewRangeEnd) properties.

Following code example shows how to configure the selected range using `ViewRangeStart` and `ViewRangeEnd` properties of `SfDateTimeRangeNavigator`.

{% highlight c# %}
SfDateTimeRangeNavigator sfRangeNavigator = new SfDateTimeRangeNavigator(); 

sfRangeNavigator.ViewRangeStart = new GregorianCalendar(2015, 4, 1).Time;

sfRangeNavigator.ViewRangeEnd = new GregorianCalendar(2016, 9, 1).Time;

{% endhighlight %}

![Range selection in Xamarin.Android DateTimeRangeNavigator](range_images/range_img1.png)

## Overlay Color

The [`OverlayColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator.html#Com_Syncfusion_Rangenavigator_SfDateTimeRangeNavigator_OverlayColor) property of [`SfDateTimeRangeNavigator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator.html) is used to customize the color of unselected area in date-time range navigator.

## Deferred Update

[`RangeChanged`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator.html) event will be fired whenever you drag the thumbs. If you are doing some long running tasks in this event handler, then dragging the thumbs will not be smooth. You can delay this event by enabling [`DeferredUpdateEnabled`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator.html#Com_Syncfusion_Rangenavigator_SfDateTimeRangeNavigator_DeferredUpdateEnabled) property. If this property is set to true, the `RangeChanged` event will get fired only when you stop dragging or if the thumb is held for more than 500 milliseconds. If it is false, the range will be updated for every movement of the thumb. However, It is true by default.

The delay of update is 500 milliseconds by default. However, it can be changed using [`DeferredUpdateDelay`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator.html#Com_Syncfusion_Rangenavigator_SfDateTimeRangeNavigator_DeferredUpdateDelay) property of [`SfDateTimeRangeNavigator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator.html). 

{% highlight c# %}
SfDateTimeRangeNavigator sfRangeNavigator = new SfDateTimeRangeNavigator(); 

sfRangeNavigator.DeferredUpdateEnabled = false;
sfRangeNavigator.DeferredUpdateDelay = 600;

{% endhighlight %}


## RangeChanged Event

[`RangeChanged`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator.html) event is triggered when the selected range of the [`SfDateTimeRangeNavigator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator.html) is changed. The argument contains the following information.

* [`ViewRangeStart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator.RangeChangedEventArgs.html#Com_Syncfusion_Rangenavigator_SfDateTimeRangeNavigator_RangeChangedEventArgs_ViewRangeStart) – used to get the start date of the selected range.
* [`ViewRangeEnd`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Rangenavigator.SfDateTimeRangeNavigator.RangeChangedEventArgs.html#Com_Syncfusion_Rangenavigator_SfDateTimeRangeNavigator_RangeChangedEventArgs_ViewRangeEnd) – used to get the end date of the selected range.
