---
layout : post
title : Interaction in Syncfusion Carousel Control in Xamarin.Android.
description : Learn how to perform an operation while changing the carouselItem or Collection in Carousel for Xamarin.Android.
platform : Xamarin.Android
control : Carousel
documentation : ug
---

# How to perform an operation while changing the carouselItem?

We can perform operation while changing the carouselItem using `SelectionChanged` event. SelectionChanged event returns the index changed SfCarouselItem.

{% highlight C# %}

carousel.SelectionChanged += (object sender, SfCarousel.SelectionChangedEventArgs e) =>
{
   
};

{% endhighlight %}

# How to perform an operation while changing the collection of carousel?

We can perform operation while changing the collection of carousel using `ItemsCollectionChanged` event. ItemsCollectionChanged event returns changed collection of SfCarouselItem

{% highlight C# %}

carousel.ItemsCollectionChanged += (object sender SfCarousel.ItemsCollectionChangedEventArgs e) =>
    {
    
    };

{% endhighlight %}

