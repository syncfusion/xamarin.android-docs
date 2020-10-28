---
layout: post
title: ItemSelected Event in Syncfusion SfTreeMap control
description: This section explains the ItemSelected event support in TreeMap. 
platform: Xamarin.Android
control: TreeMap
documentation: ug
---

# TreeMap Events

## ItemSelected

The [`ItemSelected`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Treemap.SfTreeMap.html) event occurs when an item is selected. The selected leaf node underlying data item and the IsSelected boolean property will be passed as arguments to [`ItemSelectedEventArgs`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Treemap.TreeMapSelectedEventArgs.html). The [`IsSelected`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Treemap.TreeMapSelectedEventArgs.html#Com_Syncfusion_Treemap_TreeMapSelectedEventArgs_IsSelected) property indicates whether the item has been selected.

Set the [`HighlightOnSelection`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Treemap.SfTreeMap.html#Com_Syncfusion_Treemap_SfTreeMap_HighlightOnSelection) property to true to use the `ItemSelected` event.

{% tabs %}

{% highlight C# %}

treeMap.HighlightOnSelection = true;

treeMap.ItemSelected += TreeMap_ItemSelected;

private void TreeMap_ItemSelected(object sender, TreeMapSelectedEventArgs e)
        {
           
        }

{% endhighlight %}

{% endtabs %}

