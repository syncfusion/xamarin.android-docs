---

layout: post
title: Range selection in Syncfusion SfRating for Xamarin.Andorid
description: Perform range selection with custom views in rating control
platform: Xamarin.Android
control: Rating
documentation: ug

---

# View Range Selection

When using CustomView in SfRating, Only one item will be rated. If you need to change the view of all rated CustomView items, Use the `EnableViewRangeSelection` boolean property.

N> The EnableViewRangeSelection property is used only for CustomViews. 

{% tabs %}

{% highlight C# %}

SfRating rating;

protected override void OnCreate(Bundle savedInstanceState)
{
    base.OnCreate(savedInstanceState);

    --------

    rating.EnableCustomView = true;
    rating.EnableViewRangeSelection = true;

    --------

}

{% endhighlight %}

{% endtabs %}

![SfRating EnableViewRangeSelection](images/enableviewrangeselection.png)
