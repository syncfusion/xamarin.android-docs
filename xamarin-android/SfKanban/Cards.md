---
layout: post
title: Cards for Essential xamarin.android Kanban
description: Kanban Cards
platform: xamarin.android
control: Kanban
documentation: ug
---

# Cards

The default elements of a card can be customized using the following properties of [`KanbanModel`](http://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanModel.html):

* [`Title`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanModel.html#Syncfusion_SfKanban_Android_KanbanModel_Title): Sets the title of a card.
* [`ImageURL`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanModel.html#Syncfusion_SfKanban_Android_KanbanModel_ImageURL): Sets the image URL of a card. The image will be displayed at the right in the default card template.
* [`Category`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanModel.html#Syncfusion_SfKanban_Android_KanbanModel_Category): Sets the category of a card. Based on the category, the cards will be added to the respective columns.
* [`Description`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanModel.html#Syncfusion_SfKanban_Android_KanbanModel_Description): Sets the description text of a card.
* [`ColorKey`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanModel.html#Syncfusion_SfKanban_Android_KanbanModel_ColorKey): Specifies the indicator color key. The color value of the corresponding [`Key`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanColorMapping.html#Syncfusion_SfKanban_Android_KanbanColorMapping_Key) should be added in [`IndicatorColorPalette`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.SfKanban.html#Syncfusion_SfKanban_Android_SfKanban_IndicatorColorPalette) collection of [`SfKanban`](http://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.SfKanban.html).
* [`Tags`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanModel.html#Syncfusion_SfKanban_Android_KanbanModel_Tags): Specifies the tags of a card. The tags will be displayed at the bottom in the default card template.
* [`ID`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanModel.html#Syncfusion_SfKanban_Android_KanbanModel_ID): Sets the ID of a card.

{% highlight C# %}

new KanbanModel()
{
    ID = 1,
    Title = "iOS - 1002",
    ImageURL = "Image1.png",
    Category = "Open",
    Description = "Analyze customer requirements",
    ColorKey = "Red",
    Tags = new string[] { "Incident", "Customer" }
});

{% endhighlight %}

The following code sample is used to define the colors for each key.

{% highlight C# %}

List<KanbanColorMapping> colorModels = new List<KanbanColorMapping>();
colorModels.Add(new KanbanColorMapping("Green", Color.Green));
colorModels.Add(new KanbanColorMapping("Red", Color.Red));
colorModels.Add(new KanbanColorMapping("Aqua", Color.Aqua));
colorModels.Add(new KanbanColorMapping("Blue", Color.Blue));
kanban.IndicatorColorPalette = colorModels;

{% endhighlight %}

![CardCustomization](Kanban_images/CardCustomization.png)

