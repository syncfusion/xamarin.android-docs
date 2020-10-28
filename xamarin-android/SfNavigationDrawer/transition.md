---
layout: post
title: Transition of drawer in Syncfusion NavigationDrawer control for Xamarin.Android
description: Learn how to set Transition of the DrawerView panel.
platform: Xamarin.Android
control: NavigationDrawer
documentation: ug
---
# Drawer Opening Animation

The `Transition` property specifies the sliding animations for the DrawerView panel. The `Transition` property has the following three options,

* SlideOnTop
* Push
* Reveal

N> The default transition is SlideOnTop.

## SlideOnTop

Slides the DrawerContent on top of the main content.

{% highlight c# %} 

	 Transition sliderTransition = Transition.SlideOnTop;
	 navigationDrawer.Transition = sliderTransition;

{% endhighlight %}

![](images/Slide-on-top.png)

## Push

This transition slides the Drawer and main content simultaneously.

{% highlight c# %} 

	 Transition sliderTransition = Transition.Push;
	 navigationDrawer.Transition = sliderTransition;

{% endhighlight %}

![](images/Push.png)

## Reveal

This transition keeps the Drawer content in fixed position and the main content will be slide to reveal the drawer content.

{% highlight c# %} 

	Transition sliderTransition = Transition.Reveal;
	navigationDrawer.Transition = sliderTransition;

{% endhighlight %}

![](images/reveal.png)
