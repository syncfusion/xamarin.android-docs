---
layout: post
title: looping feature of Syncfusion Picker control for Xamarin.Android
description: This section will explain about how to enable and disable looping by using SfPicker control in Xamarin.Android.
platform: Xamarin.Android
control: Picker
documentation: ug
---


# Looping in Xamarin.Android

The Looping support is used to automatically navigate the first item to repeat the list of items after reached the last item. Each forward iteration is followed by a backward iteration in the picker control. This can be achieved by `EnableLooping` property.

## EnableLooping

The looping support is achieved by setting the `EnableLooping` property to true.

{% highlight c# %}

SfPicker picker = new SfPicker();

ColorInfo info = new ColorInfo();

picker.ItemsSource = info.Colors;

// Enable Looping in picker control

picker.EnableLooping = true;

{% endhighlight %}


Screen shot for the above codes.

![Looping](images/looping_and.png)

You can find the complete Looping sample from this [link](http://www.syncfusion.com/downloads/support/directtrac/208168/ze/Looping_1756767840).

## How to restrict Looping in a particular column of the picker

The looping support can be restricted in a particular column of the picker by setting the `EnableLooping` of ColumnLoaded event argument to false.

{% highlight c# %}

picker.OnColumnLoaded+=(object sender, ColumnLoadedEventArgs e) => 
{

if (e.Column == 0)
{
    e.EnableLooping = true;
}
else
    e.EnableLooping = false;
};

{% endhighlight %}

Screen shot for the above codes.

![Looping](images/looping_multi_and.png)

You can find the sample from this [link](http://www.syncfusion.com/downloads/support/directtrac/208168/ze/AutoReverse_Sample1257178886.zip).


