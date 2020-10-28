---
layout : post
title : Setting the duration for animation in Syncfusion Carousel control in Xamarin.Android
description : Learn how to set the duration for animation in Carousel for Xamarin.Android
platform : Xamarin.Android
control : SfCarousel
documentation : ug
---

# Animation

The Duration property of the SfCarousel control is used to specify the time taken to move an item to the selected item position. The duration is specified in seconds. The default value is 300s.

{% highlight C# %}

SfCarousel carousel= new SfCarousel(this);

carousel.Duration=500;

{% endhighlight %}
