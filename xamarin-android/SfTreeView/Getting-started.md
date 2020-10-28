---
layout: post
title: Getting Started with TreeView for Xamarin.Android | Syncfusion
description: The user guide explains needed references, adding control to the app, binding data, etc. with demo app.
platform: Xamarin.Android
control: SfTreeView
documentation: ug
---

# Getting Started with Xamarin.Android TreeView (SfTreeView)

This section provides a quick overview of working with the TreeView for Xamarin.Android. Walk through the entire process of creating an app with TreeView.

## Assembly Deployment

After installing Essential Studio for Xamarin, you can find all the required assemblies in the {Syncfusion Essential Studio Installed location}\Essential Studio\{{ site.releaseversion }}\Xamarin\lib installation folder.

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\Xamarin\lib

Refer [control dependencies](https://help.syncfusion.com/xamarin-android/introduction/controldependencies#sftreeview) section to get the list of assemblies or NuGet package needs to be added as reference to use the TreeView control in any application.

N> Assemblies can be found in an unzipped package location in Mac.

## NuGet configuration

To install the required NuGet for the TreeView control in the application, configure the NuGet packages of the Syncfusion components.

Refer to the following KB to configure the NuGet package of the Syncfusion components:

[How to configure package source and install Syncfusion NuGet packages in an existing project?](https://www.syncfusion.com/kb/7441/how-to-configure-package-source-and-install-syncfusion-nuget-packages-in-an-existing-project)

The following NuGet package should be installed to use the TreeView control in the application

<table>
<tr>
<th> Project </th>
<th> Required package </th>
</tr>
<tr>
<td> Xamarin.Android </td>
<td> Syncfusion.Xamarin.TreeView.Android</td>
</tr>
</table>

### Adding TreeView Reference

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add TreeView to your project, open the NuGet package manager in Visual Studio, and search for [Syncfusion.Xamarin.SfTreeView.Android](https://www.nuget.org/packages/Syncfusion.Xamarin.SfTreeView.Android/), and then install it. 

![Add TreeView in Xamarin Android](Images/TreeView_Add.png)

To know more about obtaining our components, refer to these links: [Mac](https://help.syncfusion.com/xamarin-android/introduction/download-and-installation/mac) and [Windows](https://help.syncfusion.com/xamarin-android/introduction/download-and-installation/windows). Also, if you prefer to manually refer the assemblies instead of NuGet, refer to this [link](https://help.syncfusion.com/xamarin-android/introduction/control-dependencies#sftreeview) to know about the dependent assemblies for TreeView or refer the list of assemblies mentioned in the table below.

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>Xamarin.Android</td>
<td>Syncfusion.SfTreeView.Android.dll<br/>Syncfusion.GridCommon.Portable.dll<br/></td>
</tr>
</table>

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also must include a license key in your projects. Please refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Create a simple tree view

This section explains how to create a TreeView and configure it. The TreeView control can be configured entirely in C# code or using designer. The following figure shows how the output will look on Android devices.

![Create TreeView in Xamarin Android](Images/TreeView_Templating.png)

You can download the entire source code of this demo for Xamarin.Android from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStartedBound1294397808).

In this walk through, you will create a new application with the TreeView that includes the following topics:

* [Creating the project](#creating-the-project)
* [Adding the TreeView in Xamarin.Android using designer](#adding-the-treeview-in-xamarin.android-using-designer)
* [Adding the TreeView in Xamarin.Android using C# code](#adding-the-treeview-in-xamarin.android-using-c#-code) 
* [Populating Nodes without data source - Unbound Mode](#populating-nodes-without-data-source---unbound-mode) 
* [Creating Data Model](#creating-data-model)  
* [Bind to a hierarchical data source - Bound Mode](#bind-to-a-hierarchical-data-source---bound-mode)
* [Creating Hierarchical Data Model](#creating-hierarchical-data-model-for-the-tree-view)
* [Bind to a Hierarchy Property Descriptors data source - Bound Mode](#bind-to-a-hierarchy-Property-descriptors-data-source---bound-mode)
* [Defining a adapter to expander and content view](#defining-a-adapter-to-expander-and-content-view)
* [Interacting with tree view](#interacting-with-treeview)
* [Selection](#selection)

## Creating the Project

Create a new Android application in Xamarin Studio or Visual Studio for Xamarin.Android.

## Adding the TreeView in Xamarin.Android using designer

To add the TreeView through designer, follow the steps:

1. Add a new axml file inside the layout folder.
2. Open the newly added file and switch to designer tab. 
3. Drag the TreeView control from toolbox and drop it into the designer page. Preview for TreeView will be shown.
4. Open the properties window of TreeView and set the required properties.

![Xamarin Android TreeView Designer Previewer](Images/TreeView_Designer.png)

### Setting the TreeView properties in designer

{% tabs %}
{% highlight axml %}
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
	xmlns:android="http://schemas.android.com/apk/res/android"
	xmlns:app="http://schemas.android.com/apk/res-auto"
	xmlns:tools="http://schemas.android.com/tools"
	android:layout_width="match_parent"
	android:layout_height="match_parent"
	android:minWidth="25px"
	android:minHeight="25px">
	<Syncfusion.Android.TreeView.SfTreeView
		android:minWidth="25px"
		android:minHeight="25px"
		android:layout_width="match_parent"
		android:layout_height="wrap_content"
		android:id="@+id/sfTreeView1" />
</LinearLayout>
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
public class MainActivity : Activity
{	
	OrderInfoRepository viewModel;
	SfTreeView treeView;
	protected override void OnCreate(Bundle savedInstanceState)
	{	
		base.OnCreate(savedInstanceState);
       	SetContentView(Resource.Layout.Main);
		treeView = FindViewById<SfTreeView>(Resource.Id.sfTreeView1);
	}
}

{% endhighlight %}
{% endtabs %}

![Xamarin Android TreeView Designer Properties](Images/TreeView_Properties.png)

You can download the entire source code of this demo [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStartedBound1294397808).

Refer to this link to know the properties that can be configured through designer for TreeView.

## Adding the TreeView in Xamarin.Android using C# code

To add the treeview to your application, follow the steps:

1. Add required assemblies as discussed in assembly deployment section.
2. Import the `SfTreeView` namespace Syncfusion.Android.TreeView
3. Create an instance of tree view control.

{% tabs %}
{% highlight c# %}
using Syncfusion.Android.TreeView;

protected override void OnCreate(Bundle savedInstanceState)
{
    base.OnCreate(savedInstanceState);
    // Set our view from the "main" layout resource
    SetContentView(Resource.Layout.activity_main);
	LinearLayout layout = FindViewById<LinearLayout>(Resource.Id.linearLayout1);
    SfTreeView treeView = new SfTreeView(layout.Context);
    layout.AddView(treeView);
}
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight axml %}
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
		android:id="@+id/linearLayout1" >
</LinearLayout>
{% endhighlight %}
{% endtabs %}

## Populating Nodes without data source - Unbound Mode

You can create and manage the [TreeViewNode](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.TreeView.Engine.TreeViewNode.html) objects by yourself to display the data in a hierarchical view. To create a tree view, you use a `TreeView` control and a hierarchy of `TreeViewNode` objects. You create the node hierarchy by adding one or more root nodes to the TreeView control’s [Nodes](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_Nodes) collection. Each `TreeViewNode` can then have more nodes added to its Children collection. You can nest tree view nodes to whatever depth you require.

>**Important** 
`ItemsSource` is an alternative mechanism to `Nodes` for putting content into the TreeView control. You cannot set both `ItemsSource` and `Nodes` at the same time. When you use `ItemsSource`, nodes created for you internally, but you cannot access them from `Nodes` property.

{% tabs %}
{% highlight axml %}
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
	android:id="@+id/linearLayout1" >
	<Syncfusion.Android.TreeView.SfTreeView
		android:minWidth="25px"
		android:minHeight="25px"
		android:layout_width="wrap_content"
		android:layout_height="wrap_content"
		android:id="@+id/sfTreeView1" />
</LinearLayout>
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
using Syncfusion.Android.TreeView;
using Syncfusion.TreeView.Engine;

protected override void OnCreate(Bundle savedInstanceState)
{
    base.OnCreate(savedInstanceState);
    // Set our view from the "main" layout resource
    SetContentView(Resource.Layout.activity_main);

    var treeView = FindViewById<SfTreeView>(Resource.Id.sfTreeView1);

    var australia = new TreeViewNode() { Content = "Australia", IsExpanded = true };
    var _NSW = new TreeViewNode() { Content = "New South Wales" };
    _NSW.ChildNodes.Add(new TreeViewNode() { Content = "Sydney" });
    australia.ChildNodes.Add(_NSW);
          
    var usa = new TreeViewNode() { Content = "United States of America", IsExpanded = true };
    var newYork = new TreeViewNode() { Content = "New York" };
    var california = new TreeViewNode() { Content = "California" };
    california.ChildNodes.Add(new TreeViewNode() { Content = "San Francisco" });
    usa.ChildNodes.Add(newYork);
    usa.ChildNodes.Add(california);
          
    treeView.Nodes.Add(australia);
    treeView.Nodes.Add(usa);
}
{% endhighlight %}
{% endtabs %}

Now, run the application to render the below output:

![Xamarin Android TreeView Unbound Mode](Images/TreeView_UnBound.png)

You can also download the entire source code of this demo from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStartedUnbound1093615327).

## Creating Data Model

Create a data model to bind it to the control. 

Create a simple data source as shown in the following code example in a new class file, and save it as FileManager.cs file: 

{% tabs %}
{% highlight c# %}
public class FileManager : INotifyPropertyChanged
{
   private string fileName;
   private int imageIcon;
   private ObservableCollection<FileManager> subFiles;

   public ObservableCollection<FileManager> SubFiles
   {
       get
       {
            return subFiles;
       }

        set
       {
            subFiles = value;
            RaisedOnPropertyChanged("SubFiles");
       }
    }

    public string FileName
    {
        get
        {
            return fileName;
        }

        set
        {
            fileName = value;
            RaisedOnPropertyChanged("FileName");
        }
    }

    public int ImageIcon
    {
        get
        {
            return imageIcon;
        }

        set
        {
            imageIcon = value;
            RaisedOnPropertyChanged("ImageIcon");
        }
    }

    public FileManager()
    {
    }

    public event PropertyChangedEventHandler PropertyChanged;

    public void RaisedOnPropertyChanged(string propertyName)
    {
        if (PropertyChanged != null)
        {
            PropertyChanged(this, new PropertyChangedEventArgs(propertyName));
        }
    }
}
{% endhighlight %}
{% endtabs %}

N> If you want your data model to respond to property changes, then implement `INotifyPropertyChanged` interface in your model class.

Create a model repository class with ImageNodeInfo collection property initialized with required number of data objects in a new class file as shown in the following code example, and save it as FileManagerViewModel.cs file:

{% tabs %}
{% highlight c# %}
public class FileManagerViewModel
{
    public ObservableCollection<FileManager> Folders { get; set; }

    public FileManagerViewModel()
    {
        GenerateFiles();
    }

    private void GenerateFiles()
    {
        var doc = new FileManager() { FileName = "Documents", ImageIcon = Resource.Drawable.treeview_folder };
        var download = new FileManager() { FileName = "Downloads", ImageIcon = Resource.Drawable.treeview_folder };
        var mp3 = new FileManager() { FileName = "Music", ImageIcon = Resource.Drawable.treeview_folder };
        var pictures = new FileManager() { FileName = "Pictures", ImageIcon = Resource.Drawable.treeview_folder };
        var video = new FileManager() { FileName = "Videos", ImageIcon = Resource.Drawable.treeview_folder };

        var pollution = new FileManager() { FileName = "Environmental Pollution.docx", ImageIcon = Resource.Drawable.treeview_word };
        var globalWarming = new FileManager() { FileName = "Global Warming.ppt", ImageIcon = Resource.Drawable.treeview_ppt };
        var sanitation = new FileManager() { FileName = "Sanitation.docx", ImageIcon = Resource.Drawable.treeview_word };
        var socialNetwork = new FileManager() { FileName = "Social Network.pdf", ImageIcon = Resource.Drawable.treeview_pdf };
        var youthEmpower = new FileManager() { FileName = "Youth Empowerment.pdf", ImageIcon = Resource.Drawable.treeview_pdf };

        var game = new FileManager() { FileName = "Game.exe", ImageIcon = Resource.Drawable.treeview_exe };
        var tutorials = new FileManager() { FileName = "Tutorials.zip", ImageIcon = Resource.Drawable.treeview_zip };
        var typescript = new FileManager() { FileName = "TypeScript.7z", ImageIcon = Resource.Drawable.treeview_zip };
        var uiGuide = new FileManager() { FileName = "UI-Guide.pdf", ImageIcon = Resource.Drawable.treeview_pdf };

        var song = new FileManager() { FileName = "Goutiest", ImageIcon = Resource.Drawable.treeview_mp3 };

        var camera = new FileManager() { FileName = "Camera Roll", ImageIcon = Resource.Drawable.treeview_folder };
        var stone = new FileManager() { FileName = "Stone.jpg", ImageIcon = Resource.Drawable.treeview_png };
        var wind = new FileManager() { FileName = "Wind.jpg", ImageIcon = Resource.Drawable.treeview_png };

        var img0 = new FileManager() { FileName = "WIN_20160726_094117.JPG", ImageIcon = Resource.Drawable.treeview_img0 };
        var img1 = new FileManager() { FileName = "WIN_20160726_094118.JPG", ImageIcon = Resource.Drawable.treeview_img1 };

        var video0 = new FileManager() { FileName = "Naturals.mp4", ImageIcon = Resource.Drawable.treeview_video };
        var video1 = new FileManager() { FileName = "Wild.mpg", ImageIcon = Resource.Drawable.treeview_video };

      doc.SubFiles = new ObservableCollection<FileManager>
      {
         pollution,
         globalWarming,
         sanitation,
         socialNetwork,
         youthEmpower
      };

      download.SubFiles = new ObservableCollection<FileManager>
      {
         game,
         tutorials,
         typescript,
         uiGuide
      };

      mp3.SubFiles = new ObservableCollection<FileManager>
      {
         song
      };

      pictures.SubFiles = new ObservableCollection<FileManager>
      {
         camera,
         stone,
         wind
      };
      
      camera.SubFiles = new ObservableCollection<FileManager>
      {
         img0,
         img1
      };

      video.SubFiles = new ObservableCollection<FileManager>
      {
         video0,
         video1
      };

      nodeImageInfo.Add(doc);
      nodeImageInfo.Add(download);
      nodeImageInfo.Add(mp3);
      nodeImageInfo.Add(pictures);
      nodeImageInfo.Add(video);
      imageNodeInfo = nodeImageInfo;
  }
}
{% endhighlight %}
{% endtabs %}

## Bind to a hierarchical data source - Bound Mode

You can create a tree view by binding the [ItemsSource](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_ItemsSource) to a hierarchical data source.  And set the child object name to the [ChildPropertyName](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_ChildPropertyName) property.

{% tabs %}
{% highlight c# %}
using Syncfusion.Android.TreeView;
using Syncfusion.TreeView.Engine;

protected override void OnCreate(Bundle savedInstanceState)
{
    base.OnCreate(savedInstanceState);
    // Set our view from the "main" layout resource
    SetContentView(Resource.Layout.activity_main);
    SfTreeView treeView = FindViewById<SfTreeView>(Resource.Id.sfTreeView1);
    FileManagerViewModel viewModel = new FileManagerViewModel();
    treeView.ChildPropertyName = "SubFiles";
    treeView.ItemsSource = viewModel.Folders;
    treeView.Adapter = new NodeImageAdapter();
}
{% endhighlight %}
{% endtabs %}

## Creating Hierarchical Data Model for the tree view

Create a hierarchical data model to bind it to the control. 

Create a simple hierarchical  data source as shown in the following code example in a new class file, and save it as FileManager.cs file: 

{% tabs %}
{% highlight c# %}
public class Folder : INotifyPropertyChanged
{
    private string fileName;
    private ImageSource imageIcon;
    private ObservableCollection<File> files;

    public Folder()
    {
    }

    public ObservableCollection<File> Files
    {
        get { return files; }
        set
        {
            files = value;
            RaisedOnPropertyChanged("SubFiles");
        }
    }

    public string FileName
    {
        get { return fileName; }
        set
        {
            fileName = value;
            RaisedOnPropertyChanged("FileName");
        }
    }

    public ImageSource ImageIcon
    {
        get { return imageIcon; }
        set
        {
            imageIcon = value;
            RaisedOnPropertyChanged("ImageIcon");
        }
    }

    public event PropertyChangedEventHandler PropertyChanged;

    public void RaisedOnPropertyChanged(string _PropertyName)
    {
        if (PropertyChanged != null)
        {
            PropertyChanged(this, new PropertyChangedEventArgs(_PropertyName));
        }
    }
}

public class File : INotifyPropertyChanged
{
    private string fileName;
    private ImageSource imageIcon;
    private ObservableCollection<SubFile> subFiles;

    public File()
    {
    }

    public ObservableCollection<SubFile> SubFiles
    {
        get { return subFiles; }
        set
        {
            subFiles = value;
            RaisedOnPropertyChanged("SubFiles");
        }
    }

    public string FileName
    {
        get { return fileName; }
        set
        {
            fileName = value;
            RaisedOnPropertyChanged("FileName");
        }
    }

    public ImageSource ImageIcon
    {
        get { return imageIcon; }
        set
        {
            imageIcon = value;
            RaisedOnPropertyChanged("ImageIcon");
        }
    }

    public event PropertyChangedEventHandler PropertyChanged;

    public void RaisedOnPropertyChanged(string _PropertyName)
    {
        if (PropertyChanged != null)
        {
            PropertyChanged(this, new PropertyChangedEventArgs(_PropertyName));
        }
    }
}


public class SubFile : INotifyPropertyChanged
{
    private string fileName;
    private ImageSource imageIcon;

    public SubFile()
    {
    }

    public string FileName
    {
        get { return fileName; }
        set
        {
            fileName = value;
            RaisedOnPropertyChanged("FolderName");
        }
    }

    public ImageSource ImageIcon
    {
        get { return imageIcon; }
        set
        {
            imageIcon = value;
            RaisedOnPropertyChanged("ImageIcon");
        }
    }

    public event PropertyChangedEventHandler PropertyChanged;

    public void RaisedOnPropertyChanged(string _PropertyName)
    {
        if (PropertyChanged != null)
        {
            PropertyChanged(this, new PropertyChangedEventArgs(_PropertyName));
        }
    }
}
{% endhighlight %}
{% endtabs %}

N> If you want your hierarchical data model to respond to property changes, then implement `INotifyPropertyChanged` interface in your model class.

Create a model repository class with ImageNodeInfo collection property initialized with required number of data objects in a new class file as shown in the following code example, and save it as FileManagerViewModel.cs file:

{% tabs %}
{% highlight c# %}
public class FileManagerViewModel
{
    public ObservableCollection<Folder> Folders { get; set; }

    public ObservableCollection<File> Files { get; set; }

    public ObservableCollection<SubFile> SubFiles { get; set; }

    public FileManagerViewModel()
    {
        this.Folders = GetFiles();
    }

    private ObservableCollection<Folder> GetFiles()
    {
        var nodeImageInfo = new ObservableCollection<Folder>();
        Assembly assembly = typeof(NodeWithImage).GetTypeInfo().Assembly;

        var doc = new Folder() { FileName = "Documents", ImageIcon = ImageSource.FromResource("SampleBrowser.SfTreeView.Icons.NodeWithImage.treeview_folder.png", assembly) };
        var download = new Folder() { FileName = "Downloads", ImageIcon = ImageSource.FromResource("SampleBrowser.SfTreeView.Icons.NodeWithImage.treeview_folder.png", assembly) };
        var mp3 = new Folder() { FileName = "Music", ImageIcon = ImageSource.FromResource("SampleBrowser.SfTreeView.Icons.NodeWithImage.treeview_folder.png", assembly) };
        var pictures = new Folder() { FileName = "Pictures", ImageIcon = ImageSource.FromResource("SampleBrowser.SfTreeView.Icons.NodeWithImage.treeview_folder.png", assembly) };
        var video = new Folder() { FileName = "Videos", ImageIcon = ImageSource.FromResource("SampleBrowser.SfTreeView.Icons.NodeWithImage.treeview_folder.png", assembly) };

        var pollution = new File() { FileName = "Environmental Pollution.docx", ImageIcon = ImageSource.FromResource("SampleBrowser.SfTreeView.Icons.NodeWithImage.treeview_word.png", assembly) };
        var globalWarming = new File() { FileName = "Global Warming.ppt", ImageIcon = ImageSource.FromResource("SampleBrowser.SfTreeView.Icons.NodeWithImage.treeview_ppt.png", assembly) };
        var sanitation = new File() { FileName = "Sanitation.docx", ImageIcon = ImageSource.FromResource("SampleBrowser.SfTreeView.Icons.NodeWithImage.treeview_word.png", assembly) };
        var socialNetwork = new File() { FileName = "Social Network.pdf", ImageIcon = ImageSource.FromResource("SampleBrowser.SfTreeView.Icons.NodeWithImage.treeview_pdf.png", assembly) };
        var youthEmpower = new File() { FileName = "Youth Empowerment.pdf", ImageIcon = ImageSource.FromResource("SampleBrowser.SfTreeView.Icons.NodeWithImage.treeview_pdf.png", assembly) };

        var games = new File() { FileName = "Game.exe", ImageIcon = ImageSource.FromResource("SampleBrowser.SfTreeView.Icons.NodeWithImage.treeview_exe.png", assembly) };
        var tutorials = new File() { FileName = "Tutorials.zip", ImageIcon = ImageSource.FromResource("SampleBrowser.SfTreeView.Icons.NodeWithImage.treeview_zip.png", assembly) };
        var typeScript = new File() { FileName = "TypeScript.7z", ImageIcon = ImageSource.FromResource("SampleBrowser.SfTreeView.Icons.NodeWithImage.treeview_zip.png", assembly) };
        var uiGuide = new File() { FileName = "UI-Guide.pdf", ImageIcon = ImageSource.FromResource("SampleBrowser.SfTreeView.Icons.NodeWithImage.treeview_pdf.png", assembly) };

        var song = new File() { FileName = "Gouttes", ImageIcon = ImageSource.FromResource("SampleBrowser.SfTreeView.Icons.NodeWithImage.treeview_mp3.png", assembly) };

        var camera = new File() { FileName = "Camera Roll", ImageIcon = ImageSource.FromResource("SampleBrowser.SfTreeView.Icons.NodeWithImage.treeview_folder.png", assembly) };
        var stone = new File() { FileName = "Stone.jpg", ImageIcon = ImageSource.FromResource("SampleBrowser.SfTreeView.Icons.NodeWithImage.treeview_png.png", assembly) };
        var wind = new File() { FileName = "Wind.jpg", ImageIcon = ImageSource.FromResource("SampleBrowser.SfTreeView.Icons.NodeWithImage.treeview_png.png", assembly) };

        var img0 = new SubFile() { FileName = "WIN_20160726_094117.JPG", ImageIcon = ImageSource.FromResource("SampleBrowser.SfTreeView.Icons.NodeWithImage.treeview_img0.png", assembly) };
        var img1 = new SubFile() { FileName = "WIN_20160726_094118.JPG", ImageIcon = ImageSource.FromResource("SampleBrowser.SfTreeView.Icons.NodeWithImage.treeview_img1.png", assembly) };

        var video1 = new File() { FileName = "Naturals.mp4", ImageIcon = ImageSource.FromResource("SampleBrowser.SfTreeView.Icons.NodeWithImage.treeview_video.png", assembly) };
        var video2 = new File() { FileName = "Wild.mpeg", ImageIcon = ImageSource.FromResource("SampleBrowser.SfTreeView.Icons.NodeWithImage.treeview_video.png", assembly) };

        doc.Files = new ObservableCollection<File>
            {
                pollution,
                globalWarming,
                sanitation,
                socialNetwork,
                youthEmpower
            };

        download.Files = new ObservableCollection<File>
            {
                games,
                tutorials,
                typeScript,
                uiGuide
            };

        mp3.Files = new ObservableCollection<File>
            {
                song
            };

        pictures.Files = new ObservableCollection<File>
            {
                camera,
                stone,
                wind
            };

        camera.SubFiles = new ObservableCollection<SubFile>
            {
                img0,
                img1
            };

        video.Files = new ObservableCollection<File>
            {
                video1,
                video2
            };

        nodeImageInfo.Add(doc);
        nodeImageInfo.Add(download);
        nodeImageInfo.Add(mp3);
        nodeImageInfo.Add(pictures);
        nodeImageInfo.Add(video);
        return nodeImageInfo;
    }
}
{% endhighlight %}
{% endtabs %}

## Bind to a Hierarchy Property Descriptors data source - Bound Mode

You can create a tree view by binding the [ItemsSource](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_ItemsSource) to a hierarchy property descriptors data source. To create a tree view using hierarchical data binding, set a hierarchical collection to the `ItemsSource` property. Then create a [HierarchyPropertyDescriptors](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_HierarchyPropertyDescriptors) and set the `TargetType` and [ChildPropertyName](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_ChildPropertyName) property values. Finally add that [HierarchyPropertyDescriptors](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_HierarchyPropertyDescriptors) to treeview.

{% tabs %}
{% highlight c# %}
using Syncfusion.Android.TreeView;
using Syncfusion.TreeView.Engine;

protected override void OnCreate(Bundle savedInstanceState)
{
    base.OnCreate(savedInstanceState);
    // Set our view from the "main" layout resource
    SetContentView(Resource.Layout.activity_main);
    SfTreeView treeView = FindViewById<SfTreeView>(Resource.Id.sfTreeView1);
    FileManagerViewModel viewModel = new FileManagerViewModel();
    treeView.ItemsSource = viewModel.ImageNodeInfo;
    var data = new HierarchyPropertyDescriptors();
    data.Add(new HierarchyPropertyDescriptor() { TargetType = typeof(Folder), ChildPropertyName = "Files" });
    data.Add(new HierarchyPropertyDescriptor() { TargetType = typeof(File), ChildPropertyName = "SubFiles" });
    treeView.HierarchyPropertyDescriptors = data;
}
{% endhighlight %}
{% endtabs %}

## Defining a adapter to expander and content view

 By defining the [Adapter](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_Adapter), a custom user interface(UI) can be achieved to display the data items for both expander and content view.

The following code example will illustrate you to customize your custom content view by using `Adapter` property.

### Creating custom view for adapter

{% tabs %}
{% highlight c# %}
// Customized content view
public class NodeImageView : LinearLayout
{
    private TextView label1;
    private ImageViewExt imageIcon;

    public NodeImageView(Context context) : base(context)
    {
        this.Orientation = Orientation.Horizontal;
        label1 = new TextView(context);
        label1.Gravity = GravityFlags.CenterVertical;
        imageIcon = new ImageViewExt(context);
        this.AddView(imageIcon);
        this.AddView(label1);
    }

    protected override void OnMeasure(int widthMeasureSpec, int heightMeasureSpec)
    {
        var density = Resources.DisplayMetrics.Density;
        var measuredWidth = (int)(40 * density);
        var measuredHeight = (int)(45 * density);
        var labelWidth = Math.Abs(widthMeasureSpec - measuredWidth);
        this.label1.SetMinimumHeight(measuredHeight);
        this.label1.SetMinimumWidth(labelWidth);
        this.imageIcon.SetMinimumHeight(measuredHeight);
        this.imageIcon.SetMinimumWidth(measuredWidth);
        this.imageIcon.Measure(measuredWidth, measuredHeight);
        this.label1.Measure(labelWidth, measuredHeight);
        base.OnMeasure(widthMeasureSpec, heightMeasureSpec);
    }

    protected override void OnLayout(bool changed, int l, int t, int r, int b)
    {
        var density = Resources.DisplayMetrics.Density;
        var measuredWidth = (int)(40 * density);
        var measuredHeight = (int)(45 * density);
        this.imageIcon.Layout(0, 0, measuredWidth, measuredHeight);
        this.label1.Layout(measuredWidth, 0, Width, measuredHeight);
    }
}

// Custom image view

internal class ImageViewExt : ImageView
{
    public ImageViewExt(Context context) : base(context)
    {
        this.SetScaleType(ScaleType.CenterInside);
        var padding = (int)(5 * Resources.DisplayMetrics.Density);
        this.SetPadding(padding, padding, padding, padding);
    }

    protected override void OnMeasure(int widthMeasureSpec, int heightMeasureSpec)
    {
        base.OnMeasure(widthMeasureSpec, heightMeasureSpec);
        this.SetMeasuredDimension(widthMeasureSpec, heightMeasureSpec);
    }

    protected override void OnLayout(bool changed, int left, int top, int right, int bottom)
    {
        base.OnLayout(changed, left, top, right, bottom);
    }
}
{% endhighlight %}
{% endtabs %}

### Creating custom adapters to display the data items.

{% tabs %}
{% highlight c# %}
// Adapter extension class
public class NodeImageAdapter : TreeViewAdapter
{
    public NodeImageAdapter()
    {
    }

    protected override View CreateContentView(TreeViewItemInfoBase itemInfo)
    {
        var gridView = new NodeImageView(TreeView.Context);
        return gridView;
    }

    protected override void UpdateContentView(View view, TreeViewItemInfoBase itemInfo)
    {
        var grid = view as NodeImageView;
        var treeViewNode = itemInfo.Node;
        if (grid != null)
        {
            var icon = grid.GetChildAt(0) as ImageView;
            if (icon != null)
            {
                var imageID = (treeViewNode.Content as FileManager).ImageIcon;
                icon.SetImageResource(imageID);
            }

            var label1 = grid.GetChildAt(1) as ContentLabel;
            if (label1 != null)
            {
                label1.Text = (treeViewNode.Content as FileManager).FileName.ToString();
            }
        }
    }
}
{% endhighlight %}
{% endtabs %}

It is also applicable for both Unbound Mode data items. Now, run the application to render the similar output:

You can also download the entire source code of this demo from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStartedBound1294397808).

![Xamarin Android TreeView Bound Mode](Images/TreeView_Templating.png)

## Interacting with TreeView

The `TreeView` allows you to expand and collapse the nodes either by user interaction on the nodes or by programmatically. The expanding and collapsing interactions can be handled with the help of [NodeCollapsing](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html) and [NodeExpanding](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html) events.

 You can define how the nodes to be expanded while loading the TreeView by using [AutoExpandMode](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_AutoExpandMode) property. Also, the `TreeView` allows you to set the restrictions whether expanding and collapsing of nodes can be performed only by tapping in expander view or in both expander view and content view by using [ExpandActionTarget](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_ExpandActionTarget) property. 

N> `AutoExpandMode` property is only applicable for bound mode.For Unbound mode you need to set `IsExpanded` property to `true` while creating the nodes, to be in expanded state while loading the TreeView.

{% tabs %}
{% highlight c# %}
using Syncfusion.Android.TreeView;
using Syncfusion.TreeView.Engine;

protected override void OnCreate(Bundle savedInstanceState)
{
    base.OnCreate(savedInstanceState);
    // Set our view from the "main" layout resource
    SetContentView(Resource.Layout.activity_main);
    SfTreeView treeView = FindViewById<SfTreeView>(Resource.Id.sfTreeView1);
    FileManagerViewModel viewModel = new FileManagerViewModel();
    treeView.AutoExpandMode = AutoExpandMode.AllNodesExpanded;
    treeView.ExpanderActionTarget = ExpanderActionTarget.Node; 
    treeView.ChildPropertyName = "SubFiles";
    treeView.ItemsSource = viewModel.Folders;
    treeView.Adapter = new NodeImageAdapter();
}
{% endhighlight %}
{% endtabs %}

## Selection

The `TreeView` allows selecting the item by setting the [SelectionMode](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_SelectionMode) property. Set the `SelectionMode` property to single, single-deselect, multiple and none based on the requirements. Informations about the selected item can be tracked using the [SelectedItem](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_SelectedItem), [CurrentItem](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_CurrentItem) and [SelectedItems](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_SelectedItems) properties.

It also allows changing the selection highlight color by using the [SelectionBackgroundColor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_SelectionBackgroundColor) property. Additionally, for unbound mode, you can change the selection fore ground color of the text by using the [SelectionForegroundColor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_SelectionForegroundColor) property.

The selection operations can be handled with the help of [SelectionChanging](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html) and [SelectionChanged](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html) events.

{% tabs %}
{% highlight c# %}
using Syncfusion.Android.TreeView;
using Syncfusion.TreeView.Engine;

protected override void OnCreate(Bundle savedInstanceState)
{
    base.OnCreate(savedInstanceState);
    // Set our view from the "main" layout resource
    SetContentView(Resource.Layout.activity_main);
    SfTreeView treeView = FindViewById<SfTreeView>(Resource.Id.sfTreeView1);
    treeView.SelectionMode = SelectionMode.Single;
}
{% endhighlight %}
{% endtabs %}

## Reset tree view items

You can reset the visible treeview items by using the [ResetTreeViewItems](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_ResetTreeViewItems_System_Object_) method. If the parameter is null, all the visible treeview items will reset. If you are passing the `data object` as a parameter, a particular treeview item will reset.

{% tabs %}
{% highlight c# %}
treeView.ResetTreeViewItems();
{% endhighlight %}
{% endtabs %}

## Refresh view

You can refresh the view by using the [RefreshView](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_RefreshView) method. It will be used to refresh the items in the treeview at runtime while updating the view.

{% tabs %}
{% highlight c# %}
treeView.RefreshView();
{% endhighlight %}
{% endtabs %}
