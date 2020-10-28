---
layout: post
title: PlaceholderStyle for Xamarin.Android Kanban
description: Kanban Placeholder style
platform: Xamarin.Android
control: Kanban
documentation: ug
---

# Placeholder

The placeholder is used to denote the new position of a card in the [`KanbanColumn`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanColumn.html). It will appear when dragging a card over the column.

### Placeholder style

The [`PlaceholderStyle`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.SfKanban.html#Syncfusion_SfKanban_Android_SfKanban_PlaceholderStyle) property is used to customize the placeholder. The following [`KanbanPlaceholderStyle`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanPlaceholderStyle.html) properties are used to customize its appearance:

* [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_Android_KanbanPlaceholderStyle_BackgroundColor) - Changes the background color of placeholder.
* [`DashGap`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_Android_KanbanPlaceholderStyle_DashGap) - Determines the dash gap of placeholder.
* [`DashWidth`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_Android_KanbanPlaceholderStyle_DashWidth) - Provides dash width of placeholder.
* [`StrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_Android_KanbanPlaceholderStyle_StrokeColor) - Changes the stroke color of placeholder.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_Android_KanbanPlaceholderStyle_StrokeWidth) - Changes the stroke width of placeholder.
* [`TextSize`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_Android_KanbanPlaceholderStyle_TextSize) - Changes the text size of placeholder.
* [`TextColor`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_Android_KanbanPlaceholderStyle_TextColor) - Changes the text color of placeholder.

The following properties are used to customize the selected category when you have more than one category in a column:

* [`SelectedBackgroundColor`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_Android_KanbanPlaceholderStyle_SelectedBackgroundColor) - Changes the background color of a selected placeholder.
* [`SelectedDashGap`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_Android_KanbanPlaceholderStyle_SelectedDashGap) - Determines the dash gap of a selected placeholder.
* [`SelectedDashWidth`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_Android_KanbanPlaceholderStyle_SelectedDashWidth) - Provides dash width of a selected placeholder.
* [`SelectedStrokeColor`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_Android_KanbanPlaceholderStyle_SelectedStrokeColor) - Changes the stroke color of a selected placeholder.
* [`SelectedStrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_Android_KanbanPlaceholderStyle_SelectedStrokeWidth) - Changes the stroke width of a selected placeholder.
* [`SelectedTextSize`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_Android_KanbanPlaceholderStyle_SelectedTextSize) - Changes the size of the text in a selected placeholder.
* [`SelectedTextColor`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanPlaceholderStyle.html#Syncfusion_SfKanban_Android_KanbanPlaceholderStyle_SelectedTextColor) - Changes the color of the text in a selected placeholder.

The following code example describes the above behavior.

{% highlight C# %}

KanbanPlaceholderStyle style = new KanbanPlaceholderStyle();
style.BackgroundColor = Color.Rgb(239, 89, 123);
style.DashGap = 1;
style.DashWidth = 1;
style.StrokeColor = Color.Blue;
style.StrokeWidth = 2;
style.TextSize = 20;
style.TextColor = Color.Green;

style.SelectedBackgroundColor = Color.Rgb(0, 255, 0);
style.SelectedDashGap = 2;
style.SelectedDashWidth = 1;
style.SelectedStrokeColor = Color.Yellow;
style.SelectedStrokeWidth = 2;
style.SelectedTextSize = 20;
style.SelectedTextColor = Color.Red;

kanban.PlaceholderStyle = style;

{% endhighlight %}

The following screenshot illustrates the result of the above code sample.

![PlaceholderStyle support for Xamarin.Android Kanban](SfKanban_images/PlaceholderStyle.png)

