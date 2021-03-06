---
layout: post
title: Scrolling | TreeView for Xamarin.Android | Syncfusion
description: Describes about programmatic scrolling of treeview.
platform: Xamarin.Android
control: SfTreeView
documentation: ug
---

# Scrolling

## Programmatic scrolling

### Bring InTo View

The TreeView allows programmatically scrolling based on the data model and [TreeViewNode](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.TreeView.Engine.TreeViewNode.html) by using the [BringIntoView](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_BringIntoView_Syncfusion_TreeView_Engine_TreeViewNode_System_Boolean_System_Boolean_Syncfusion_Android_TreeView_ScrollToPosition_) method.

It also enables and disables the scrolling animation when changing the view. By default, the scrolling will be animated.

{% tabs %}
{% highlight c# %}

SfTreeView treeView;
FileManagerViewModel viewModel;

protected override void OnCreate(Bundle savedInstanceState)
{
    base.OnCreate(savedInstanceState);
    // Set our view from the "main" layout resource
    SetContentView(Resource.Layout.activity_main);
    treeView = FindViewById<SfTreeView>(Resource.Id.sfTreeView1);
    viewModel = new FileManagerViewModel();
    treeView.ChildPropertyName = "SubFiles";
    treeView.ItemsSource = viewModel.Folders;
    treeView.Adapter = new NodeImageAdapter();
    treeView.Loaded += TreeView_Loaded;
}

private void TreeView_Loaded(object sender, TreeViewLoadedEventArgs e)
{
    var count= viewModel.ImageNodeInfo.Count;
    var data = viewModel.ImageNodeInfo[count-1];
    treeView.BringIntoView(data);
}

{% endhighlight %}
{% endtabs %}

## Scrollbar Visibility

The TreeView provides an option to enable or disable the `Scrollbar` visibility by using the [IsScrollBarVisible](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_IsScrollBarVisible) property. By default, the value will be true.

N> Due to some restrictions in native ScrollView, you cannot change the `IsScrollBarVisible` value at runtime. It can be defined only when initializing the TreeView.

{% tabs %}
{% highlight c# %}

treeView.IsScrollBarVisible = false;

{% endhighlight %}
{% endtabs %}
