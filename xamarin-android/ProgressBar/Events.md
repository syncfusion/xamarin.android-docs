---
layout: post
title: Events
platform: Xamarin.Android
control: ProgressBar
documentation: ug
---

# Events

## ValueChanged

This event is triggered when the progress value is changed. This event contains the following event argument.

* [`Progress`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.ProgressBar.ProgressValueEventArgs.html#Syncfusion_Android_ProgressBar_ProgressValueEventArgs_Progress): Represents the progress value.

The following code example shows how to customize the color of a progress indicator based on progress using this event. 

{% highlight c# %}

SfLinearProgressBar linearProgressBar = new SfLinearProgressBar(this);

linearProgressBar.Progress = 100;

linearProgressBar.ValueChanged += this.ProgressBarBase_OnValueChanged;

private void ProgressBarBase_OnValueChanged(object sender, ProgressValueEventArgs e)
{   
    if (e.Progress < 50)
    {
        this.linearProgressBar.ProgressColor = Android.Graphics.Color.Red;
    }
    else if (e.Progress >= 50)
    {
        this.linearProgressBar.ProgressColor = Android.Graphics.Color.Green; 
    }
}

{% endhighlight %}

## ProgressCompleted

This event is triggered when the progress attains the [`Maximum`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.ProgressBar.ProgressBarBase.html#Syncfusion_Android_ProgressBar_ProgressBarBase_Maximum) value. This event contains the following argument.

* [`Progress`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.ProgressBar.ProgressValueEventArgs.html#Syncfusion_Android_ProgressBar_ProgressValueEventArgs_Progress):  Represents the progress value.

The following code example shows how to customize the progress bar when progress reaches maximum using this event. 

{% highlight c# %}

private SfCircularProgressBar circularProgressBar;

protected override void OnCreate(Bundle savedInstanceState)
{
		base.OnCreate(savedInstanceState);

		circularProgressBar = new SfCircularProgressBar(this);

		circularProgressBar.Minimum = 100;

		circularProgressBar.Maximum = 500;

		circularProgressBar.Progress = 500;

		circularProgressBar.ProgressCompleted += this.ProgressBarBase_OnProgressCompleted;

        circularProgressBar.Content = new TextView(this);

		(circularProgressBar.Content as TextView).SetText("Start", TextView.BufferType.Normal);

        SetContentView(circularProgressBar);
}

private void ProgressBarBase_OnProgressCompleted(object sender, ProgressValueEventArgs e)
{
    if (e.Progress.Equals(this.circularProgressBar.Maximum))
    {
       (this.circularProgressBar.Content as TextView).SetText("Completed", TextView.BufferType.Normal);
    }
}

{% endhighlight %}
 
