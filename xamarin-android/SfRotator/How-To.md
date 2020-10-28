---
layout: post
title: Customization in Syncfusion Rotator control for Xamarin.Android 
description: Learn how to customize the Rotator control with its Properties
platform: Xamarin.Android 
control: Rotator
documentation: ug
---

# How to create Rotator control in .axml Layout file.?

We can create a rotator control in .axml file and accessing its property in .cs file.

### Create a control in .axml file

Reference the Rotator control view using the fully qualified name like `com.syncfusion.rotator.SfRotator`.

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
android:orientation="vertical"
android:layout_width="match_parent"
android:layout_height="match_parent">
    <com.syncfusion.rotator.SfRotator
    android:id="@+id/rotator"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    />
</LinearLayout>

{% endhighlight %}

## In MainActivity.cs file

{% highlight C# %}

public class MainActivity : Activity
{
    protected override void OnCreate(Bundle savedInstanceState)
    {
    
        base.OnCreate(savedInstanceState);

        SetContentView(Resource.Layout.Main);

        Context context = this;

        SfRotator rotator = (SfRotator)FindViewById(Resource.Id.rotator);

        rotator.SelectedIndex = 2;

        List<SfRotatorItem> collection = new List<SfRotatorItem>();

        for (int i = 1; i <= 5; i++)
        {
            collection.Add(new SfRotatorItem(context) { ImageContent = "movie" + i.ToString() });
        }
        rotator.DataSource = collection;
    }
}

{% endhighlight %}

# How to perform the operation while changing the Rotator's Item.?

We can perform operation while the changing the Rotator's item using `SelectionChanged` event. SelectionChanged event returns changed Rotator control's Item.
<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>e.P0</td>
<td>Displays the changed Rotator's Item</td>
</tr>
</table>

{% highlight C# %}

rotator.SelectionChanged += (object sender, SfRotator.SelectionChangedEventArgs e) =>
{
    // Perform the operation when Rotator's Item changed.
};

{% endhighlight %}

# How to dynamically change the Rotator's Item.?

`SelectedIndex` property is used dynamically change the selected items in Rotator control.

N> Default value of SelectedIndex property is 0. 

{% highlight C# %}	

SfRotator rotator = new SfRotator(this);

rotator.SelectedIndex = 2;
	
{% endhighlight %}
