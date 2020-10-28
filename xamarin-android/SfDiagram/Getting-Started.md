---
title: Getting Started in Essential Xamarin.Android Diagram | Syncfusion
description: Getting started with Xamarin.Android diagram and walk through to create a demo application from the scratch.
platform: Xamarin.Android
control: SfDiagram
documentation: UG
keywords: 
---
# Getting started in Essential Xamarin.Android Diagram
This section provides a quick overview for working with Diagram for Xamarin.Android. This walkthrough demonstrates that, how to create a simple flow chart and an organization chart.

## Adding diagram reference 
Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add diagram to your project, open the NuGet package manager in Visual Studio, and search for [“Syncfusion.Xamarin.SfDiagram.Android”](https://www.nuget.org/packages/Syncfusion.Xamarin.SfDiagram.Android), and then install it. 

![Diagram reference in Xamarin.Android diagram](images/Getting-Started_img1.jpeg)

I>Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Basic building blocks of Diagram
• **Diagram-**It represents the drawing surface where all the graphical elements like nodes and connectors resides, can be used to display various types of diagrams and it is the root instance of the diagram control. A Diagram instance contains a collection of nodes and connectors to represent the  graphical diagram.
• **Nodes-**This represents the geometric shapes such as flowchart elements, network diagram elements, use case elements, etc.
• **Connectors-**These are the objects used to create link between two nodes, to represent the relationships between them in the diagram.
• **Ports-**It represents a point in the node, where the connectors can be connected. A Node can contain any number of ports.
• **Annotation-**It is a block of the text that can be displayed over a Node or Connector. Annotation is used to textually represent an object with a string that can be edited at run time.

## Creating a simple flow chart
Create a new cross platform app (Xamarin.Android) with portable class library in the Visual Studio and name the project as “GettingStarted” and refer to the above mentioned assemblies to the respective projects.
**Adding SfDiagram in Xamarin.Android**
1.Create a new blank application for Android using Visual Studio and name it as “GettingStartedDroid”. Refer the above-mentioned assemblies to the project.
Add the below code in the Main.axml to include PDF Viewer control.
{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8"?> 
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android" android:orientation="vertical" android:layout_width="match_parent" android:layout_height="match_parent"
android:id="@+id/linear_layout"> 
<Syncfusion.SfDiagram.Android.SfDiagram android:layout_width="match_parent" android:layout_height="match_parent" android:id="@+id/diagram_control" /> </LinearLayout>
{% endhighlight %}
{% endtabs %}
Please add the below code snippet in the MainActivity class
•	In the MainActivity.cs class, declare an instance of SfDiagram globally.
•	In the override method OnCreate, set the content view to Main.
{% tabs %}
{% highlight c# %}
using Syncfusion.SfDiagram.Android;
namespace GettingStarted
{
    public class MainActivity : Activity    
{
        SfDiagram diagram;
        protected override void OnCreate(Bundle bundle)
       {
               base.OnCreate(bundle);
               SetContentView(Resource.Layout.Main);
               Diagram = FindViewById<SfDiagram>(Resource.Id.diagram_control);
        }
    }
}
{% endhighlight %}
{% endtabs %}
The following code snippet illustrates the creation of Nodes and Connectors in the diagram.
{% tabs %}
{% highlight c# %}
protected override void OnCreate(Bundle bundle)
{
base.OnCreate(bundle);
// Set our view from the "main" layout resource
SetContentView(Resource.Layout.Main);
LinearLayout linearLayout = FindViewById<LinearLayout>(Resource.Id.linear_layout);
SfDiagram diagram = new SfDiagram(this);
diagram.LayoutParameters = new LayoutParams(LayoutParams.MatchParent, LayoutParams.MatchParent);
Node begin = AddNode("Begin", 300, 120, 240, 80, "begin", ShapeType.Ellipse);
Node process = AddNode("Process", 300, 280, 240, 120, "process", ShapeType.Rectangle);
Node end = AddNode("End", 380, 450, 80, 80, "end", ShapeType.Ellipse);
//Add nodes to the SfDiagram
diagram.AddNode(begin);
diagram.AddNode(process);
diagram.AddNode(end);
Connector connector1 = new Connector(this)
{
  SourceNode = begin,
  TargetNode = process,
};
Connector connector2 = new Connector(this)
{
  SourceNode = process,
  TargetNode = end,
};
//Add connectors to the SfDiagram
diagram.AddConnector(connector1);
diagram.AddConnector(connector2);
linearLayout.AddView(diagram);
}
//Create Node
public Node AddNode(string id, float offsetX, float offsetY, float width, float height, string text, ShapeType shape)
{
  Node node = new Node(this);
  node.OffsetX = offsetX;
  node.OffsetY = offsetY;
  node.Height = height;
  node.Width = width;
  node.ShapeType = shape;
  node.Style.Brush = new SolidBrush(Color.Rgb(100, 149, 237));
  node.Annotations.Add(new Annotation() { Content = text, FontSize = 18, TextBrush = new SolidBrush(Color.White) });
  return node;
}
{% endhighlight %}
{% endtabs %}
The flow chart will get displayed in the SfDiagram as follows
![Getting started demo in Xamarin.Android diagram](images/Getting-Started_img2.jpeg)

This demo project can be downloaded from the following link.
[GettingStarted_Demo](http://files2.syncfusion.com/Xamarin.Android/Samples/GettingStarted_Android_SfDiagram.zip)

## Create a simple organizational chart
SfDiagram provides support to auto-arrange the nodes based on hierarchical relation. Organization chart is an example of displaying hierarchical information.
Now, you have to create a class named “Employee” to store the employee’s information like name, designation, ID, reporting person ID, etc. Also, create a collection class that stores a collection of the employees.
{% tabs %}
{% highlight c# %}
//Employee Business Object
public class Employee
{
    public string ParentId { get; set; }
    public string Name { get; set; }
    public string Designation { get; set; }
    public int EmployeeId { get; set; }
}
//Employee Collection
public class Employees : ObservableCollection<Employee>  
{
}
{% endhighlight %}
{% endtabs %}
**Initialize Employee data**
Define Employee Information as a Collection. The below code example shows an employee array whose,
•Name is used as a unique identifier and
•ParentId is used to identify the person to whom an employee report to, in the organization.
{% tabs %}
{% highlight c# %}
//Initializes the employee collection
ObservableCollection<Employee> employees = new ObservableCollection<Employee>();
employees.Add(new Employee() { Name = "Elizabeth", EmployeeId = "1", ParentId = "", Designation = "CEO" });
employees.Add(new Employee() { Name = "Christina", EmployeeId = "2", ParentId = "1", Designation = "Manager" });
employees.Add(new Employee() { Name = "Yang", EmployeeId = "3", ParentId = "1", Designation = "Manager" });
employees.Add(new Employee() { Name = "Yoshi", EmployeeId = "4", ParentId = "2", Designation = "Team Lead" });
employees.Add(new Employee() { Name = "Philip", EmployeeId = "5", ParentId = "2", Designation = "S/w Developer" });
employees.Add(new Employee() { Name = "Roland", EmployeeId = "6", ParentId = "3", Designation = "TeamLead" });
employees.Add(new Employee() { Name = "Yvonne", EmployeeId = "7", ParentId = "3", Designation = "Testing Engineer" });
//Initializes the DataSourceSettings
diagram.DataSourceSettings = new DataSourceSettings() { DataSource = employees, Id = "EmployeeId", ParentId = "ParentId" };
//Initializes the Layout
DirectedTreeLayout treeLayout = new DirectedTreeLayout() { HorizontalSpacing = 80, VerticalSpacing = 50, TreeOrientation = TreeOrientation.TopToBottom };
diagram.LayoutManager = new LayoutManager() { Layout = treeLayout };
{% endhighlight %}
{% endtabs %}
The Employee data is displayed in the SfDiagram as follows
![Organization chart demo in Xamarin.Android diagram](images/Getting-Started_img3.jpeg)

This demo project can be downloaded from the following link.
[OrganizationalChart_Demo](http://files2.syncfusion.com/Xamarin.Android/Samples/OrganizationalChart_Android_SfDiagram.zip)
