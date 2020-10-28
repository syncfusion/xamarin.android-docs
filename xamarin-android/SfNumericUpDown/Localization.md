---
layout: post
title: Localization in Syncfusion NumericUpDown control for Xamarin.Android
description: Learn how to localize the NumericUpDown control
platform: Xamarin.Android
control: NumericUpDown
documentation: ug
---
# Localization

The SfNumericUpDown value can be localized to any specific culture. It can be specified by setting the `Culture` property with `System.Globalization.CultureInfo` object instance.

N> Default `Culture` property value is en-US.

{% tabs %}

{% highlight C# %}

	numeric.Culture = new System.Globalization.CultureInfo("en-US");
	
{% endhighlight %}

{% endtabs %}

![](images/Culture.png)




