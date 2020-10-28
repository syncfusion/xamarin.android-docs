---
layout: post
title: NavigationMode of Syncfusion Rotator control for Xamarin.Forms 
description: Learn how to view the different navigation modes of the Rotator control in Xamarin.Forms
platform: Xamarin.Forms 
control: Rotator
documentation: ug
---

# Navigation Modes

The `NavigationStripMode` property specifies the appearance of navigation bar items. The image data can be selected either by Thumbnail or by Dots navigation modes.

* `Thumbnail` - The slider items will be loaded in thumbnail view additionally. When a thumbnail item is clicked, the slider will switch to the corresponding image data.

{% highlight C# %}

SfRotator rotator = new SfRotator(this);
rotator.NavigationStripMode = NavigationStripMode.Thumbnail;	

{% endhighlight %}

![](images/thumbnail1.png)

* `Dots` - The slider items will be loaded in dots view additionally. When a dots item is clicked, the slider will switch to the corresponding image data.

{% highlight C# %}

SfRotator rotator = new SfRotator(this);
rotator.NavigationStripMode = NavigationStripMode.Dots;	

{% endhighlight %}

![](images/rotator.png)

## Items / Dot Strip Positions

The `NavigationStripPosition` specifies the placement position of the navigation bar items such as thumbnail or dots relative to the slider area. 

There are four available positions,

* `Bottom` - Sets the position of the navigation bar items to the bottom.
* `Left` - Sets the position of the navigation bar items to the left.
* `Top` - Sets the position of the navigation bar items to the top.
* `Right` - Sets the position of the navigation bar items to the right.

{% highlight C# %}

SfRotator rotator = new SfRotator(this);
rotator.NavigationStripPosition = NavigationStripPosition.Top;

{% endhighlight %}

![](images/top.png)