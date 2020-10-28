---
layout: post
title: Load On-demand | TreeView for Xamarin.Android | Syncfusion
description: This topic explains about how to load the child nodes on demand for treeview in SfTreeView Xamarin.Android
platform: Xamarin.Android
control: SfTreeView
documentation: ug
---

# Load on demand in Xamarin.Android TreeView (SfTreeView)

TreeView allows you to load the child items only when they are requested using the Load on-demand(Lazy load). It helps to load the child items from services when the end-user expands the node. Initially populate the root [Nodes](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_Nodes) by assigning the [ItemsSource](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_ItemsSource) and then when any node is expanded, the child items can be loaded using the [LoadOnDemand](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.TreeView.SfTreeView.html#Syncfusion_Android_TreeView_SfTreeView_LoadOnDemand) event. Load on-demand is applicable for the bound mode only.

{% tabs %}
{% highlight c# %}
public class MainActivity : AppCompatActivity
{
    protected override void OnCreate(Bundle savedInstanceState)
    {
        base.OnCreate(savedInstanceState);
        // Set our view from the "main" layout resource
        SetContentView(Resource.Layout.activity_main);
        SfTreeView treeView = FindViewById<SfTreeView>(Resource.Id.sfTreeView1);
        MusicInfoRepository viewModel = new MusicInfoRepository();
        treeView.LoadOnDemand += TreeView_LoadOnDemandEvent;
        treeView.ItemsSource = viewModel.Menu;
        treeView.Adapter = new NodeImageAdapter();

    }
    private async void TreeView_LoadOnDemandEvent(object sender, LoadOnDemandEventArgs e)
    {
        if (e.Action == Action.RequestStatus)
        {
            e.HasChildNodes = (e.Node.Content as MusicInfo).HasChild;
        }

        else if (e.Action == Action.PopulateNodes)
        {
            var viewModel = new MusicInfoRepository();
            var node = e.Node;
            if (node.ChildNodes.Count > 0)
            {
                node.IsExpanded = true;
                return;
            }

            node.ShowExpanderAnimation = true;
            await Task.Delay(2000);
            MusicInfo musicInfo = node.Content as MusicInfo;
            var items = viewModel.GetSubMenu(musicInfo.ID);
            node.PopulateChildNodes(items);
            if (items.Count() > 0)
                node.IsExpanded = true;
            node.ShowExpanderAnimation = false;
        }
    }
}
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
/// <summary>
/// ViewModel class with <see cref="Command"/> for load on demand. 
/// </summary>
public class MusicInfoRepository
{
    private ObservableCollection<MusicInfo> menu;

    public ObservableCollection<MusicInfo> Menu
    {
        get { return menu; }
        set { menu = value; }
    }

    public ICommand TreeViewOnDemandCommand
    {
        get; set;
    }

    public MusicInfoRepository()
    {
        this.Menu = this.GetMenuItems();
        TreeViewOnDemandCommand = new Command(ExecuteOnDemandLoading, CanExecuteOnDemandLoading);
    }

    /// <summary>
    /// CanExecute method is called before expanding and initialization of node. Returns whether the node has child nodes or not.
    /// Based on return value, expander visibility of the node is handled.  
    /// </summary>
    /// <param name="sender">TreeViewNode is passed as default parameter </param>
    /// <returns>Returns true, if the specified node has child items to load and expander icon is displayed for that node, else returns false and icon is not displayed.</returns>
    private bool CanExecuteOnDemandLoading(object sender)
    {
        var hasChildNodes = ((sender as TreeViewNode).Content as MusicInfo).HasChildNodes;
        if (hasChildNodes)
            return true;
        else
            return false;
    }

    /// <summary>
    /// Execute method is called when any item is requested for load-on-demand items.
    /// </summary>
    /// <param name="obj">TreeViewNode is passed as default parameter </param>
    private void ExecuteOnDemandLoading(object obj)
    {
        var node = obj as TreeViewNode;

        // Skip the repeated population of child items when every time the node expands.
        if (node.ChildNodes.Count > 0)
        {
            node.IsExpanded = true;
            return;
        }

        //Animation starts for expander to show progressing of load on demand
        node.ShowExpanderAnimation = true;
        MusicInfo musicInfo = node.Content as MusicInfo;
        Device.BeginInvokeOnMainThread(async () =>
        {
            await Task.Delay(2000);

            //Fetching child items to add
            var items = GetSubMenu(musicInfo.ID);

            // Populating child items for the node in on-demand
            node.PopulateChildNodes(items);
            if (items.Count() > 0)
                //Expand the node after child items are added.
                node.IsExpanded = true;

            //Stop the animation after load on demand is executed, if animation not stopped, it remains still after execution of load on demand.
            node.ShowExpanderAnimation = false;
        });
    }

    private ObservableCollection<MusicInfo> GetMenuItems()
    {
        ObservableCollection<MusicInfo> menuItems = new ObservableCollection<MusicInfo>();
        menuItems.Add(new MusicInfo() { ItemName = "Discover Music", HasChildNodes = true, ID = 1 });
        menuItems.Add(new MusicInfo() { ItemName = "Sales and Events", HasChildNodes = true, ID = 2 });
        menuItems.Add(new MusicInfo() { ItemName = "Categories", HasChildNodes = true, ID = 3 });
        menuItems.Add(new MusicInfo() { ItemName = "MP3 Albums", HasChildNodes = true, ID = 4 });
        menuItems.Add(new MusicInfo() { ItemName = "Fiction Book Lists", HasChildNodes = true, ID = 5 });
        return menuItems;
    }

    public IEnumerable<MusicInfo> GetSubMenu(int iD)
    {
        ObservableCollection<MusicInfo> menuItems = new ObservableCollection<MusicInfo>();
        if (iD == 1)
        {
            menuItems.Add(new MusicInfo() { ItemName = "Hot Singles", HasChildNodes = false, ID = 11 });
            menuItems.Add(new MusicInfo() { ItemName = "Rising Artists", HasChildNodes = false, ID = 12 });
            menuItems.Add(new MusicInfo() { ItemName = "Live Music", HasChildNodes = false, ID = 13 });
            menuItems.Add(new MusicInfo() { ItemName = "More in Music", HasChildNodes = true, ID = 14 });
        }
        else if (iD == 2)
        {
            menuItems.Add(new MusicInfo() { ItemName = "100 Albums - $10 Each", HasChildNodes = false, ID = 21 });
            menuItems.Add(new MusicInfo() { ItemName = "Hip-Hop and R&B Sale", HasChildNodes = false, ID = 22 });
            menuItems.Add(new MusicInfo() { ItemName = "CD Deals", HasChildNodes = false, ID = 23 });
        }
        else if (iD == 3)
        {
            menuItems.Add(new MusicInfo() { ItemName = "Songs", HasChildNodes = false, ID = 31 });
            menuItems.Add(new MusicInfo() { ItemName = "Bestselling Albums", HasChildNodes = false, ID = 32 });
            menuItems.Add(new MusicInfo() { ItemName = "New Releases", HasChildNodes = false, ID = 33 });
            menuItems.Add(new MusicInfo() { ItemName = "MP3 Albums", HasChildNodes = false, ID = 34 });
        }
        else if (iD == 4)
        {
            menuItems.Add(new MusicInfo() { ItemName = "Rock Music", HasChildNodes = false, ID = 41 });
            menuItems.Add(new MusicInfo() { ItemName = "Gospel", HasChildNodes = false, ID = 42 });
            menuItems.Add(new MusicInfo() { ItemName = "Latin Music", HasChildNodes = false, ID = 43 });
            menuItems.Add(new MusicInfo() { ItemName = "Jazz", HasChildNodes = false, ID = 44 });
        }
        else if (iD == 5)
        {
            menuItems.Add(new MusicInfo() { ItemName = "Hunger Games", HasChildNodes = false, ID = 51 });
            menuItems.Add(new MusicInfo() { ItemName = "Pride and Prejudice", HasChildNodes = false, ID = 52 });
            menuItems.Add(new MusicInfo() { ItemName = "Harry Potter", HasChildNodes = false, ID = 53 });
            menuItems.Add(new MusicInfo() { ItemName = "Game Of Thrones", HasChildNodes = false, ID = 54 });
        }
        else if (iD == 14)
        {
            menuItems.Add(new MusicInfo() { ItemName = "Music Trade-In", HasChildNodes = false, ID = 141 });
            menuItems.Add(new MusicInfo() { ItemName = "Redeem a Gift card", HasChildNodes = false, ID = 142 });
            menuItems.Add(new MusicInfo() { ItemName = "Band T-Shirts", HasChildNodes = false, ID = 143 });
        }
        return menuItems;
    }
}
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
/// <summary>
/// Model
/// </summary>
public class MusicInfo : INotifyPropertyChanged
{
    public string itemName;
    public int id;
    public bool hasChildNodes;

    public string ItemName
    {
        get { return itemName; }
        set
        {
            itemName = value;
            OnPropertyChanged("ItemName");
        }
    }

    public int ID
    {
        get { return id; }
        set
        {
            id = value;
            OnPropertyChanged("ID");
        }
    }

    public bool HasChildNodes
    {
        get { return hasChildNodes; }
        set
        {
            hasChildNodes = value;
            OnPropertyChanged("HasChildNodes");
        }
    }

    public event PropertyChangedEventHandler PropertyChanged;

    private void OnPropertyChanged(string propertyName)
    {
        PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
    }
}
{% endhighlight %}
{% endtabs %}

## On-demand loading of child items

You can load child items for the node in the `LoadOnDemand` event. It will get called when user expands the tree node. In `LoadOnDemand` event, you have can perform following operations,
* Show or hide busy indicator in the place of expander by setting [TreeViewNode.ShowExpanderAnimation](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_ShowExpanderAnimation) until the data fetched.
* Once data fetched, you can populate the child nodes by calling [TreeViewNode.PopulateChildNodes](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_PopulateChildNodes_System_Collections_IEnumerable_) method by passing the child items collection. 
* When load on-demand event triggered, the expanding operation will not be handled by `TreeView`. So, you have to set [TreeViewNode.IsExpanded](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_IsExpanded) property to `true` to expand the tree node after populating child nodes.
* You can skip population of child items again and again when every time the node expands, based on [TreeViewNode.ChildNodes](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_ChildNodes) count. 
* You can get the number of child nodes displayed in the view by using the [TreeViewNode.VisibleNodesCount](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_VisibleNodesCount) property.
* The child nodes of the treeView node can be notified based upon the return value of [HasChildNodes](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_HasChildNodes) property. If the node has any child nodes, it returns `true` otherwise it returns `false`.

{% tabs %}
{% highlight c# %}
private async void TreeView_LoadOnDemandEvent(object sender, LoadOnDemandEventArgs e)
{
    if (e.Action == Action.RequestStatus)
    {

        e.HasChildNodes = (e.Node.Content as MusicInfo).HasChild;
    }
    else if (e.Action == Action.PopulateNodes)
    {
        var viewModel = new MusicInfoRepository();
        var node = e.Node;
        // Skip the repeated population of child items when every time the node expands.
        if (node.ChildNodes.Count > 0)
        {
            node.IsExpanded = true;
            return;
        }
        //Animation starts for expander to show progressing of load on demand
        node.ShowExpanderAnimation = true;
        await Task.Delay(2000);
        MusicInfo musicInfo = node.Content as MusicInfo;
        //Fetching child items to add
        var items = viewModel.GetSubMenu(musicInfo.ID);
        // Populating child items for the node in on-demand
        node.PopulateChildNodes(items);
        if (items.Count() > 0)
            //Expand the node after child items are added.
            node.IsExpanded = true;
        //Stop the animation after load on demand is executed, if animation not stopped, it remains still after execution of load on demand.
        node.ShowExpanderAnimation = false;
    }
}
{% endhighlight %}
{% endtabs %}

You can download the entire source code [here](https://github.com/SyncfusionExamples/load-on-demand-treeview-xamarin-android)

![Xamarin Android TreeView with LoadOnDemand](Images/TreeView_LoadonDemand.gif)