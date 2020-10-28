---
layout: post
title: Appearance and Styling in Syncfusion Rating control for Xamarin.Android
description: Learn how to change the appearance and styling of rating control using ItemSize, ItemSpacing, ItemCount and customization properties.
platform: Xamarin.Android
control: Rating
documentation: ug
---

# Restrict User Selection

SfRating control provides support for changeable or unchangeable values for Rating control. This is achieved by the `ReadOnly` property. When this property is set to True, the Rating value becomes unchangeable. 

N> By default, property value is set to False.

{% tabs %}

{% highlight C# %}

	   rating.ReadOnly= true;

{% endhighlight %}

{% endtabs %}

![](images/readOnly.jpg)

