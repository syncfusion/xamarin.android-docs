---
layout: post
title: Freeze Panes | SfDataGrid | Xamarin.Android | Syncfusion
description: How to freeze rows and columns in a SfDataGrid.
platform: Xamarin.Android
control: SfDataGrid
documentation: UG
---

# Freeze panes

The data grid allows freezing the rows and columns when scrolling the grid.

## Freeze rows

The data grid extensively supports freezing the rows at the top of the view and below the header row by setting the [SfDataGrid.FrozenRowsCount](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.SfDataGrid.html#Syncfusion_SfDataGrid_SfDataGrid_FrozenRowsCount) property. 

The following code example illustrates freezing two rows in the data grid.

{% highlight c# %}
//Setting number of rows to freeze in SfDataGrid
dataGrid.FrozenRowsCount = 2; 
{% endhighlight %}

### Limitation

* `FrozenRowsCount` should be less than the number of rows that is displayed in the view.

For example: If you have 10 rows in view, set `FrozenRowsCount` to a maximum value of 9.

N> The header row is frozen by default and works regardless of the `FrozenRowsCount` property.


## Freeze columns

The data grid also supports freezing the columns on the left of the view by setting the [SfDataGrid.FrozenColumnsCount](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.SfDataGrid.html#Syncfusion_SfDataGrid_SfDataGrid_FrozenColumnsCount) property. 

The following code example illustrates freezing two columns in the data grid.

{% highlight c# %}
//Setting number of columns to freeze in SfDataGrid
dataGrid.FrozenColumnsCount = 2;  
{% endhighlight %}

### Limitation

* `FrozenColumnsCount` should be less than the number of columns displayed in the view.

For example: If you have 5 columns in view, set `FrozenColumnsCount` to a maximum value of 4.

N> The row header is frozen by default and works regardless of the `FrozenColumnsCount` property.
