---
layout: post
title: Events in Syncfusion RadialMenu control for Xamarin.Android
description: Learn how to perform events like navigating, opening, navigated, opened, center button tapped and when the center button back has been tapped in SfRadialMenu.
platform: Xamarin.Android
control: SfRadialMenu
documentation: ug
---

# Events

## Perform an action when navigating to the next level

In a radial menu, you can perform actions when navigating from one level to another. The `Navigating` event occurs when navigating from one level to another, and the `Navigated` event occurs after  navigating to another level.

{% tabs %}
{% highlight c# %}

using Android.App;
using Android.Widget;
using Android.OS;
using Syncfusion.SfRadialMenu.Android;
using Android.Graphics;
using Android.Views;
using System.Collections.Generic;

namespace GettingStarted
{
    [Activity(Label = "GettingStarted", MainLauncher = true)]
    public class MainActivity : Activity
    {
        protected override void OnCreate(Bundle savedInstanceState)
        {
            base.OnCreate(savedInstanceState);
            SfRadialMenu radialMenu = new SfRadialMenu(this);
            radialMenu.Navigating += RadialMenu_Navigating;
            radialMenu.Navigated += RadialMenu_Navigated;
            List<SfRadialMenuItem> itemCollection = new List<SfRadialMenuItem>();
            itemCollection.Add(new SfRadialMenuItem(this) { Text = "Cut" });
            itemCollection.Add(new SfRadialMenuItem(this) { Text = "Copy" });
            itemCollection.Add(new SfRadialMenuItem(this) { Text = "Paste" });
            radialMenu.Items = itemCollection;
            radialMenu.CenterButtonText = "\uE713";
            radialMenu.CenterButtonTypeface = Typeface.CreateFromAsset(this.Assets, "Segoe MDL2 Assets.ttf");
            radialMenu.CenterButtonRadius = 32;
            radialMenu.CenterButtonBorderColor = Color.White;
            SetContentView(radialMenu);
        }

        private void RadialMenu_Navigated(object sender, NavigatedEventArgs e)
        {
            Android.App.AlertDialog.Builder dialog = new Android.App.AlertDialog.Builder(this);
            Android.App.AlertDialog alert = dialog.Create();
            alert.SetTitle("Alert");
            alert.SetMessage("ItemNavigated");
            alert.SetButton("OK", (c, eve) =>
            {
                // OK button click task  
            });

            alert.Show();
        }

        private void RadialMenu_Navigating(object sender, NavigatingEventArgs e)
        {
            Android.App.AlertDialog.Builder dialog = new Android.App.AlertDialog.Builder(this);
            Android.App.AlertDialog alert = dialog.Create();
            alert.SetTitle("Alert");
            alert.SetMessage("ItemNavigating");
            alert.SetButton("OK", (c, eve) =>
            {
                // OK button click task  
            });

            alert.Show();
        }
    }
}

{% endhighlight %}
{% endtabs %}

N> You can cancel navigation using the `Cancel` event argument.

## Perform an action when opening the radial menu

You can perform an action when opening the radial menu. The `Opening` event occurs when opening the radial menu, and the `Opened` event occurs after the radial menu is opened.

{% tabs %}
{% highlight c# %}

using Android.App;
using Android.Widget;
using Android.OS;
using Syncfusion.SfRadialMenu.Android;
using Android.Graphics;
using Android.Views;
using System.Collections.Generic;

namespace GettingStarted
{
    [Activity(Label = "GettingStarted", MainLauncher = true)]
    public class MainActivity : Activity
    {
        protected override void OnCreate(Bundle savedInstanceState)
        {
            base.OnCreate(savedInstanceState);
            SfRadialMenu radialMenu = new SfRadialMenu(this);
            radialMenu.Opening += RadialMenu_Opening;
            radialMenu.Opened += RadialMenu_Opened;
            List<SfRadialMenuItem> itemCollection = new List<SfRadialMenuItem>();
            itemCollection.Add(new SfRadialMenuItem(this) { Text = "Cut" });
            itemCollection.Add(new SfRadialMenuItem(this) { Text = "Copy" });
            itemCollection.Add(new SfRadialMenuItem(this) { Text = "Paste" });
            radialMenu.Items = itemCollection;
            radialMenu.CenterButtonText = "\uE713";
            radialMenu.CenterButtonBackText = "\uE72b";
            radialMenu.CenterButtonTypeface = Typeface.CreateFromAsset(this.Assets, "Segoe_MDL2_Assets.ttf");
            radialMenu.CenterButtonRadius = 32;
            radialMenu.CenterButtonBorderColor = Color.White;
            SetContentView(radialMenu);
        }

        private void RadialMenu_Opened(object sender, OpenedEventArgs e)
        {
            Android.App.AlertDialog.Builder dialog = new Android.App.AlertDialog.Builder(this);
            Android.App.AlertDialog alert = dialog.Create();
            alert.SetTitle("Alert");
            alert.SetMessage("ItemOpening");
            alert.SetButton("OK", (c, eve) =>
            {
                // OK button click task  
            });
            alert.Show();
        }

        private void RadialMenu_Opening(object sender, OpeningEventArgs e)
        {
            Android.App.AlertDialog.Builder dialog = new Android.App.AlertDialog.Builder(this);
            Android.App.AlertDialog alert = dialog.Create();
            alert.SetTitle("Alert");
            alert.SetMessage("ItemOpened");
            alert.SetButton("OK", (c, eve) =>
            {
                // OK button click task  
            });
            alert.Show();
        }
    }
}

{% endhighlight %}
{% endtabs %}

## Perform an action when closing the radial menu

You can perform an action when closing the radial menu. The `Closing` event occurs when closing the radial menu, and the `Closed` event occurs after the radial menu is closed.

N> You can cancel the opening of the radial menu using the `Cancel` event argument.

{% tabs %}
{% highlight c# %}

using Android.App;
using Android.Widget;
using Android.OS;
using Syncfusion.SfRadialMenu.Android;
using Android.Graphics;
using Android.Views;
using System.Collections.Generic;

namespace GettingStarted
{
    [Activity(Label = "GettingStarted", MainLauncher = true)]
    public class MainActivity : Activity
    {
		protected override void OnCreate(Bundle savedInstanceState)
		{
			base.OnCreate(savedInstanceState);
			SfRadialMenu radialMenu = new SfRadialMenu(this);
			radialMenu.Closing += RadialMenu_Closing;
			radialMenu.Closed += RadialMenu_Closed;
			List<SfRadialMenuItem> itemCollection = new List<SfRadialMenuItem>();
			itemCollection.Add(new SfRadialMenuItem(this) {Text="Cut"});
			itemCollection.Add(new SfRadialMenuItem(this) {Text ="Copy"});
			itemCollection.Add(new SfRadialMenuItem(this) {Text ="Paste"});
			radialMenu.Items = itemCollection;
			radialMenu.CenterButtonText = "\uE713";
			radialMenu.CenterButtonBackText = "\uE72b";
			radialMenu.CenterButtonTypeface = Typeface.CreateFromAsset(this.Assets, "Segoe MDL2 Assets.ttf");
			radialMenu.CenterButtonRadius = 32;
			radialMenu.CenterButtonBorderColor = Color.White;
			SetContentView(radialMenu);
		}

		private void RadialMenu_Closed(object sender, ClosedEventArgs e)
		{
			Android.App.AlertDialog.Builder dialog = new Android.App.AlertDialog.Builder(this);
			Android.App.AlertDialog alert = dialog.Create();
			alert.SetTitle("Alert");
			alert.SetMessage("ItemClosed");
			alert.SetButton("OK", (c, eve) =>
			{
				// OK button click task  
			});
			alert.Show();
		}

		private void RadialMenu_Closing(object sender, ClosingEventArgs e)
		{
			Android.App.AlertDialog.Builder dialog = new Android.App.AlertDialog.Builder(this);
			Android.App.AlertDialog alert = dialog.Create();
			alert.SetTitle("Alert");
			alert.SetMessage("ItemClosing");
			alert.SetButton("OK", (c, eve) =>
			{
				// OK button click task  
			});
			alert.Show();
		}
	}
}

{% endhighlight %}
{% endtabs %}

N> You can close navigation using the `Cancel` event argument.

## Perform an action by tapping the center button

You can perform an action by tapping the center button of the radial menu. The `CenterButtonBackTapped` event occurs when the center button of the radial menu is tapped.

{% tabs %}
{% highlight c# %}

using Android.App;
using Android.Widget;
using Android.OS;
using Syncfusion.SfRadialMenu.Android;
using Android.Graphics;
using Android.Views;
using System.Collections.Generic;

namespace GettingStarted
{
    [Activity(Label = "GettingStarted", MainLauncher = true)]
    public class MainActivity : Activity
    {
	protected override void OnCreate(Bundle savedInstanceState)
		{
			base.OnCreate(savedInstanceState);
			SfRadialMenu radialMenu = new SfRadialMenu(this);
			radialMenu.CenterButtonBackTapped += RadialMenu_CenterButtonBackTapped;
			List<SfRadialMenuItem> itemCollection = new List<SfRadialMenuItem>();
			itemCollection.Add(new SfRadialMenuItem(this) {Text="Cut"});
			itemCollection.Add(new SfRadialMenuItem(this) {Text ="Copy"});
			itemCollection.Add(new SfRadialMenuItem(this) {Text ="Paste"});
			radialMenu.Items = itemCollection;
			radialMenu.CenterButtonText = "\uE713";
			radialMenu.CenterButtonBackText = "\uE72b";
			radialMenu.CenterButtonTypeface = Typeface.CreateFromAsset(this.Assets, "Segoe MDL2 Assets.ttf");
			radialMenu.CenterButtonRadius = 32;
			radialMenu.CenterButtonBorderColor = Color.White;
			SetContentView(radialMenu);
		}

		private void RadialMenu_CenterButtonBackTapped(object sender, CenterButtonBackTappedEventArgs e)
		{
			Android.App.AlertDialog.Builder dialog = new Android.App.AlertDialog.Builder(this);
			Android.App.AlertDialog alert = dialog.Create();
			alert.SetTitle("Alert");
			alert.SetMessage("CenterButtonBackTapped");
			alert.SetButton("OK", (c, eve) =>
			{
				// OK button click task  
			});
			alert.Show();
		}
	}
}

{% endhighlight %}
{% endtabs %}

## Perform an action by tapping the radial menu item

You can perform an action by tapping a radial menu item. The `CenterButtonBackTapped` event occurs when the radial menu item is tapped.

{% tabs %}
{% highlight xaml %}

using Android.App;
using Android.Widget;
using Android.OS;
using Syncfusion.SfRadialMenu.Android;
using Android.Graphics;
using Android.Views;
using System.Collections.Generic;

namespace GettingStarted
{
    [Activity(Label = "GettingStarted", MainLauncher = true)]
    public class MainActivity : Activity
    {
		protected override void OnCreate(Bundle savedInstanceState)
		{
			base.OnCreate(savedInstanceState);
			SfRadialMenu radialMenu = new SfRadialMenu(this);
			List<SfRadialMenuItem> itemCollection = new List<SfRadialMenuItem>();
			itemCollection.Add(new SfRadialMenuItem(this) {Text="Cut"});
			itemCollection.Add(new SfRadialMenuItem(this) {Text ="Copy"});
			itemCollection.Add(new SfRadialMenuItem(this) {Text ="Paste"});			
			radialMenu.Items = itemCollection;
			radialMenu.CenterButtonText = "\uE713";
			radialMenu.CenterButtonTypeface = Typeface.CreateFromAsset(this.Assets, "Segoe MDL2 Assets.ttf");
			radialMenu.CenterButtonRadius = 32;
			radialMenu.CenterButtonBorderColor = Color.White;
			radialMenu.Items[0].ItemTapped += MainActivity_ItemTapped;
			SetContentView(radialMenu);
		}

		private void MainActivity_ItemTapped(object sender, RadialMenuItemTappedEventArgs e)
		{
			Android.App.AlertDialog.Builder dialog = new Android.App.AlertDialog.Builder(this);
			Android.App.AlertDialog alert = dialog.Create();
			alert.SetTitle("Alert");
			alert.SetMessage("ItemTapped");
			alert.SetButton("OK", (c, eve) =>
			{
				// OK button click task  
			});
			alert.Show();
		}
	}
}

{% endhighlight %}
{% endtabs %}