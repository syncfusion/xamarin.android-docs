---
layout: post
title: Precision Mode in Syncfusion Rating control for Xamarin.Android
description: Learn how to change the precision mode of rating control
platform: Xamarin.Android
control: Rating
documentation: ug
---

# Precision Mode

The precision mode defines the accuracy level of the SfRating control. It has Standard, Half and Exact options.

## Standard

The rating item will be filled completely based on the rating value.

{% tabs %}

{% highlight C# %}

	   rating.Precision=Precision.Standard;

{% endhighlight %}

{% endtabs %}

![](images/standard.jpg)

## Half

The rating item will be filled partially based on the rating value.

{% tabs %}

{% highlight C# %}

	   rating.Precision=Precision.Half;

{% endhighlight %}

{% endtabs %}

![](images/half.jpg) 

## Exact

The rating item will be filled exactly based on the rating value.

{% tabs %}

{% highlight C# %}

	   rating.Precision=Precision.Exact;

{% endhighlight %}

{% endtabs %}

![](images/exact.jpg) 



