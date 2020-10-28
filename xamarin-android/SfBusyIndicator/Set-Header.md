---
layout: post
title: Set title to the Syncfusion BusyIndicator control for Xamarin.Android
description: Learn how to set title and fontface to BusyIndicator control
platform: Xamarin.Android
control: SfBusyIndicator
documentation: ug
---

# Set Header

SfBusyIndicator provides option to set the text that indicates the information related to loading. This can be done using `Title` property.

{% tabs %}

{% highlight c# %}

	SfBusyIndicator busyIndicator = new SfBusyIndicator(this);
	busyIndicator.AnimationType = AnimationTypes.Battery;
	busyIndicator.Title="Loading...";
	
{% endhighlight %}

{% endtabs %}

![](images/Title_img1.png) 
                                          
BusyIndicator with title
{:.caption}

## FontFace

User can modify the Font style and Font size of the title which is displayed beneath the animation. `FontFace` property can be used to modify these settings. 

{% tabs %}

{% highlight c# %}

	SfBusyIndicator busyIndicator = new SfBusyIndicator(this);
	busyIndicator.AnimationType=AnimationTypes.Battery;
	busyIndicator.Title="Loading...";
	busyIndicator.Fontface=Typeface.create("Arial",Typeface.NONE);

{% endhighlight %}

{% endtabs %}

![](images/Title_img2.png)   
                                                  
BusyIndicator with font face
{:.caption}

