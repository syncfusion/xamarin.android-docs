---
layout: post
title: Various features of Syncfusion NavigationDrawer control for Xamarin.Android
description: Learn how to set content view, drawer content view, footer view, header view, drawer size in NavigationDrawer.
platform: Xamarin.Android
control: NavigationDrawer
documentation: ug
---

# Setting Main Content

The SfNavigationDrawer is mainly divided into two parts, such as [Main Content](#main-content) and  [Drawer Panel Content](/xamarin-android/SfNavigationDrawer/Drawer-Content "Sliding Panel Content")

## Main Content

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
	
![](images/Content-View.png)

