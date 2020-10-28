---
layout : post
title : No Result Found Text in Syncfusion SfAutoComplete control for Xamarin.Android
description : Learn how to display the no result found text in SfAutoComplete
platform : Xamarin.Android
control : SfAutoComplete
documentation : ug
---

# No Results Found

When the entered item is not in the suggestion list, SfAutoComplete displays a text indicating there is no search results found. We can set the desire text to be displayed for indicating no results found with the `NoResultsFoundText` property.

{% tabs %}

{% highlight C# %}

countryAutoComplete.NoResultsFoundText="No Results Found";
	 
{% endhighlight %}

{% endtabs %}

![NoResultsFound](images/NoResultsFound.png)

## Customizing NoResultsFoundText

The `NoResultsFoundTextColor`, `NoResultsFoundFontSize` and `NoResultsFoundTypeface` properties are used to customize the foreground color, font size and typeface of NoResultsFoundText.
{% tabs %}

{% highlight c# %}

countryAutoComplete.NoResultsFoundText = "No Results Found";
countryAutoComplete.NoResultsFoundFontSize = 20;
countryAutoComplete.NoResultsFoundTextColor = Android.Graphics.Color.DarkGreen;
countryAutoComplete.NoResultsFoundTypeface = Typeface.CreateFromAsset(this.Assets, "Pacifico.ttf");

{% endhighlight %}

{% endtabs %}

![NoResultsFound_Customization](images/NoResultsFound_Customization.jpg)