---
layout: post
title: Precision Mode in Xamarin.Android Rating control | Syncfusion
description: Learn how to change the precision mode of Syncfusion Essential Xamarin.Android Rating control, and more.
platform: Xamarin.Android
control: Rating
documentation: ug
---

# Precision Mode in Xamarin.Android Rating control

The precision mode defines the accuracy level of the SfRating control. It has Standard, Half and Exact options.

## Standard

The rating item will be filled completely based on the rating value.

{% tabs %}

{% highlight C# %}

	   rating.Precision=Precision.Standard;

{% endhighlight %}

{% endtabs %}

![Standard_Images1](images/standard.jpg)

## Half

The rating item will be filled partially based on the rating value.

{% tabs %}

{% highlight C# %}

	   rating.Precision=Precision.Half;

{% endhighlight %}

{% endtabs %}

![Half_Images2](images/half.jpg) 

## Exact

The rating item will be filled exactly based on the rating value.

{% tabs %}

{% highlight C# %}

	   rating.Precision=Precision.Exact;

{% endhighlight %}

{% endtabs %}

![Exact_Images3](images/exact.jpg) 



