---
layout: post
title: States
description: States.
platform: Xamarin.Android
control: ProgressBar
documentation: ug
---

# States

Based on the progress estimation, you can configure the states of the progress bar.

## Determinate

This is the default state. You can use it when the progress estimation is known.

## Indeterminate

By enabling the [`IsIndeterminate`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.ProgressBar.ProgressBarBase.html#Syncfusion_Android_ProgressBar_ProgressBarBase_IsIndeterminate) property, the state of the progress bar can be changed to indeterminate when progress cannot be estimated or is not being calculated. It can be combined with determinate mode to let users know that the app is estimating progress before actual progress starts.

{% highlight c# %}

// Using linear progress bar. 
SfLinearProgressBar sfLinearProgressBar = new SfLinearProgressBar(this);            
sfLinearProgressBar.IsIndeterminate = true;            
// Using circular progress bar.
SfCircularProgressBar circularProgressBar = new SfCircularProgressBar(this);            
circularProgressBar.IsIndeterminate = true;            

{% endhighlight %} 

## Buffer

The secondary task’s progress can be defined by using the [`SecondaryProgress`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.ProgressBar.SfLinearProgressBar.html#Syncfusion_Android_ProgressBar_SfLinearProgressBar_SecondaryProgress) property as shown in the following code example.

{% highlight c# %}

SfLinearProgressBar sfLinearProgressBar = new SfLinearProgressBar(this);

sfLinearProgressBar.Progress = 75;

sfLinearProgressBar.SecondaryProgress = 25;

{% endhighlight %}

![](overview_images/buffer.png)
