---
layout: post
title: Customization in Syncfusion Rating control for Xamarin.Android
description: Learn how to change the appearance and styling of rating control using ItemSize, ItemSpacing, ItemCount and customization properties.
platform: Xamarin.Android
control: Rating
documentation: ug
---

# Customizing appearance

You can customize the color, stroke width, and stroke color of rated and unrated items using the following properties of `SfRatingSettings`:

* `RatedFill`
* `UnRatedFill`
* `RatedStroke`
* `UnRatedStroke`
* `RatedStrokeWidth`
* `UnRatedStrokeWidth`

## Rating settings

For customizing styles, set the value of `RatingSettings` property with `SfRatingsSettings` object instance.

{% tabs %}

{% highlight C# %}

SfRating rating;
SfRatingSettings ratingSettings;
protected override void OnCreate(Bundle savedInstanceState)
{
    base.OnCreate(savedInstanceState);
    rating = new SfRating(this);
    ratingSettings = new SfRatingSettings();
    rating.RatingSettings = ratingSettings;
}

{% endhighlight %}

{% endtabs %}

## Set fill color

The SfRating control supports to set the fill color for the selected and unselected items.

### Selected items

The `RatedFill` property fills the rated area with the specified solid color in the SfRating control.

{% tabs %}

{% highlight C# %}

	ratingSettings.RatedFill = Color.Red;

{% endhighlight %}

{% endtabs %}

![Rated Items](images/ratedFill.jpg)

### Unselected items

The `UnRatedFill` property fills the unrated area with the specified solid color in the SfRating control.

{% tabs %}

{% highlight C# %}

	ratingSettings.UnRatedFill = Color.Gray;

{% endhighlight %}

{% endtabs %}

![Unrated Items](images/unRatedFill.jpg)

## Set stroke color

The SfRating control supports to set the stroke color for the selected and unselected items.

### Selected items

The RatedStroke property sets the stroke for the rated area with the specified solid color for the selected items in the SfRating control.

{% tabs %}

{% highlight C# %}

    ratingSettings.RatedStroke = Color.DarkGreen;

{% endhighlight %}

{% endtabs %}

![Rated Item Stroke Color](images/ratedStroke.png)

### Unselected items

The `UnRatedStroke` property sets the stroke for the unrated area with the specified solid color in the SfRating control.

{% tabs %}

{% highlight C# %}

	ratingSettings.UnRatedStroke = Color.Black;

{% endhighlight %}

{% endtabs %}

![Unrated Item Stroke Color](images/unRatedStroke.jpg)
 
## Set stroke width

The SfRating control supports to set the stroke width for the selected and unselected items.

### Selected items

The `RatedStrokeWidth` property sets the stroke width for the rated area with the specified value in the SfRating control.

{% tabs %}

{% highlight C# %}

	ratingSettings.RatedStrokeWidth = 3;

{% endhighlight %}

{% endtabs %}

![Rated Item Stroke Width](images/ratedStrokeWidth.jpg)

### Unselected items

The `UnRatedStrokeWidth` property sets the stroke width for the unrated area with the specified value in the SfRating control.

{% tabs %}

{% highlight C# %}

	ratingSettings.UnRatedStrokeWidth = 3;

{% endhighlight %}

{% endtabs %}

![Unrated Item Stroke Width](images/unRatedStrokeWidth.jpg)
