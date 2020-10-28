---
layout: post
title: Tab Items
description: About Tab items in TabView control for Xamarin.Android platform
platform: Xamarin.Android
control: TabView
documentation: ug
---

# Tab Items

Tab items can be configured in tab view through the Items property of `SfTabView`, where it holds collection of `SfTabItem` through `TabItemsCollection`


{% tabs %}

{% highlight C# %}

var allContactsGrid = new FrameLayout(ApplicationContext);
var favoritesGrid = new FrameLayout(ApplicationContext);
var contactsGrid = new FrameLayout(ApplicationContext);
allContactsGrid.SetBackgroundColor(Color.Red);
favoritesGrid.SetBackgroundColor(Color.Green);
contactsGrid.SetBackgroundColor(Color.Blue);
var tabItems = new TabItemCollection
{
new SfTabItem()
{
Title = "Calls",
Content = allContactsGrid
},
new SfTabItem()
{
Title = "Favorites",
Content = favoritesGrid
},
new SfTabItem()
{
Title = "Contacts",
Content = contactsGrid
}
};

tabView.Items = tabItems;
SetContentView(tabView);

{% endhighlight %}

{% endtabs %}

## Share the header space equally

In order to share the header space equally for the , we can set the number of tabs which can be distributed in the available space though `VisibleHeaderCount` of SfTabView.

{% tabs %}

{% highlight C# %}

tabView.VisibleHeaderCount = 3;

{% endhighlight %}

{% endtabs %}


