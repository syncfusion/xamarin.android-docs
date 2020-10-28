---
layout : post
title : Transformation in Syncfusion Carousel control in Xamarin.Android
description : Learn how to set the Transformation in Carousel for Xamarin.Android
platform : Xamarin.Android
control : Carousel
documentation : ug
---

# Transformation

## Tilt Non Selected Items

The `RotationAngle` property in the SfCarousel control is used to rotate all the items in a specified angle. 

If the angle value is positive, then the rotation is in the clockwise direction. If the angle value is negative, the rotation is in the counterclockwise direction. 

N> This angle can also be specified from 0 to 360.

{% highlight C# %}

SfCarousel carousel = new SfCarousel(this);

carousel.RotationAngle=40;

{% endhighlight %}


![](images/rotationangle.png)

## Set Gap between Unselected Items

Specify the distance between the items in SfCarousel panel using `Offset` property.

N> The default value is 20.

{% highlight C# %}

SfCarousel carousel = new SfCarousel(this);

carousel.Offset=30;

{% endhighlight %}

![](images/offset.png)

## Set Gap between Selected Item and Unselected Item

Distance between the selected item and other items can be customized by using `SelectedItemOffset` property.

N> The default value is 0.

{% highlight C# %}

SfCarousel carousel = new SfCarousel(this);

carousel.SelectedItemOffset=5;

{% endhighlight %}

## Set Scaling for Carousel Items

The `ScaleOffset` property in the SfCarousel control is used to scale all the unselected items to the specified scale value.

{% highlight C# %}
	
SfCarousel carousel = new SfCarousel(this);
carousel.ScaleOffset=0.7f;

{% endhighlight %}


![](images/scaleoffset.png)

## Spacing between the Items in Linear mode

Spacing of all the items in Linear mode can be determined by using `ItemSpacing` property.

{% highlight C# %}

SfCarousel carousel = new SfCarousel();
carousel.ItemSpacing=5;
carousel.ViewMode=ViewMode.Linear;

{% endhighlight %}
