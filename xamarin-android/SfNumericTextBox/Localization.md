---
layout: post
title: Localization in Syncfusion NumericTextBox control for Xamarin.Android
description: Learn how to localize the  NumericTextBox
platform: Xamarin.Android
control: NumericTextBox
documentation: ug
---
# Localization

The SfNumericTextBox value can be localized to any specific culture. It can be specified by setting the `Culture` property with `System.Globalization.CultureInfo` object instance.

N> Default `Culture` property value is en-US.

{% tabs %}

{% highlight c# %}

	numericTextBox.Culture = new System.Globalization.CultureInfo("fr-FR");
	
{% endhighlight %}

{% endtabs %}


![](images/Culture.png)

