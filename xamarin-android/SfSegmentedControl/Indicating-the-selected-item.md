---
layout: post
title: selection indicator in Syncfusion SegmentedControl for Xamarin.Android
description: Learn how to handle selection indicator settings, selection text color and selection strip in Segmented control
platform: Xamarin.Android
control: SegmentedControl
documentation: ug
---

# Indicating the selected item

The segmented control indicates the selected item by differentiating it with the text color of the item or by using selection strip.

## Selection text color

The user can change the text color of the Selected item to desired color.The selected item text color can be customized by the [`SelectionTextColor`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentedControl.html#Syncfusion_Android_Buttons_SfSegmentedControl_SelectionTextColor) property.

{% highlight c# %}

[C#]

segmentedControl.SelectionTextColor = Color.ParseColor("#02A0AE");

{% endhighlight %}

![Xamarin.Android SfSegmentedControl selection text color](images/Selection-indicator/Xamarin_Android_selectiontextcolor.png)

## Selection Strip

A selection strip is used to indicate the selected item in the segmented control. The selection strip can be customized in many forms.

#### Position

The position of the selection indicator can be customized by the user in different ways.

##### Top

The selection strip can be displayed as a line with customizable color and thickness. It can be positioned at the top of an item.

{% highlight c# %}

[C#]

segmentedControl.SelectionIndicatorSettings = new SelectionIndicatorSettings()
{
    Position = Position.Top
};

{% endhighlight %}

![Selection Strip Top](images/Selection-indicator/Xamarin_Android_Top.png)

##### Bottom

As like Top placement selection strip can be customized by its color and thickness which can be positioned at the bottom of an item.

{% highlight c# %}

[C#]

segmentedControl.SelectionIndicatorSettings = new SelectionIndicatorSettings()
{
    Position = Position.Bottom
};

{% endhighlight %}

![Selection Strip Bottom](images/Selection-indicator/Xamarin_Android_Bottom.png)

##### Fill

The selection strip can be placed over a segment item to indicate it is selected. You can customize its color to highlight the item.

{% highlight c# %}

[C#]

segmentedControl.SelectionIndicatorSettings = new SelectionIndicatorSettings()
{
    Position = Position.Fill
};

{% endhighlight %}

![Selection Strip Fill](images/Selection-indicator/Xamarin_Android_Fill.png)

##### Border

The selection strip can be set as a border to highlight the selected item.

{% highlight c# %}

[C#]

segmentedControl.SelectionIndicatorSettings = new SelectionIndicatorSettings()
{
    Position = Position.Border
};

{% endhighlight %}

![Selection Strip Border](images/Selection-indicator/Xamarin_Android_Border.png)

#### Color

The background color of the selection strip can be customized using [`Color`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentItem.html#Syncfusion_Android_Buttons_SfSegmentItem_SelectionBackgroundColor) property which is inside SelectionIndicatorSettings class.

{% highlight c# %}

[C#]

segmentedControl.SelectionIndicatorSettings = new SelectionIndicatorSettings()
{
    Color = Color.ParseColor("#2C7BBC")
};

{% endhighlight %}

![Selection Strip Color](images/Selection-indicator/Xamarin_Android_stripcolor.png)

#### Thickness

The border thickness of the selection strip can be customized using [`Thickness`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentedControl.html#Syncfusion_Android_Buttons_SfSegmentedControl_SegmentBorderThickness) property which is inside SelectionIndicatorSettings class

{% highlight c# %}

[C#]

segmentedControl.SelectionIndicatorSettings = new SelectionIndicatorSettings()
{
    StrokeThickness = 10
};

{% endhighlight %}
