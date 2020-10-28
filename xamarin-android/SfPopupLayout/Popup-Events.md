---
layout: post
title: Popup Events| SfPopupLayout |Xamarin.Android| Syncfusion
description: How to use different events exposed in SfPopupLayout.
platform: Xamarin.Android
control: SfPopupLayout
documentation: ug
--- 

# Events

There are four built-in events in the SfPopupLayout control namely:

* Opening
* Opened
* Closing
* Closed

## Opening event

The [SfPopupLayout.Opening](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.SfPopupLayout.html) event will be fired whenever opening the Pop-upView in the application. It can cancel the pop-up opening with `CancelEventArgs` that contains the following property:

* [Cancel](https://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true): Pop-up opening is based on this value.

{% tabs %}
{% highlight c# %}
//MainActivity.cs

protected override void OnCreate(Bundle bundle)
{
	....
    popupLayout.Opening += PopupLayout_Opening;
    SetContentView(popupLayout);
    ....
}

private void PopupLayout_Opening(object sender, System.ComponentModel.CancelEventArgs e)
{
    e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

## Opened event

The [SfPopupLayout.Opened](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.SfPopupLayout.html) event will be fired whenever displaying the Pop-upView in the application.

You can execute your own set of codes once the pop-up is opened and visible in the application in its respective event handler.

{% tabs %}
{% highlight c# %}
//MainActivity.cs

protected override void OnCreate(Bundle bundle)
{
	....
    popupLayout.Opened += PopupLayout_Opened;
    SetContentView(popupLayout);
    ....
}

private void PopupLayout_Opened(object sender, EventArgs e)
{
    // Codes that needs to be executed once popup is visible in the screen
}
{% endhighlight %}
{% endtabs %}

## Closing event

The [SfPopupLayout.Closing](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.SfPopupLayout.html) event will be fired whenever closing the Pop-upView in the application.  It can cancel pop-up closing with `CancelEventArgs` that contains the following property:

* [Cancel](https://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true): Pop-up opening is based on this value.

{% tabs %}
{% highlight c# %}
//MainActivity.cs

protected override void OnCreate(Bundle bundle)
{
	....
    popupLayout.Closing += PopupLayout_Closing;
    SetContentView(popupLayout);
    ....
}

private void PopupLayout_Closing(object sender, System.ComponentModel.CancelEventArgs e)
{
    e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

## Closed event

The [SfPopupLayout.Closed](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.SfPopupLayout.html) event will be fired whenever dismissing the Pop-upView from the view.

You can execute your own set of codes once the popup is completely closed in its respective event handler.

{% tabs %}
{% highlight c# %}
//MainActivity.cs

protected override void OnCreate(Bundle bundle)
{
	....
    popupLayout.Closed += PopupLayout_Closed;
    SetContentView(popupLayout);
    ....
}

private void PopupLayout_Closed(object sender, EventArgs e)
{
    // Codes that needs to be executed once popup is completely closed
}
{% endhighlight %}
{% endtabs %}

## Footer button clicked events

Following two events are available in the footer:

* AcceptButtonClicked
* DeclineButtonClicked

### AcceptButtonClicked

The SfPopupLayout.PopupView.AcceptButtonClicked will be fired when clicking the Accept button in the pop-up footer. It can cancel pop-up closing with `CancelEventArgs` that contains the following property:

* [Cancel](https://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true): Pop-up opening is based on this value.

{% tabs %}
{% highlight c# %}
public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.PopupView.AppearanceMode = AppearanceMode.TwoButton;
    popupLayout.PopupView.AcceptButtonClicked += PopupView_AcceptButtonClicked;
    ....
}

private void PopupView_AcceptButtonClicked(object sender, System.ComponentModel.CancelEventArgs e)
{
     e.Cancel = true;
}

{% endhighlight %}
{% endtabs %}

### DeclineButtonClicked

The SfPopupLayout.PopupView.DeclineButtonClicked will be fired when clicking the Decline button in the pop-up footer. It can cancel pop-up closing with `CancelEventArgs` that contains the following property:

* [Cancel](https://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true): Pop-up opening is based on this value.

{% tabs %}
{% highlight c# %}
public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.PopupView.AppearanceMode = AppearanceMode.TwoButton;
    popupLayout.PopupView.DeclineButtonClicked += PopupView_DeclineButtonClicked;
    ....
}

private void PopupView_DeclineButtonClicked(object sender, System.ComponentModel.CancelEventArgs e)
{
    e.Cancel = true;
}

{% endhighlight %}
{% endtabs %}
