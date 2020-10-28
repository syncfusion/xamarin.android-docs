---
layout: post
title: Various Features in Syncfusion NumericUpDown control for Xamarin.Android
description: Learn how to decide maximum decimal digits to be displayed, nullable value support, autoreverse, setting range and configuring step value in NumericUpDown
platform: Xamarin.Android
control: NumericUpDown
documentation: ug
---
# Auto Reverse

While incrementing, the control will start from Minimum value once it reaches the Maximum value and vice-versa.

N> By default the property value is false.

{% tabs %}

{% highlight C# %}

numericupdown.AutoReverse = true;

{% endhighlight %}

{% endtabs %}

## Continuous Spinning Between Ranges

User can restrict the Values between a specific range by setting `Maximum` and `Minimum` property value.

N> By default the minimum property value is 0 and maximum property value is 100.

{% tabs %}

{% highlight C# %}

sfNumericUpDown.Minimum = 10;
sfNumericUpDown.Maximum = 50

{% endhighlight %}

{% endtabs %}

![](images/maximum.png)

![](images/minimum.png)

## Set Increment

Frequency in which values gets incremented can be decided using `StepValue` property.

N> By default the property value is 1.

{% tabs %}

{% highlight C# %}

	sfNumericUpDown.StepValue = 6;

{% endhighlight %}

{% endtabs %}
