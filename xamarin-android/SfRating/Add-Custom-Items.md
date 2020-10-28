---
layout: post
title: Adding Custom items in Syncfusion Rating control for Xamarin.Android
description: Learn how to add the Custom Items in rating control
platform: Xamarin.Android
control: Rating
documentation: ug
---

# Custom Views

SfRating Items control provides support to add custom views.

## Add SfRating Items

Add the SfRating Items control with a required optimal name by using the included namespace.

{% highlight C# %}

SfRating rating;
SfRatingItem ratingItem;

protected override void OnCreate(Bundle savedInstanceState)
{
    base.OnCreate(savedInstanceState);
    rating = new SfRating(this);
    ratingItem = new SfRatingItem(this);
}

{% endhighlight %}

## Set Selected View
 
The `SelectedView` property is used to apply the given SelectedView to selected rating item.

{% highlight C# %}

    ImageView angrySelected = new ImageView(this);
    angrySelected.SetImageResource(Resource.Drawable.Angry_selected);
    ratingItem.SelectedView = angrySelected;

{% endhighlight %}

## Set UnSelected View
 
The `UnSelectedView` property is used to apply the given UnSelectedView to unselected rating item.

{% highlight C# %}

    ImageView angryUnselected = new ImageView(this);
    angryUnselected.SetImageResource(Resource.Drawable.Angry_Unselected);
    ratingItem.UnSelectedView = angryUnselected;

{% endhighlight %}

## Add Items

The `Items` property is used to hold the collection of SfRatingItem. 

N> SfRatingItem keeps both selected and unselected view respectively.

{% highlight C# %}

    List<SfRatingItem> ratingItemList = new List<SfRatingItem>();
    ratingItemList.Add(ratingItem);
    rating.Items = ratingItemList;

{% endhighlight %}

## Enable Custom Items

When `EnableCustomItems` property is enabled, it will display the custom items added in the rating items. 

{% highlight C# %}

    SfRating rating = new SfRating(this);
    SfRatingItem angry = new SfRatingItem(this);
    ImageView angrySelected = new ImageView(this);
    angrySelected.SetImageResource(Resource.Drawable.Angry_selected);			
    angry.SelectedView = angrySelected;
    ImageView angryUnselected = new ImageView(this);
    angryUnselected.SetImageResource(Resource.Drawable.Angry_Unselected);	
    angry.UnSelectedView = angryUnselected;

    SfRatingItem unhappy = new SfRatingItem(this);
    ImageView unhappySelected = new ImageView(this);
    unhappySelected.SetImageResource(Resource.Drawable.UnHappy_selected);
    unhappy.SelectedView = unhappySelected;
    ImageView unhappyUnselected = new ImageView(this);
    unhappyUnselected.SetImageResource(Resource.Drawable.UnHappy_Unselected);
    unhappy.UnSelectedView = unhappyUnselected;

    SfRatingItem neutral = new SfRatingItem(this);
    ImageView neutralSelected = new ImageView(this);
    neutralSelected.SetImageResource(Resource.Drawable.Neutral_selected);
    neutral.SelectedView = neutralSelected;
    ImageView neutralUnselected = new ImageView(this);
    neutralUnselected.SetImageResource(Resource.Drawable.Neutral_Unselected);
    neutral.UnSelectedView = neutralUnselected;

    SfRatingItem happy = new SfRatingItem(this);
    ImageView happySelected = new ImageView(this);
    happySelected.SetImageResource(Resource.Drawable.Happy_selected);
    happy.SelectedView = happySelected;
    ImageView happyUnselected = new ImageView(this);
    happyUnselected.SetImageResource(Resource.Drawable.Happy_Unselected);
    happy.UnSelectedView = happyUnselected;

    SfRatingItem exited = new SfRatingItem(this);
    ImageView exitedSelected = new ImageView(this);
    exitedSelected.SetImageResource(Resource.Drawable.Excited_selected);
    exited.SelectedView = exitedSelected;
    ImageView exitedUnselected = new ImageView(this);
    exitedUnselected.SetImageResource(Resource.Drawable.Excited_Unselected);
    exited.UnSelectedView = exitedUnselected;

    List<SfRatingItem> ratingItemList = new List<SfRatingItem>();
    ratingItemList.Add(angry);
    ratingItemList.Add(unhappy);
    ratingItemList.Add(neutral);
    ratingItemList.Add(happy);
    ratingItemList.Add(exited);
    rating.Items = ratingItemList;
    rating.EnableCustomView = true;

{% endhighlight %}

![Custom Rating Item](images/CustomviewItems.png)
 