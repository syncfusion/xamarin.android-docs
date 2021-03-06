---
layout: post
title: Popup Animations | SfPopupLayout |Xamarin.Android | Syncfusion
description: Animations in SfPopupLayout
platform: Xamarin.Android
control: SfPopupLayout
documentation: ug
--- 

# Popup Animations

Built-in animations are available in SfPopupLayout, which is applied when the PopupView opens and closes in the screen.
SfPopupLayout has different animation modes as listed below.

* [Zoom](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.AnimationMode.html)
* [Fade](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.AnimationMode.html)
* [SlideOnLeft](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.AnimationMode.html)
* [SlideOnRight](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.AnimationMode.html)
* [SlideOnTop](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.AnimationMode.html)
* [SlideOnBottom](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.AnimationMode.html)
* [None](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.AnimationMode.html)


N> Setting of AnimationMode is same for both `Displaying pop-up when the SfPopupLayout is set as root view` and `Displaying pop-up when the SfPopupLayout is not set as root view` 

## Zoom 

Zoom-out animation will be applied when the PopupView opens and Zoom-in animation will be applied when the PopupView closes.

{% tabs %}
{% highlight c# %}

//MainActivity.cs

protected override void OnCreate(Bundle bundle)
{
	....
    popupLayout.PopupView.AnimationMode = AnimationMode.Zoom;
    SetContentView(popupLayout);
    ....
}

{% endhighlight %}
{% endtabs %}

Executing the above codes renders the following output in an android device.

![](GettingStarted_images/ZoomAnimation.gif)

## Fade 

Fade-out animation will be applied when the PopupView opens and Fade-in animation will be applied when the PopupView closes

{% tabs %}
{% highlight c# %}

//MainActivity.cs

protected override void OnCreate(Bundle bundle)
{
	....
    popupLayout.PopupView.AnimationMode = AnimationMode.Fade;
    SetContentView(popupLayout);
    ....
}

{% endhighlight %}
{% endtabs %}

Executing the above codes renders the following output in an android device.

![](GettingStarted_images/FadeAnimation.gif)

## SlideOnLeft 

PopupView will be animated from left-to-right, when it opens and from right-to-left when the PopupView closes.

{% tabs %}
{% highlight c# %}

//MainActivity.cs

protected override void OnCreate(Bundle bundle)
{
	....
    popupLayout.PopupView.AnimationMode = AnimationMode.SlideOnLeft;
    SetContentView(popupLayout);
    ....
}

{% endhighlight %}
{% endtabs %}

Executing the above codes renders the following output in an android device.

![](GettingStarted_images/SlideOnLeftAnimation.gif)

## SlideOnRight

PopupView will be animated from right-to-left, when it opens and from left-to-right when the PopupView closes.

{% tabs %}
{% highlight c# %}

//MainActivity.cs

protected override void OnCreate(Bundle bundle)
{
    ....
    popupLayout.PopupView.AnimationMode = AnimationMode.SlideOnRight;
    SetContentView(popupLayout);
    ....
}
{% endhighlight %}
{% endtabs %}

Executing the above codes renders the following output in an android device.

![](GettingStarted_images/SlideOnRightAnimation.gif)

## SlideOnTop 

PopupView will be animated from top-to-bottom, when it opens and from bottom-to-top when the PopupView closes.

{% tabs %}
{% highlight c# %}

//MainActivity.cs

protected override void OnCreate(Bundle bundle)
{
	....
    popupLayout.PopupView.AnimationMode = AnimationMode.SlideOnTop;
    SetContentView(popupLayout);
    ....
}

{% endhighlight %}
{% endtabs %}

Executing the above codes renders the following output in an android device.

![](GettingStarted_images/SlideOnTopAnimation.gif)

## SlideOnBottom

PopupView will be animated from bottom-to-top, when it opens and from top-to-bottom when the PopupView closes.

{% tabs %}
{% highlight c# %}

//MainActivity.cs

protected override void OnCreate(Bundle bundle)
{
    ....
    popupLayout.PopupView.AnimationMode = AnimationMode.SlideOnBottom;
    SetContentView(popupLayout);
    ....
}
{% endhighlight %}
{% endtabs %}

Executing the above codes renders the following output in an android device.

![](GettingStarted_images/SlideOnBottomAnimation.gif)

## None

Animation will not be applied.

{% tabs %}
{% highlight c# %}

//MainActivity.cs

protected override void OnCreate(Bundle bundle)
{
	....
    popupLayout.PopupView.AnimationMode = AnimationMode.None;
    SetContentView(popupLayout);
    ....
}

{% endhighlight %}
{% endtabs %}

Executing the above codes renders the following output in an android device.

![](GettingStarted_images/AnimationMode_None.gif)
