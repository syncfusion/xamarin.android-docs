---
layout: post
title: Various Features in Syncfusion NumericUpDown control for Xamarin.Android
description: Learn how to decide maximum decimal digits to be displayed, nullable value support, autoreverse, setting range and configuring step value in NumericUpDown
platform: Xamarin.Android
control: NumericUpDown
documentation: ug
---
# Assign Nullable Value

The null values can be set in SfNumericUpDown `Value` property, by setting `AllowNull` property value to true.

N> By default, the property value is false.

{% tabs %}

{% highlight C# %}

	numericupdown.AllowNull=true;

{% endhighlight %}

{% endtabs %}

![](images/allownull.png)

## Set Hint Text

The `WaterMark` property can be used to provide a hint that helps the user to get started with their input. The watermark text is visible when value is empty or null.

{% tabs %}

{% highlight C# %}

	numericupdown.Watermark = "Numeric Text";
	
{% endhighlight %}

{% endtabs %}

![](images/watermark.png)