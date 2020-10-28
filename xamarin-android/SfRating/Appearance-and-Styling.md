---
layout: post
title: Appearance-Styling in Syncfusion Rating control for Xamarin.Android
description: Learn how to change the appearance and styling of rating control using ItemSize, ItemSpacing, ItemCount and customization properties.
platform: Xamarin.Android
control: Rating
documentation: ug
---

# Appearance and Styling

When the default view is not needed, you can customize the view of Xamarin.Forms SfRating control. The SfRating control provides support to customize the size, item count, and space between rating items.

## Set size

The `ItemSize` property sets the size for the rating items. 

N> The default value of this property is 50.

{% tabs %}

{% highlight C# %}

	   rating.ItemSize=20;

{% endhighlight %}

{% endtabs %}

![ Rating Item Size](images/layoutSize.jpg)
 
## Set space between items

The `ItemSpacing` property sets spacing between the rating items.

N> The default value of this property is 5.

{% tabs %}

{% highlight C# %}

	   rating.ItemSpacing=20;

{% endhighlight %}

{% endtabs %}

![Space between Rating Items](images/layoutSpace.jpg)
 
## Set number of items

The `ItemCount` property sets the number of rating items to be displayed.

N> The default value of this property is 5.

 {% tabs %}

{% highlight C# %}

	   rating.ItemCount = 4;

{% endhighlight %}

{% endtabs %}

![Rating item customization](images/fourStar.jpg)

## Rating Settings

For styling customization, Set the `RatingSettings` property value with `SfRatingSettings` object instance.

{% tabs %}

{% highlight c# %}

SfRatingSettings ratingSettings = new SfRatingSettings();
ratingSettings.RatedFill = Color.Gray;

{% endhighlight %}

{% endtabs %}

After adding `RatingSettings` add the RatingSettings instance to `SfRating` instance.

{% tabs %}

{% highlight c# %}

rating.RatingSettings = ratingSettings;

{% endhighlight %}

{% endtabs %}