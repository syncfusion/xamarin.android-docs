---
layout: post
title:  Custom Header
description: Custom Header in Syncfusion TabView control for Xamarin.Android platform
platform: Xamarin.Android
control: TabView
documentation: ug
---

# Custom Header 

When built-in view is not needed, it can be overridden by adding custom view for the header region for a tab. 

{% tabs %}

{% highlight C# %}

Button allCallsButton = new Button(context);
allCallsButton.Text = "All Calls";
allCallsButton.SetBackgroundColor(Android.Graphics.Color.Yellow);
allCallsButton.Clicked += AllCallsButton_Clicked;
var tabViewItem = new SfTabItem()
{
Title = "Calls",
Content = allContactsGrid,
HeaderContent = allCallsButton
};
			
{% endhighlight %}

{% endtabs %}

## How to handle events for custom view with tab view?

When using button or similar control with clicked event, it can be handled directly and set the SelectedIndex property to navigate the clicked view.

{% highlight C# %}

private void Button_Clicked(object sender, System.EventArgs e)
{
tabView.SelectedIndex = 0;
}
			
{% endhighlight %}

