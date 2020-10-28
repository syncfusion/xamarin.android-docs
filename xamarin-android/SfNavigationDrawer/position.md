---
layout: post
title: Position of Drawer in Syncfusion NavigationDrawer control for Xamarin.Android
description: Learn how to set position of the DrawerView panel.
platform: Xamarin.Android
control: NavigationDrawer
documentation: ug
---
# Configuring The Drawer In Different Sides

The `Position` property specifies the sliding position of the DrawerView panel. The `Position` property has the following four options,

* Left

* Right

* Top

* Bottom

N> The default option is Left.

## Left

Sets the SfNavigationDrawer sliding position to the left.

{% tabs %}

{% highlight c# %}

	Position sliderposition = Position.Left;	
	navigationDrawer.Position=sliderposition;

{% endhighlight %}

{% endtabs %}

![](images/Left.png)

## Right

Sets the SfNavigationDrawer sliding position to the right.

{% tabs %}

{% highlight c# %}

	Position sliderposition = Position.Right;	
	navigationDrawer.Position=sliderposition;

{% endhighlight %}

{% endtabs %}

![](images/Right.png)
	
## Top

Sets the SfNavigationDrawer sliding position to the top.

{% tabs %}

{% highlight c# %}

	Position sliderposition = Position.Top;	
   	navigationDrawer.Position=sliderposition;

{% endhighlight %}

{% endtabs %}

![](images/Top.png)

## Bottom

Sets the SfNavigationDrawer sliding position to the bottom.

{% highlight c# %}

	Position sliderposition = Position.Bottom;	
	navigationDrawer.Position=sliderposition;

{% endhighlight %}

![](images/bottom.png)






