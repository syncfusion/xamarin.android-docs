---
layout : post
title : No Result Found Text in Syncfusion SfComboBox control for Xamarin.Android
description : Learn how to display the no result found text in SfComboBox
platform : Xamarin.Android
control : SfComboBox
documentation : ug
---

# No Results Found

When the entered item is not in the suggestion list, SfComboBox displays a text indicating there is no search results found. We can set the desire text to be displayed for indicating no results found with the `NoResultsFoundText` property.

{% tabs %}

{% highlight C# %}

comboBox.NoResultsFoundText="No Results Found";
	 
{% endhighlight %}

{% endtabs %}

![NoResultsFound](images/NoResultsFound.jpg)

## Customizing NoResultsFoundText

The `NoResultsFoundTextColor`, `NoResultsFoundFontSize` and `NoResultsFoundTypeface` properties are used to customize the foreground color, font size and typeface of NoResultsFoundText.
{% tabs %}

{% highlight c# %}

comboBox.NoResultsFoundText = "No Results Found";
comboBox.NoResultsFoundFontSize = 20;
comboBox.NoResultsFoundTextColor = Android.Graphics.Color.DarkGreen;
comboBox.NoResultsFoundTypeface = Typeface.CreateFromAsset(this.Assets, "Pacifico.ttf");

{% endhighlight %}

{% endtabs %}

![NoResultsFound_Customization](images/NoResultsFound_Customization.jpg)