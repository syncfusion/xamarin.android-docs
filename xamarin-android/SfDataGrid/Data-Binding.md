---
layout: post
title: Data Binding | SfDataGrid | Xamarin.Android | Syncfusion
description: Learn here how to bind the data from different sources in Syncfusion Xamarin.Android DataGrid (SfDataGrid) control with more detail.
platform: Xamarin.Android
control: SfDataGrid
documentation: UG
---

# Data Binding from different sources in Xamarin.Android SfDataGrid 

The SfDataGrid is bound to an external data source to display the data. It supports the data sources such as [List](https://msdn.microsoft.com/en-us/library/6sh2ey19(v=vs.110).aspx), [ObservableCollection](https://msdn.microsoft.com/en-us/library/ms668604(v=vs.110).aspx), and so on. The [SfDataGrid.ItemsSource](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.SfDataGrid.html#Syncfusion_SfDataGrid_SfDataGrid_ItemsSource) property helps binding the SfDataGrid with the collection of objects.

To bind the data source of the SfDataGrid, set the `SfDataGrid.ItemsSource` property as follows, such that each row in the SfDataGrid would bind to an object in the data source and each column would bind to a property in the data model object.

{% highlight c# %}
OrderInfoRepository viewModel = new OrderInfoRepository ();
dataGrid.ItemsSource = viewModel.OrderInfoCollection; 
{% endhighlight %}

If the data source implements `ICollectionChanged` interface, the SfDataGrid will automatically refreshes the view when an item is added, removed, or cleared. When you add or remove an item in `ObservableCollection`, the SfDataGrid automatically refreshes the view as the `ObservableCollection` implements the [INotifyCollectionChanged](https://msdn.microsoft.com/en-us/library/system.collections.specialized.inotifycollectionchanged(v=vs.110).aspx) but, when doing the same in `List`, the SfDataGrid will not refresh the view automatically.

If the data model implements the `INotifyPropertyChanged` interface, the SfDataGrid responds to the property change at runtime to update the view.

## Binding with IEnumerable

The SfDataGrid control supports binding any collection that implements the [IEnumerable](https://msdn.microsoft.com/en-us/library/system.collections.ienumerable) interface. All the data operations such as sorting, grouping, and filtering are supported when binding collection derived from `IEnumerable`.

## Binding with DataTable

The SfDataGrid control supports binding the [DataTable](https://msdn.microsoft.com/en-us/library/system.data.datatable). The SfDataGrid control automatically refreshes the UI when binding `DataTable` as `ItemsSource` when rows are added, removed, or cleared.

The following code illustrates how to create and bind `DataTable` as `ItemsSource` to SfDataGrid.

{% highlight c# %}
// In ViewModel

public class ViewModel
{        
    public ViewModel()
    {
        SetRowsToGenerate(50);
    }
        
    private DataTable dataTable;

    public DataTable DataTable
    {
        get { return dataTable; }
        set { this.dataTable = value; }
    }

    public void SetRowsToGenerate (int count)
    {
        dataTable = new DataTable();
        dataTable.Columns.Add("Name");
        dataTable.Columns.Add("ID");

        for (int i = 1; i < count; i++)
        {
            dataTable.Rows.Add("Name" + i.ToString(),10000 + i);
        }
    }
}

// In MainActivity.cs

SfDataGrid dataGrid = new SfDataGrid(BaseContext);
ViewModel viewModel = new ViewModel();
dataGrid.ItemsSource = viewModel.DataTable;

SetContentView(dataGrid);
{% endhighlight %}

Below are the limitations when binding DataTable as `ItemsSource` to SfDataGrid.

* Custom sorting is not supported.
* [SfDataGrid.View.Filter](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Data.CollectionViewAdv.html#Syncfusion_Data_CollectionViewAdv_Filter) is not supported.
* Advanced Filtering does not support Case Sensitive filtering.
* [GridUnboundColumn.Expression](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.GridUnboundColumn.html#Syncfusion_SfDataGrid_GridUnboundColumn_Expression) is not supported. This can be achieved by using the [DataColumn](https://msdn.microsoft.com/en-us/library/System.Data.DataColumn) of DataTable by setting [DataColumn.Expression](https://msdn.microsoft.com/en-us/library/system.data.datacolumn.expression) property.
* [SfDataGrid.LiveDataUpdateMode](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Data.CollectionViewAdv.html#Syncfusion_Data_CollectionViewAdv_LiveDataUpdateMode) is not supported.
* Filtering with [TimeSpan](https://msdn.microsoft.com/en-us/library/system.timespan) values is not supported.
* Filtering with sub second components in `DateTime` values is not supported.

## Binding with dynamic data object

SfDataGrid control supports binding [dynamic data object](https://msdn.microsoft.com/en-us/library/system.dynamic). The following code illustrates how to create and bind dynamic objects as `ItemsSource` to SfDataGrid.

{% highlight c# %}
// In ViewModel

public class ViewModel
{        
    public ViewModel()
    {
        SetRowsToGenerate(50);
    }
        
    private ObservableCollection<ExpandoObject> collection;

    public ObservableCollection<ExpandoObject> Collection
    {
        get { return collection; }
        set { this.collection = value; }
    }

    public void SetRowsToGenerate (int count)
    {
        collection = new ObservableCollection<ExpandoObject>();
        for (int i = 1; i < count; i++)
        {
            dynamic obj = new ExpandoObject();
            obj.Name = "Name" + i.ToString();
            obj.ID = 10000 + i;
            collection.Add(obj);
        }
    }
}

// In MainActivity.cs

SfDataGrid dataGrid = new SfDataGrid(BaseContext);
ViewModel viewModel = new ViewModel();
dataGrid.ItemsSource = viewModel.Collection;

SetContentView(dataGrid);
{% endhighlight %}

## Binding Complex properties

SfDataGrid control supports binding Complex property to its columns. To bind the complex property to [GridColumn](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.GridColumn.html), set the complex property path to [MappingName](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.GridColumn.html#Syncfusion_SfDataGrid_GridColumn_MappingName).

{% highlight c# %}
this.dataGrid.Columns.Add(new GridTextColumn() { MappingName = "OrderID.Order" });
{% endhighlight %}

## Binding Indexer properties

SfDataGrid control supports binding an indexer property to its columns. To bind an indexer property to [GridColumn](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.GridColumn.html), set the indexer property path to [MappingName](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.GridColumn.html#Syncfusion_SfDataGrid_GridColumn_MappingName).

{% highlight c# %}
this.dataGrid.Columns.Add(new GridTextColumn() { MappingName = "CustomerID[0].Customer" });
{% endhighlight %}

## View

The data grid has the [View](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.SfDataGrid.html#Syncfusion_SfDataGrid_SfDataGrid_View) property of type [ICollectionViewAdv](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Data.CollectionViewAdv.html) interface that implements `ICollectionView` interface. The `View` is responsible for maintaining and manipulating data and other advanced operations like `Sorting`, `Grouping`, etc.

When binding Collection to the `ItemsSource` property of the SfDataGrid, `View` will be created and maintains the operations on `Data` such as `Grouping`, `Sorting`, `Insert`, `Delete`, and `Modification`.

N> The DataGrid creates different types of views derived from the `ICollectionViewAdv` interface based on `ItemsSource`.

I> `View` related properties can be used only after creating the `SfDataGrid` view. Hence, changes related to view can be done in `SfDataGrid.GridViewCreated` or `SfDataGrid.GridLoaded` event or at runtime only.

The following property is associated with `View`.

### LiveDataUpdateMode

The SfDataGrid supports updating the view during data manipulation operations and property changes using [LiveDataUpdateMode](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Data.LiveDataUpdateMode.html). It allows customizing when to update the view based on the `SfDataGrid.View.LiveDataUpdateMode` property.

<table>
<tr>
<th>LiveDataUpdateMode</th>
<th>Description</th>
</tr>
<tr>
<td>Default</td>
<td>Data operations are not updated. </td>
</tr>
<tr>
<td>AllowSummaryUpdate</td>
<td>Summaries are updated during data manipulation change.</td>
</tr>
<tr>
<td>AllowDataShaping</td>
<td>DataOperations like sorting, grouping, and filtering are updated during data manipulation change.</td>
</tr>
</table>

{% highlight c# %}
dataGrid.GridViewCreated += DataGrid_GridViewCreated;
private void DataGrid_GridViewCreated(object sender, GridViewCreatedEventArgs e)
{
    dataGrid.View.LiveDataUpdateMode = LiveDataUpdateMode.Default;
}
{% endhighlight %}

The following events are associated with `View`.

### RecordPropertyChanged

The [RecordPropertyChanged ](https://help.syncfusion.com/cr/xamarin-android/) event is raised when the `DataModel` property value is changed, if the `DataModel` implements the `INotifyPropertyChanged` interface. The event receives with two arguments namely, sender that handles the `DataModel`, and [PropertyChangedEventArgs](http://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.ComponentModel.PropertyChangedEventArgs)&rd=true) as argument.

`PropertyChangedEventArgs` has the following property:

* [PropertyName](https://msdn.microsoft.com/en-us/library/system.componentmodel.propertychangedeventargs.propertyname): It denotes the `PropertyName` of the changed value.

### CollectionChanged

The [CollectionChanged ](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Data.CollectionViewAdv.html) event is raised whenever changes occur in `Records or DisplayElements` collection. The event receives two arguments namely, sender that handles `View` object, and [NotifyCollectionChangedEventArgs](http://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs)&rd=true) as argument.

`NotifyCollectionChangedEventArgs` has the following properties:

* [Action](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.Action)&rd=true): It contains the current action. (i.e.) `Add`, `Remove`, `Move`, `Replace`, `Reset`.
* [NewItems](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.NewItems)&rd=true): It contains the list of new items involved in the change.
* [OldItems](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldItems)&rd=true): It contains the list of old items affected by the `Action`.
* [NewStartingIndex](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.NewStartingIndex)&rd=true): It contains the index at which the change occurred.
* [OldStartingIndex](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex)&rd=true): It contains the index at which the `Action` occurred.

### SourceCollectionChanged

The [SourceCollectionChanged ](https://help.syncfusion.com/cr/xamarin-android/) event is raised when you make changes in `SourceCollection` for example, add or remove the collection. The event receives two arguments namely, sender that handles `GridQueryableCollectionViewWrapper` object, and `NotifyCollectionChangedEventArgs` as argument.

`NotifyCollectionChangedEventArgs` has the following properties:

* [Action](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.Action)&rd=true): It contains the current action. (i.e.) `Add`, `Remove`, `Move`, `Replace`, `Reset`.
* [NewItems](http://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.NewItems)&rd=true): It contains the list of new items involved in the change.
* [OldItems](http://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldItems)&rd=true): It contains the list of old items affected by the `Action`.
* [NewStartingIndex](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.NewStartingIndex)&rd=true): It contains the index at which the change occurred.
* [OldStartingIndex](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex)&rd=true): It contains the index at which the `Action` occurred.

The following methods are associated with `View` to defer refresh the view:
<table>
<tr>
<th>
Method Name
</th>
<th>
Description
</th>
</tr>
<tr>
<td>
DeferRefresh
</td>
<td>
Enter the defer cycle to perform all data operations in view and update once.
</td>
</tr>
<tr>
<td>
BeginEdit & EndEdit
</td>
<td>
When BeginEdit method is called it suspends all the updates until EndEdit method is called. You can suspend and resume all the operations in these methods and update the view at once.
</td>
</tr>
</table>

### Data virtualization

The SfDataGrid allows loading large amounts of data in less time by setting SfDataGrid.EnableDataVirtualization property to true.

To set the EnableDataVirtualization property, follow the code example.

{% highlight c# %}
datagrid.EnableDataVirtualization = true;
{% endhighlight %}
