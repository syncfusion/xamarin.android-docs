---
layout: post
title: Getting started | SfDataGrid | Xamarin.Android | Syncfusion
description: Getting started with Xamarin.Android DataGrid and walk through to create a demo application from the scratch.
platform: Xamarin.Android
control: SfDataGrid
documentation: ug
---

# Getting Started with Xamarin.Android DataGrid (SfDataGrid)

This section provides a quick overview of working with the data grid for Xamarin.Android. You will walk through the entire process of creating a real world of the data grid.

## Assembly deployment

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, {Syncfusion Essential Studio Installed location}\Essential Studio\{{ site.releaseversion }}\Xamarin\lib

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\Xamarin\lib

N> Assemblies can be found in the unzipped package location on a Mac.

## NuGet configuration

To install the required NuGet for the SfDataGrid control in the application, configure the NuGet packages of the Syncfusion components.

Refer to the following KB to configure the NuGet package of the Syncfusion components:

[How to configure package source and install Syncfusion NuGet packages in an existing project?](https://www.syncfusion.com/kb/7441/how-to-configure-package-source-and-install-syncfusion-nuget-packages-in-an-existing-project)

The following NuGet package should be installed to use the SfDataGrid control in the application

<table>
<tr>
<th> Project </th>
<th> Required package </th>
</tr>
<tr>
<td> Xamarin.Forms </td>
<td> Syncfusion.Xamarin.SfDataGrid.Android</td>
</tr>
</table>

### Adding SfDataGrid Reference

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfDataGrid to your project, open the NuGet package manager in Visual Studio, and search for [Syncfusion.Xamarin.SfDataGrid.Android](https://www.nuget.org/packages/Syncfusion.Xamarin.SfDataGrid.Android/#), and then install it.

![SfDataGrid in nuget.org](SfDataGrid_images/SfDataGrid_NuGet_Android.png)

To know more about obtaining our components, refer to this [link](https://help.syncfusion.com/xamarin-android/introduction/download-and-installation). Also, if you prefer to manually refer the assemblies instead of NuGet, refer the list of assemblies mentioned in the table below.


<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>Xamarin.Android</td>
<td>Syncfusion.Linq.Android.dll<br/>Syncfusion.SfDataGrid.Android.dll<br/>Syncfusion.GridCommon.Portable.dll<br/>Syncfusion.SfNumericTextBox.Android.dll<br/></td>
</tr>
</table>

To export the SfDataGrid to Excel and PDF formats, search for [Syncfusion.Xamarin.SfGridConverter](https://www.nuget.org/packages/Syncfusion.Xamarin.SfGridConverter.Android/) in the NuGet package manager, and then install it.

![DataGridExport in nuget.org](SfDataGrid_images/SfGridConverter_Android.png)

If you prefer to manually refer the assemblies instead of NuGet, refer the list of assemblies mentioned in the table below.

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>Xamarin.Android</td>
<td>Syncfusion.SfGridConverter.Android.dll<br/>pcl\Syncfusion.Compression.Portable.dll<br/>pcl\Syncfusion.Pdf.Portable.dll<br/>pcl\Syncfusion.XlsIO.Portable.dll<br/></td>
</tr>
</table>

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Create a simple data grid

This section explains how to create a data grid and configure it. The data grid control can be configured entirely in C# code or using designer. The following figure shows how the output will look on Android devices.

![SfDataGrid in Xamarin.Android](SfDataGrid_images/GettingStarted.png)

You can download the entire source code of this demo for Xamarin.Android from [here](https://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStarted2087929300).
 
In this walk through, you will create a new application that contains the data grid which includes the following topics:

* [Creating the project](#creating-the-project)  
* [Adding data grid in Xamarin.Android](#adding-sfdatagrid-in-xamarinandroid) 
* [Create data model](#create-datamodel-for-the-sfdatagrid)  
* [Binding data](#binding-data-to-sfdatagrid) 
* [Defining columns](#defining-columns) 
* [Sorting](#sorting) 
* [Grouping](#grouping) 
* [Selection](#selection)
* [Editing](https://help.syncfusion.com/xamarin-android/sfdatagrid/editing)

## Creating the project

Create a new Android application in Xamarin Studio or Visual Studio for Xamarin.Android.

## Adding the data grid in Xamarin.Android using designer

To add the data grid through designer, follow the steps:

1. Add a new xaml file inside the layout folder.
2. Open the newly added file and switch to designer tab. 
3. Drag the SfDataGrid control from toolbox and drop it into the designer page. Preview for SfDataGrid will be shown.
4. Open the properties window of SfDataGrid and set the required properties.

![SfDataGrid Android Previewer](SfDataGrid_images/custom_designer2_SfDataGrid_Android_Preview.gif)

### Setting the SfDataGrid properties in designer

{% tabs %}

{% highlight axml %}
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:p1="http://schemas.android.com/apk/res/android"
    xmlns:custom="http://schemas.android.com/apk/res-auto"
    p1:orientation="vertical"
    p1:layout_width="match_parent"
    p1:layout_height="wrap_content"
    p1:id="@+id/linearLayout1">
    <Syncfusion.SfDataGrid.DataPager.SfDataPager
        p1:minWidth="25px"
        p1:minHeight="25px"
        p1:id="@+id/sfDataPager1"
        p1:layout_width="match_parent"
        p1:layout_height="50.0dp"
        custom:numericButtonCount="5"
		custom:pageSize="15"
		custom:pageCount="5" />
    <Syncfusion.SfDataGrid.SfDataGrid
        p1:minWidth="25px"
        p1:minHeight="25px"
        p1:layout_width="match_parent"
        p1:layout_height="wrap_content"
        p1:id="@+id/sfDataGrid1"
		custom:allowEditing="true"
		custom:allowSorting="true"
		custom:allowResizingColumn="true"
		custom:selectionMode="single" />
</LinearLayout>


{% endhighlight %}

{% highlight c# %}
namespace Custom_Designer
{
[Activity(Label = "MainActivity", MainLauncher = true)]
	public class MainActivity : Activity
	{	
		OrderInfoRepository viewModel;
		SfDataGrid sfGrid;
		SfDataPager sfPager;
		protected override void OnCreate(Bundle savedInstanceState)
		{	
			base.OnCreate(savedInstanceState);
			SetContentView(Resource.Layout.Main);
			viewModel = new OrderInfoRepository();
			sfGrid = FindViewById<SfDataGrid>(Resource.Id.sfDataGrid1);
			sfPager = FindViewById<SfDataPager>(Resource.Id.sfDataPager1);
			sfPager.Source = viewModel.OrderInfoCollection;
			sfGrid.ItemSource = sfPager.PagedSource;
		 }
	 }
}

{% endhighlight %}

{% endtabs %}

You can download the entire source code of this demo [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Designer_Support_SfDataGrid_Android429337173).

Refer to this link to know the properties that can be configured through designer for SfDataGrid.

## Adding the data grid in Xamarin.Android using C# code

1. Add the required assembly references to the project as discussed in the [Assembly deployment](#assembly-deployment) section.

2. Import the data grid control namespace Syncfusion.SfDataGrid.

3. Create an instance of the data grid control and add it as a child to the view hosted in the activity.


{% tabs %}

{% highlight c# %}
using Syncfusion.SfDataGrid; 

[Activity (Label = "GettingStarted", MainLauncher = true)]
public class MainActivity : Activity
{
    SfDataGrid dataGrid;
    protected override void OnCreate (Bundle bundle)
    {
        base.OnCreate (bundle);
        RelativeLayout layout = (RelativeLayout)FindViewById (Resource.Id.Relative);
        dataGrid = new SfDataGrid (BaseContext);
		
		// If creating SfDataGrid instance via axml comment the above line of code and uncomment the below line of code.
		// dataGrid = FindViewById<SfDataGrid>(Resource.Id.sfDataGrid1);
		
        layout.AddView (dataGrid);
		 SetContentView (layout);
    }
}
{% endhighlight %}

{% highlight axml %}
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:p1="http://schemas.android.com/apk/res/android"
    xmlns:custom="http://schemas.android.com/apk/res-auto"
    p1:orientation="vertical"
    p1:layout_width="match_parent"
    p1:layout_height="wrap_content"
    p1:id="@+id/linearLayout1">
    <Syncfusion.SfDataGrid.SfDataGrid
        p1:minWidth="25px"
        p1:minHeight="25px"
        p1:layout_width="match_parent"
        p1:layout_height="wrap_content"
        p1:id="@+id/sfDataGrid1" />
</LinearLayout>
{% endhighlight %}
{% endtabs %}


## Create a data model for the SfDataGrid

The data grid is a data-bound control, so we must create a data model to bind it to the control. 

Create a simple data source as shown in the following code example in a new class file and save it as **OrderInfo.cs** file. 

{% highlight c# %}
public class OrderInfo
{
    private int orderID;
    private string customerID;
    private string customer;
    private string shipCity;
    private string shipCountry;

    public int OrderID {
        get { return orderID; }
        set { this.orderID = value; }
    }

    public string CustomerID {
        get { return customerID; }
        set { this.customerID = value; }
    }

    public string ShipCountry {
        get { return shipCountry; }
        set { this.shipCountry = value; }
    }

    public string Customer {
        get { return this.customer; }
        set { this.customer = value; }
    }

    public string ShipCity {
        get { return shipCity; }
        set { this.shipCity = value; }
    }

    public OrderInfo (int orderId, string customerId, string country, string customer, string shipCity)
    {
        this.OrderID = orderId;
        this.CustomerID = customerId;
        this.Customer = customer;
        this.ShipCountry = country;
        this.ShipCity = shipCity;
    }
} 
{% endhighlight %}

N> If you want your data model to respond to property changes, implement the `INotifyPropertyChanged` interface in your model class

Create a model repository class with OrderInfo collection property initialized with required number of data objects in a new class file as shown in the following code example and save it as **OrderInfoRepository.cs** file.

{% highlight c# %}
public class OrderInfoRepository
{
    private ObservableCollection<OrderInfo> orderInfo;
    public ObservableCollection<OrderInfo> OrderInfoCollection {
        get { return orderInfo; }
        set { this.orderInfo = value; }
    }

    public OrderInfoRepository ()
    {
        orderInfo = new ObservableCollection<OrderInfo> ();
        this.GenerateOrders ();
    }

    private void GenerateOrders ()
    {
        orderInfo.Add (new OrderInfo (1001, "Maria Anders", "Germany", "ALFKI", "Berlin"));
        orderInfo.Add (new OrderInfo (1002, "Ana Hardy", "Mexico", "ANATR", "Mexico D.F."));
        orderInfo.Add (new OrderInfo (1003, "Ant Fuller", "Mexico", "ANTON", "Mexico D.F."));
        orderInfo.Add (new OrderInfo (1004, "Thomas Hardy", "UK", "AROUT", "London"));
        orderInfo.Add (new OrderInfo (1005, "Tim Adams", "Sweden", "BERGS", "Berlin"));
        orderInfo.Add (new OrderInfo (1006, "Hanna Moos", "Germany", "BLAUS", "Mannheim"));
        orderInfo.Add (new OrderInfo (1007, "Andrew Fuller", "France", "BLONP", "Strasbourg"));
        orderInfo.Add (new OrderInfo (1008, "Martin King", "Spain", "BOLID", "Madrid"));
        orderInfo.Add (new OrderInfo (1009, "Lenny Lin", "France", "BONAP", "Marseille"));
        orderInfo.Add (new OrderInfo (1010, "John Carter", "Canada", "BOTTM", "Tsawassen"));
        orderInfo.Add (new OrderInfo (1011, "Lenny King", "UK", "AROUT", "London"));
        orderInfo.Add (new OrderInfo (1012, "Anne Wilson", "Germany", "BLAUS", "Mannheim"));
        orderInfo.Add (new OrderInfo (1013, "Ana Kyle", "France", "BLONP", "Strasbourg"));
        orderInfo.Add (new OrderInfo (1014, "Gina Irene", "UK", "AROUT", "London"));
    }
}
{% endhighlight %}

## Binding data to the data grid

To bind the data source of the data grid, set the [SfDataGrid.ItemsSource](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.SfDataGrid.html#Syncfusion_SfDataGrid_SfDataGrid_ItemsSource) property as follows.  

The following code example binds the collection created in the previous step to the`SfDataGrid.ItemsSource` property.


{% tabs %}
{% highlight c# %}
OrderInfoRepository viewModel = new OrderInfoRepository ();
dataGrid.ItemsSource = viewModel.OrderInfoCollection; 
//If binding data to SfDataGrid instance via axml comment the above line code and uncomment the below line code
// dataGrid = FindViewById<SfDataGrid>(Resource.Id.sfDataGrid1);
dataGrid.ItemSource = viewModel.OrderInfoCollection;
{% endhighlight %}
{% highlight axml %}
 <Syncfusion.SfDataGrid.SfDataGrid
        p1:minWidth="25px"
        p1:minHeight="25px"
        p1:layout_width="match_parent"
        p1:layout_height="wrap_content"
        p1:id="@+id/sfDataGrid1" />
{% endhighlight %}
{% endtabs %}

Now, run the application to render the following output.

![Data Virtualization in SfDataGrid for Xamarin.Android](SfDataGrid_images/Overview.png)

## Defining columns

By default, the data grid automatically creates the column for all the properties in the data source. The type of the generated column depends on the type of data in the column. When the column is auto generated, handle the [SfDataGrid.AutoGeneratingColumn](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.SfDataGrid.html) event to customize or cancel the columns before it is added to the Columns collection in the data grid.
 
Columns can also be manually defined by setting the [SfDataGrid.AutoGenerateColumns](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.SfDataGrid.html#Syncfusion_SfDataGrid_SfDataGrid_AutoGenerateColumns) property to false and by adding the [GridColumn](http://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.GridColumn.html) objects to the [SfDataGrid.Columns](http://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.GridColumn.html) collection. The following code example illustrates how this can be done. 

{% highlight c# %}
dataGrid.AutoGenerateColumns = false;

GridTextColumn orderIdColumn = new GridTextColumn ();
orderIdColumn.MappingName = "OrderID";
orderIdColumn.HeaderText = "Order ID";

GridTextColumn customerIdColumn = new GridTextColumn ();
customerIdColumn.MappingName = "CustomerID";
customerIdColumn.HeaderText = "Customer ID";

GridTextColumn customerColumn = new GridTextColumn ();
customerColumn.MappingName = "Customer";
customerColumn.HeaderText = "Customer";

GridTextColumn countryColumn = new GridTextColumn ();
countryColumn.MappingName = "ShipCountry";
countryColumn.HeaderText = "Ship Country";

dataGrid.Columns.Add (orderIdColumn);
dataGrid.Columns.Add (customerIdColumn);
dataGrid.Columns.Add (customerColumn);
dataGrid.Columns.Add (countryColumn); 
{% endhighlight %}

## Sorting

The data grid applies sorting to its data by setting the [SfDataGrid.AllowSorting](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.SfDataGrid.html#Syncfusion_SfDataGrid_SfDataGrid_AllowSorting) property to true.
 
 {% tabs %}
{% highlight c# %}
dataGrid.AllowSorting = true; 
{% endhighlight %}
{% highlight axml %}
 <Syncfusion.SfDataGrid.SfDataGrid
        p1:minWidth="25px"
        p1:minHeight="25px"
        p1:layout_width="match_parent"
        p1:layout_height="wrap_content"
        p1:id="@+id/sfDataGrid1"
		custom: allowSorting = "true" />
{% endhighlight %}
{% endtabs %}
Run the application and touch the header cell to sort the data and the following output will be displayed.
 
![Sorting in SfDataGrid for Xamarin.Android](SfDataGrid_images/Sorting.png)

You can also configure sorting by adding the column to the [SfDataGrid.SortColumnDescriptions](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.SfDataGrid.html#Syncfusion_SfDataGrid_SfDataGrid_SortColumnDescriptions) collection as follows.

{% highlight c# %}
dataGrid.SortColumnDescriptions.Add (new SortColumnDescription () { ColumnName = "CustomerID" });
{% endhighlight %}

## Grouping

The data grid allows grouping a column by adding the column to the [SfDataGrid.GroupColumnDescriptions](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.SfDataGrid.html#Syncfusion_SfDataGrid_SfDataGrid_SortColumnDescriptions) collection as follows.

{% highlight c# %}
dataGrid.GroupColumnDescriptions.Add (new GroupColumnDescription () { ColumnName = "Product" });
{% endhighlight %}

Run the application to render the following output. 

![Grouping in SfDataGrid for Xamarin.Android](SfDataGrid_images/Grouping.png)

## Selection

The data grid allows selecting the row or rows by setting the [SfDataGrid.SelectionMode](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.SfDataGrid.html#Syncfusion_SfDataGrid_SfDataGrid_SelectionMode) property. You can set the `SfDataGrid.SelectionMode` property to single, multiple, single deselect, or none. Information about the selected row or rows can be tracked using the [SfDataGrid.SelectedItem](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.SfDataGrid.html#Syncfusion_SfDataGrid_SfDataGrid_SelectedItem) and [SfDataGrid.SelectedItems](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.SfDataGrid.html#Syncfusion_SfDataGrid_SfDataGrid_SelectedItems) properties.

You can handle the selection operations with the help of the [SelectionChanging](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.SfDataGrid.html) and [SelectionChanged](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfDataGrid.SfDataGrid.html) events of the data grid.

## Loading the data grid with customized height and width

The data grid can be loaded with specific height and width inside different layouts by specifying the height and width of the data grid when adding it as a child to its parent.

The following code example illustrates how this can be done.

{% tabs %}
{% highlight c# %}
protected override void OnCreate(Bundle bundle)
{
    base.OnCreate(bundle);
    linearLayout = new LinearLayout(this);
    datagrid = new SfDataGrid(this);
    viewModel = new ViewModel();
    datagrid.ItemsSource = viewModel.OrdersInfo;
    //To place SfDataGrid at center position, padding has been set.
    linearLayout.SetPadding(80, 250, 0, 0);
    linearLayout.AddView(datagrid, 500, 500);
    SetContentView(linearLayout);
} 
{% endhighlight %}
{% highlight axml %}
<LinearLayout xmlns:p1="http://schemas.android.com/apk/res/android"
    xmlns:custom="http://schemas.android.com/apk/res-auto"
    p1:orientation="vertical"
    p1:layout_width="match_parent"
    p1:layout_height="wrap_content"
    p1:id="@+id/linearLayout1"
	p1:paddingTop="250dp"
	p1:paddingTop="80dp"
	p1:paddingTop="250dp"
	p1:paddingTop="80dp">
<Syncfusion.SfDataGrid.SfDataGrid 
	p1:minWidth = "25px"
	p1:minHeight = "25px"
	p1:layout_width="500dp"
	p1:layout_height="500dp"
	p1:id="@+id/sfDataGrid"/>
</LinearLayout>
{% endhighlight %}
{% endtabs %}
The following screenshot shows how the data grid is loaded with specific height and width.

![SfDataGrid with specific height and width](SfDataGrid_images/Loading_with specific_height_and_width.png)

## Properties configured using designer

<table>
<tr>
<th> Properties</th>
<th> Attribute name</th>
</tr>
<tr><td>AutoGenerateColumns</td> <td>autoGenerateColumns</td></tr>
<tr><td>IndentColumnWidth</td><td>indentColumnWidth</td></tr>
<tr><td>AllowResizingColumn</td><td>allowResizingColumn</td></tr>
<tr><td>ResizingMode</td><td>resizingMode</td></tr>
<tr><td>RowHeaderWidth</td><td>rowHeaderWidth</td></tr>
<tr><td>ShowRowHeader</td><td>showRowHeader</td></tr>
<tr><td>AllowSorting</td><td>allowSorting</td></tr>
<tr><td>AllowTriStateSorting</td><td>allowTriStateSorting</td></tr>
<tr><td>AllowMultiSorting</td><td>allowMultiSorting</td></tr>
<tr><td>SortTapAction</td><td>sortTapAction</td></tr>
<tr><td>GroupingMode</td><td>groupingMode</td></tr>
<tr><td>AutoExpandGroups</td><td>autoExpandGroups</td></tr>
<tr><td>AllowGroupExpandCollapse</td><td>allowGroupExpandCollapse</td></tr>
<tr><td>AllowEditing</td><td>allowEditing</td></tr>
<tr><td>EditTapAction</td><td>editTapAction</td></tr>
<tr><td>EditorSelectionBehavior</td><td>editorSelectionBehavior</td></tr>
<tr><td>SelectionMode</td><td>selectionMode</td></tr>
<tr><td>SelectedIndex</td><td>selectedIndex</td></tr>
<tr><td>ScrollingMode</td><td>scrollingMode</td></tr>
<tr><td>VerticalOverScrollMode</td><td>verticalOverScrollMode</td></tr>
<tr><td>AlternationCount</td><td>alternationCount</td></tr>
<tr><td>AllowLoadMore</td><td>allowLoadMore</td></tr>
<tr><td>LoadMoreText</td><td>loadMoreText</td></tr>
<tr><td>LoadMorePosition</td><td>loadMorePosition</td></tr>
<tr><td>AllowPullToRefresh</td><td>allowPullToRefresh</td></tr>
<tr><td>AllowDraggingColumn</td><td>allowDraggingColumn</td></tr>
<tr><td>FrozenColumnsCount</td><td>frozenColumnsCount</td></tr>
<tr><td>AllowDraggingRow</td><td>allowDraggingRow</td></tr>
<tr><td>FrozenRowsCount</td><td>frozenRowsCount</td></tr>
<tr><td>AllowSwiping</td><td>allowSwiping</td></tr>
<tr><td>MaxSwipeOffset</td><td>maxSwipeOffset</td></tr>
<tr><td>ColumnSizer</td><td>columnSizer</td></tr>
<tr><td>RowHeight</td><td>rowHeight</td></tr>
<tr><td>HeaderRowHeight</td><td>headerRowHeight</td></tr>
<tr><td>NumericButtonCount</td><td>numericButtonCount</td></tr>
<tr><td>PageSize</td><td>pageSize</td></tr>
<tr><td>PageCount</td><td>pageCount</td></tr>
<tr><td>Orientation</td><td>orientation</td></tr>
<tr><td>UseOnDemandPaging</td><td>useOnDemandPaging</td></tr>
<tr><td>NumericButtonBackground</td><td>numericButtonBackground</td></tr>
<tr><td>SelectionForeground</td><td>selectionForeground</td></tr>
</table>
