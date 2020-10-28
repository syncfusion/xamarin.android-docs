---
layout: post
title: Tapped event for Syncfusion Essential SfTabView.
description: Tapped event in TabView control for Xamarin.Android platform
platform: Xamarin.Android
control: TabView
documentation: ug
---

# TabItemTapped

Whenever the TabItem is tapped, the `TabItemTapped` event will occur. Using this event, you can Modify the selected Tab Item properties.

{% tabs %}

{% highlight C# %}

SfTabView tabView;

protected override void OnCreate(Bundle savedInstanceState)
{
    base.OnCreate(savedInstanceState);
    tabView = new SfTabView(this)
    {
        VisibleHeaderCount = 3,
        Items = new TabItemCollection
                {
                    new SfTabItem() { Title = "Call", Content = callsTabItem },
                    new SfTabItem() { Title = "Favorite", Content = favoritesTabItem },
                    new SfTabItem() { Title = "Contacts", Content = contactsTabItem }
                }
    };
    tabView.TabItemTapped += TabView_TabItemTapped;
    SetContentView(tabView);
}
private void TabView_TabItemTapped(object sender, TabItemTappedEventArgs e)
{
    Android.App.AlertDialog.Builder alertDialog = new Android.App.AlertDialog.Builder(this);
    alertDialog.SetTitle("TabViewItem Tapped");
    alertDialog.SetMessage(e.TabItem.Title + " Item Tapped");
    alertDialog.SetNeutralButton("OK", (c, eve) => { });
    alertDialog.Show();
}

{% endhighlight %}

{% endtabs %}

![TabItemTapped](images/TabView-Events/TabItemTapped.png)