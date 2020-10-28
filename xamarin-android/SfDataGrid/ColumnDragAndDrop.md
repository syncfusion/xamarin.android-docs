---
layout: post
title: Column Drag and Drop | SfDataGrid | Xamarin | Syncfusion
description: How to enable and perform column drag and drop operation and its customization.
platform: Xamarin.Android
control: SfDataGrid
documentation: UG
---

# Column Drag and Drop

The SfDataGrid allows dragging and dropping a column header by setting the [SfDataGrid.AllowDraggingColumn](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.SfDataGrid.html#Syncfusion_SfDataGrid_SfDataGrid_AllowDraggingColumn) property to `true`. Drag view is displayed when dragging a column header. The drag and drop operations can be handled using the [SfDataGrid QueryColumnDragging](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.SfDataGrid.html) event. 

The following code example illustrates how to enable column drag and drop in the SfDataGrid.

{% tabs %}
{% highlight c# %}
sfGrid.AllowDraggingColumn = true;
{% endhighlight %}
{% endtabs %}

![Column drag and drop](SfDataGrid_images/ColumnDraganddrop.gif)

## Events in column drag and drop

The `QueryColumnDragging` event is fired upon dragging a column and will be continuously fired till the dragging ends. By handing the `SfDataGrid.QueryColumnDragging ` event, you can also cancel the dragging of a particular column header.

The `QueryColumnDragging` event provides following properties in [QueryColumnDraggingEventArgs](http://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.QueryColumnDraggingEventArgs.html):

* [From](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.QueryColumnDraggingEventArgs.html#Syncfusion_SfDataGrid_QueryColumnDraggingEventArgs_From): Returns the index of the dragging column.
* [To](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.QueryColumnDraggingEventArgs.html#Syncfusion_SfDataGrid_QueryColumnDraggingEventArgs_To): Returns the dragging index where you try to drop the column.
* [Reason](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.QueryColumnDraggingEventArgs.html#Syncfusion_SfDataGrid_QueryColumnDraggingEventArgs_Reason): Returns column dragging details as `QueryColumnDraggingReason`.
* [DraggingPosition](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.QueryColumnDraggingEventArgs.html#Syncfusion_SfDataGrid_QueryColumnDraggingEventArgs_DraggingPosition): Returns the positions of the drag view during column drag and drop operations.
* [CanAutoScroll](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.QueryColumnDraggingEventArgs.html#Syncfusion_SfDataGrid_QueryColumnDraggingEventArgs_CanAutoScroll): Returns whether auto-scrolling should happen when column drag view reaches the left or right ends of the `SfDataGrid`.
* [Cancel](https://msdn.microsoft.com/en-us/library/system.componentmodel.canceleventargs_properties(v=vs.110).aspx): Returns the Boolean property to cancel the event.

### Cancel dragging for a particular column 

Dragging of a particular column can be canceled using [QueryColumnDraggingReason](http://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.QueryColumnDraggingReason.html) argument of the `QueryColumnDragging` event handler.

{% tabs %}
{% highlight c# %}

this.SfGrid.QueryColumnDragging += SfGrid_QueryColumnDragging;

private void SfGrid_QueryColumnDragging(object sender, QueryColumnDraggingEventArgs e)
{
    //e.From returns the index of the dragged column.
    //e.Reason returns the dragging status of the column.
    if (e.From == 1 && e.Reason == QueryColumnDraggingReason.DragStarted)
        e.Cancel = true;
}

{% endhighlight %}
{% endtabs %}

### Cancel dropping when dragging over particular columns

Dropping when dragging over particular columns can be canceled using `QueryColumnDraggingReason` argument of the `QueryColumnDragging` event handler.

{% tabs %}
{% highlight c# %}

this.SfGrid.QueryColumnDragging += SfGrid_QueryColumnDragging;

private void SfGrid_QueryColumnDragging(object sender, QueryColumnDraggingEventArgs e)
{
    //e.To returns the index of the current column.
    //e.Reason returns the dragging status of the column.
    if ((e.To > 5 || e.To < 10) &&
    (e.Reason == QueryColumnDraggingReason.DragEnded || e.Reason == QueryColumnDraggingReason.Dragging))
        e.Cancel = true;
} 

{% endhighlight %}
{% endtabs %}

### Cancel dropping of particular column

Dropping of a particular column can be canceled using `QueryColumnDraggingReason` argument of the `QueryColumnDragging` event handler.

{% tabs %}
{% highlight c# %}

this.SfGrid.QueryColumnDragging += SfGrid_QueryColumnDragging;

private void SfGrid_QueryColumnDragging(object sender, QueryColumnDraggingEventArgs e)
{
    //e.From returns the index of the dragged column.
    //e.Reason returns the dragging status of the column.
    if (e.From == 1 && e.Reason == QueryColumnDraggingReason.DragEnded)
        e.Cancel = true;
}

{% endhighlight %}
{% endtabs %}

## Cancel dropping at a particular position

Dropping at a particular position can be canceled using `QueryColumnDraggingReason` argument of the `QueryColumnDragging` event handler.

{% tabs %}
{% highlight c# %}

this.SfGrid.QueryColumnDragging += SfGrid_QueryColumnDragging;

private void SfGrid_QueryColumnDragging(object sender, QueryColumnDraggingEventArgs e)
{
    //e.To returns the index of the current column.
    //e.Reason returns the dragging status of the column.
    if ((e.To == 5 || e.To == 7) && e.Reason == QueryColumnDraggingReason.DragEnded)
        e.Cancel = true;
}

{% endhighlight %}
{% endtabs %}

## Cancel dropping of a particular column in a position

Dropping of a particular column in a position can be canceled using `QueryColumnDraggingReason` and `Position` arguments of the `QueryColumnDragging` event handler. 

{% tabs %}
{% highlight c# %}

this.SfGrid.QueryColumnDragging += SfGrid_QueryColumnDragging;

private void SfGrid_QueryColumnDragging(object sender, QueryColumnDraggingEventArgs e)
{
    //e.To returns the index of the current column.
    //e.DraggingPosition returns the x and y position of the current column
     if (e.DraggingPosition == new Point(100,100) && e.Reason == QueryColumnDraggingReason.DragEnded)
                e.Cancel = true;
}

{% endhighlight %}
{% endtabs %}

## Cancel drag and drop between frozen and non-frozen columns

### Cancel dragging between frozen and non-frozen columns

Dragging between frozen and non-frozen columns can be canceled using `QueryColumnDraggingReason` and `From` arguments of the `QueryColumnDragging` event handler by checking whether the value of `From` argument is a frozen column index. 

{% tabs %}
{% highlight c# %}

SfGrid.FrozenColumnsCount = 2;

this.SfGrid.QueryColumnDragging += SfGrid_QueryColumnDragging;

private void SfGrid_QueryColumnDragging(object sender, QueryColumnDraggingEventArgs e)
{
    //e.From returns the index of the dragged column.
    //e.To returns the index of the current column.
      if (e.From < 2 && e.Reason == QueryColumnDraggingReason.DragStarted)
        e.Cancel = true;
}

{% endhighlight %}
{% endtabs %}

### Cancel dropping between frozen and non-frozen columns

Dropping between frozen and non-frozen columns can be canceled using `QueryColumnDraggingReason` and `From` arguments of the `QueryColumnDragging` event handler by checking whether the `e.From` value is a frozen column index.

{% tabs %}
{% highlight c# %}

SfGrid.FrozenColumnsCount = 2;

this.SfGrid.QueryColumnDragging += SfGrid_QueryColumnDragging;

private void SfGrid_QueryColumnDragging(object sender, QueryColumnDraggingEventArgs e)
{
    //e.From returns the index of the dragged column.
    //e.To returns the index of the current column.
      if (e.From < 2 && e.Reason == QueryColumnDraggingReason.DragEnded)
        e.Cancel = true;
}

{% endhighlight %}
{% endtabs %}

## Customize column drag and drop indicators

The SfDataGrid allows customizing the column drag and drop indicators by writing a custom grid style, deriving from [DataGridStyle](http://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.DataGridStyle.html) and assigning it to the [SfDataGrid.GridStyle](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.SfDataGrid.html#Syncfusion_SfDataGrid_SfDataGrid_GridStyle) property.

{% tabs %}
{% highlight c#%}

dataGrid.GridStyle = new CustomGridStyle();

{% endhighlight %}

{% highlight c#%}
// Custom style class
public class CustomGridStyle : DataGridStyle
{
    public CustomGridStyle()
    {     
    }
    public override int GetColumnDragDownIndicator()
    {
        return Resource.Drawable.GreenDown;
    }
    public override int GetColumnDragUpIndicator()
    {
        return Resource.Drawable.GreenUp;
    }
}
{% endhighlight %}
{% endtabs %}

![Customize column indicator](SfDataGrid_images/CustomizedIndicator_Column.jpg)

## Cancel auto scrolling

Horizontal auto-scrolling of the `SfDataGrid` during column drag and drop can be canceled using `CanAutoScroll` argument of the `QueryColumnDragging` event handler.

{% tabs %}
{% highlight c# %}

this.SfGrid.QueryColumnDragging += SfGrid_QueryColumnDragging;

private void SfGrid_QueryColumnDragging(object sender, QueryColumnDraggingEventArgs e)
{  
    // Disable scroll while dragging and dropping the columns.   
    e.CanAutoScroll = false;
}

{% endhighlight %}
{% endtabs %}
