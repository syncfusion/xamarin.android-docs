---
layout : post
title : Getting Started with Syncfusion Carousel Control for Xamarin.Android
description : A quick tour to initial users on Syncfusion carousel control for Xamarin.Android platform.
platform : Xamarin.Android
control : SfCarousel
documentation : ug
---

# Getting Started

This section explains you the steps to configure a SfCarousel control in a real-time scenario and also provides a walk-through on some of the customization features available in SfCarousel control.

## Referencing Essential Studio components in your solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\15.x.x.x\lib

Add the following assembly references to the Android project,

android\Syncfusion.SfCarousel.Android.dll

and 

Xamarin.Android.Support.v17.Leanback library (from NuGet Packages)

## Add SfCarousel

The SfCarousel control is configured entirely in C# code. The following steps explain on how to create a SfCarousel and configure its elements,

* Adding namespace for the added assemblies. 

{% highlight C# %}

using Com.Syncfusion.Carousel;

{% endhighlight %}

* Now add the SfCarousel control with a required optimal name by using the included namespace.

{% highlight C# %}

SfCarousel carousel=new SfCarousel(this);
SetContentView(carousel);

{% endhighlight %}

## Set Gap between Items

SfCarousel provides option to set the distance between the items in the panel. This can be done by using the `Offset` property in SfCarousel control.

{% highlight C# %}

SfCarousel carousel = new SfCarousel(this);
carousel.Offset=20;

{% endhighlight %}

## Tilt Non Selected Items

Items in the SfCarousel control can be rotated in user defined angle. `RotationAngle` property is used to decide the angle in which items should be rotated.

{% highlight C# %}

SfCarousel carousel = new SfCarousel(this);
carousel.RotationAngle = 45;

{% endhighlight %}

## Setting DataSource

SfCarousel items can be populated with a collection of image data. For example, a user may want to create a SfCarousel control which will display a list of images.

{% highlight c# %}

List<SfCarouselItem> tempCollection = new List<SfCarouselItem>();

for (int i = 1; i <= 6; i++)
{
	SfCarouselItem sfCarouselItem = new SfCarouselItem(this);
	sfCarouselItem.ImageName = "image" + i.ToString();
	tempCollection.Add(sfCarouselItem);
}

carousel.SelectedIndex = 2;
carousel.DataSource = tempCollection;

{% endhighlight %}


### Setting the height and width of carousel's Item

`ItemHeight` and `ItemWidth` properties are used to change the height and width of carouselItem in carousel panel.

{% highlight C# %}

SfCarousel sfCarousel=new SfCarousel(this);
sfCarousel.ItemWidth=150;
sfCarousel.ItemHeight=170;

{% endhighlight %}

## SelectedIndex

We can bring particular item to the center of the screen using `SelectedIndex` property in SfCarousel control.

N> The `SelectedIndex` property will be 0 by default.

{% highlight c# %}

SfCarousel carousel=new SfCarousel(this);
carousel.SelectedIndex=2;

{% endhighlight %}

![](images/carousel.png)

You can find the complete getting started sample from this [Link](http://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStartedSampleCarousel39791457)