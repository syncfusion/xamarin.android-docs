---
layout: post
title: Getting Started with Syncfusion NavigationDrawer control for Xamarin.Android
description: A quick tour to initial users on Syncfusion NavigationDrawer control for Xamarin.Android platform
platform: Xamarin.Android
control: NavigationDrawer
documentation: ug
---

# Getting Started

This section provides overview for working with Essential NavigationDrawer for Xamarin.Android. You can walk through the entire process of creating an NavigationDrawer.

## Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

Add the following assembly references to the Android project,

android\Syncfusion.SfNavigationDrawer.Andriod.dll

and 

Xamarin.Android.Support.v4 library (from Nuget Packages)

## Add SfNavigationDrawer

* Adding reference to NavigationDrawer.

{% tabs %}

{% highlight c# %}

using Com.Syncfusion.NavigationDrawer; 

{% endhighlight %}

{% endtabs %}

* Create an instance of SfNavigationDrawer.

{% tabs %}

{% highlight c# %}
 
SfNavigationDrawer navigationDrawer = new SfNavigationDrawer(this);
SetContentView(navigationDrawer);
	
{% endhighlight %}

{% endtabs %}

## Add Drawer Content

The sliding main content of the SfNavigationDrawer which is a part of DrawerPanel can be set using `DrawerContentView` property with desired views.

{% tabs %}

{% highlight c# %}

namespace NavigationDrawerSample
{
    [Activity(Label = "NavigationDrawerSample", MainLauncher = true, Icon = "@drawable/icon")]
    public class MainActivity : Activity
    {
        ListView viewItem;
        ArrayAdapter<string> arrayAdapter;
        protected override void OnCreate(Bundle bundle)
        {
            base.OnCreate(bundle);

            SfNavigationDrawer navigationDrawer;
            
            navigationDrawer = new SfNavigationDrawer(this);
            List<string> positionlist = new List<string>();
            positionlist.Add("Home");
            positionlist.Add("Profile");
            positionlist.Add("Inbox");
            positionlist.Add("Outbox");
            positionlist.Add("Sent Items");
            positionlist.Add("Trash");
            arrayAdapter = new ArrayAdapter<string>(this, Android.Resource.Layout.SimpleListItem1, positionlist);
            viewItem = new ListView(this);
            viewItem.Adapter = arrayAdapter;
            viewItem.SetBackgroundColor(Android.Graphics.Color.ParseColor("#1aa1d6"));
            viewItem.LayoutParameters = new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MatchParent, ViewGroup.LayoutParams.MatchParent);FrameLayout frameLayout = new FrameLayout(this);
            frameLayout.LayoutParameters = new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MatchParent, ViewGroup.LayoutParams.MatchParent);
            frameLayout.AddView(viewItem);
            navigationDrawer.DrawerContentView = frameLayout;
			SetContentView(navigationDrawer);
		}
	}
}

{% endhighlight %}

{% endtabs %}


## Add Drawer Header Content

SfNavigationDrawer provides option to display certain information like user id or names in the header part instead of providing everything in the drawer content view. 

This can be done using `DrawerHeaderView` property in SfNavigationDrawer.

{% tabs %}

{% highlight c# %}

	namespace navigationDrawerSample
{
	[Activity(Label = "navigationDrawerSample", MainLauncher = true, Icon = "@mipmap/icon")]
	public class MainActivity : Activity
	{
           SfNavigationDrawer navigationDrawer;
           protected override void OnCreate(Bundle bundle)
        {
            base.OnCreate(bundle);
            
            navigationDrawer = new SfNavigationDrawer(this);

            ImageView userImg = new ImageView(this);
            userImg.SetImageResource(Resource.Drawable.Icon);
            userImg.SetBackgroundColor(Android.Graphics.Color.ParseColor("#1aa1d6"));
            TextView userName = new TextView(this);
            userName.Text = "James Pollock";
            userName.TextSize = 20;
            userName.SetBackgroundColor(Android.Graphics.Color.Transparent);
            userName.SetTextColor(Android.Graphics.Color.White);
            LinearLayout headerLayout = new LinearLayout(this);
            headerLayout.Orientation = Orientation.Vertical;
            headerLayout.SetBackgroundColor(Android.Graphics.Color.ParseColor("#1aa1d6"));
            headerLayout.SetPadding(0, 20, 0, 0);
            headerLayout.AddView(userImg);
            headerLayout.AddView(userName);
            navigationDrawer.DrawerHeaderView = headerLayout;
            SetContentView(navigationDrawer);
    }
}
}
 
 
{% endhighlight %}

{% endtabs %}

## Add Main Content

The main view of the SfNavigationDrawer can be set using `ContentView` property with desired views.

{% tabs %}

{% highlight c# %}
	namespace navigationDrawerSample
{
	[Activity(Label = "navigationDrawerSample", MainLauncher = true, Icon = "@mipmap/icon")]
	public class MainActivity : Activity
	{
           SfNavigationDrawer navigationDrawer;
           protected override void OnCreate(Bundle bundle)
        {
            base.OnCreate(bundle);
            
            navigationDrawer = new SfNavigationDrawer(this);
            FrameLayout ContentFrame=new FrameLayout(this); 
            ContentFrame.SetBackgroundColor(Android.Graphics.Color.White);
            ImageView userImg = new ImageView(this);
            userImg.SetImageResource(Resource.Drawable.Icon);
            userImg.SetBackgroundColor(Android.Graphics.Color.ParseColor("#1aa1d6"));
            ContentFrame.AddView(userImg);
            navigationDrawer.ContentView=ContentFrame;
			SetContentView(navigationDrawer);
		}
	}
}


{% endhighlight %}

{% endtabs %}

![](images/getting-started.png)

## Set Drawing Edge for Drawer Panel

SfNavigationDrawer provides support to change the sliding position of the DrawerView panel. This can be set using `Position` property. The position can be any one of the following four options.

* Left

* Right

* Top

* Bottom

N> The default option is Left.

{% tabs %}

{% highlight c# %}

Position sliderposition = Position.Left;	
navigationDrawer.Position=sliderposition;

{% endhighlight %}

{% endtabs %}

## Change Drawer Opening Animation

The `Transition` property specifies the sliding animations for the DrawerView panel. The `Transition` property has the following three options,

* SlideOnTop
* Push
* Reveal

N> The default transition is SlideOnTop.

{% tabs %}

{% highlight c# %} 

    Transition sliderTransition = Transition.SlideOnTop;
	navigationDrawer.Transition = sliderTransition;


{% endhighlight %}

{% endtabs %}
