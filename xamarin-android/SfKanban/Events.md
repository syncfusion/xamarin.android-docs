---
layout: post
title: Events in xamarin.android Kanban control
description: Kanban Events
platform: xamarin.android
control: Kanban
documentation: ug
---

# Events

## ItemTapped

[`ItemTapped`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.SfKanban.html) event is triggered when you tap any card. The argument contains the following information:

* [`Column`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanTappedEventArgs.html#Syncfusion_SfKanban_Android_KanbanTappedEventArgs_Column): Gets the column of a card.
* [`Data`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanTappedEventArgs.html#Syncfusion_SfKanban_Android_KanbanTappedEventArgs_Data): Gets the underlying model of a card.
* [`Index`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanTappedEventArgs.html#Syncfusion_SfKanban_Android_KanbanTappedEventArgs_Index): Gets the index of a card in a column.
* [`ViewCell`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanTappedEventArgs.html#Syncfusion_SfKanban_Android_KanbanTappedEventArgs_ViewCell): Gets the tapped view cell.

## DragStart

[`DragStart`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.SfKanban.html) event is triggered when you start to drag a card. The argument contains the following information:

* [`Cancel`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragStartEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragStartEventArgs_Cancel): Cancels the drag action.
* [`Data`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragEventArgs_Data): Gets the underlying model of a card.
* [`KeepItem`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragStartEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragStartEventArgs_KeepItem): Determines whether to keep the dragged card in the source location until it is dropped in a new location. When it is true, the preview of the card will be created for dragging.
* [`SourceColumn`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragEventArgs_SourceColumn): Gets the source column of a card.
* [`SourceIndex`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragEventArgs_SourceIndex): Gets the index of the card in a source column.

## DragEnd  

[`DragEnd`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.SfKanban.html) event is triggered whenever a card is dropped or a dragging action is canceled. The argument contains the following information:

* [`Cancel`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragEndEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragEndEventArgs_Cancel): Cancels the drag action.
* [`Data`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragEventArgs_Data): Gets the underlying model of a card.
* [`SourceColumn`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragEventArgs_SourceColumn): Gets the source column of a card.
* [`SourceIndex`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragEventArgs_SourceIndex): Gets the index of the card in a source column.
* [`TargetCategory`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragEndEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragEndEventArgs_TargetCategory): Gets the category of a column where the card is going to be dropped.
* [`TargetColumn`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragEndEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragEndEventArgs_TargetColumn): Gets the current column, which is the drop target for a card.
* [`TargetIndex`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragEndEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragEndEventArgs_TargetIndex): Gets the index of the card in a target column.

## DragEnter 

[`DragEnter`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.SfKanban.html) event is triggered when a card enters into a column when dragging. The argument contains the following information:

* [`Cancel`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragEnterEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragEnterEventArgs_Cancel): Cancels the drag action.
* [`Data`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragEventArgs_Data): Gets the underlying model of a card.
* [`IsAboveMaximumLimit`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragEnterEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragEnterEventArgs_IsAboveMaximumLimit): Determines whether the total cards count of the target column should be above the maximum limit if you drop the card in target column. You can define the maximum limit of the cards using the `KanbanColumn.MaximumLimit` property.
* [`SourceColumn`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragEventArgs_SourceColumn): Gets the source column of a card.
* [`SourceIndex`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragEventArgs_SourceIndex): Gets the index of the card in a source column.
* [`TargetColumn`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragEnterEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragEnterEventArgs_TargetColumn): Gets the column upon which the card enters.
* [`TargetIndex`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragEnterEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragEnterEventArgs_TargetIndex): Gets the index of the card in a target column.

## DragLeave 

[`DragLeave`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.SfKanban.html) event is triggered when a card leaves a column when dragging. The argument contains the following information:

* [`Data`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragEventArgs_Data): Gets the underlying model of a card.
* [`IsBelowMinimumLimit`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragLeaveEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragLeaveEventArgs_IsBelowMinimumLimit): Determines whether the total cards count of the target column should be below the minimum limit if you remove the card from target column. You can define the minimum limit of the cards using the `KanbanColumn.MinimumLimit` property.
* [`SourceColumn`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragEventArgs_SourceColumn): Gets the source column of a card.
* [`SourceIndex`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragEventArgs_SourceIndex): Gets the index of the card in a source column.
* [`TargetColumn`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragLeaveEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragLeaveEventArgs_TargetColumn): Gets the column from which the card leaves.

## DragOver

[`DragOver`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.SfKanban.html) event is triggered when a card is dragged to a new index within a column. The argument contains the following information:

* [`Cancel`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragOverEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragOverEventArgs_Cancel): Cancels the drag action.
* [`Data`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragEventArgs_Data): Gets the underlying model of a card.
* [`SourceColumn`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragEventArgs_SourceColumn): Gets the source column of a card.
* [`SourceIndex`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragEventArgs_SourceIndex): Gets the index of the card in source column.
* [`TargetColumn`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragOverEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragOverEventArgs_TargetColumn): Gets the current column, which is the drop target for a card.
* [`TargetIndex`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.KanbanDragOverEventArgs.html#Syncfusion_SfKanban_Android_KanbanDragOverEventArgs_TargetIndex): Gets a new index of a card in target column.

## ColumnsGenerated 

[`ColumnsGenerated`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.SfKanban.html) event will be fired after the columns are generated automatically. You can access the auto-generated columns using the [`SfKanban.ActualColumns`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfKanban.Android.SfKanban.html#Syncfusion_SfKanban_Android_SfKanban_ActualColumns) property.

