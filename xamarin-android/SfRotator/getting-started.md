---
layout: post
title: Getting Started with syncfusion Rotator control for Xamarin.Android 
description:  A quick tour to initial users on Syncfusion Rotator control for Xamarin.Android platform
platform: Xamarin.Android 
control: Rotator 
documentation: ug
---

# Getting Started

This section explains you the steps to configure a SfRotator control in a real-time scenario and also provides a walk-through on some of the customization features available in SfRotator control.

## Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

N> Assemblies are available in unzipped package location in Mac.

Add the following assembly references to the Android project,

android\Syncfusion.SfRotator.Android.dll

## Initializing the SfRotator

* Adding namespace for the added assemblies.

{% highlight C# %}

using Com.Syncfusion.Rotator; 

{% endhighlight %}

* Now add the SfRotator control with a required optimal name by using the included namespace.

{% highlight C# %}
	
SfRotator  rotator  = new SfRotator(this);
SetContentView(rotator);

{% endhighlight %}

# Adding items 

SfRotator items can be populated with a collection of image data or any other custom view. This collection must be the items of SfRotatorItem. To get the view of Rotator, we have two ways with SfRotatorItem or using RotatorAdapter.

## Through RotatorItem 

* `ImageContent` - Populating the RotatorItem with collection of Image data.

* `Content` - Populating the RotatorItem with custom view.

### Using ImageContent 

{% highlight C# %}

Context context = this;

SfRotator rotator = new SfRotator(context);

List<SfRotatorItem> collection = new List<SfRotatorItem>();

for(int i = 1; i < 5; i++)
{
	SfRotatorItem item = new SfRotatorItem(context);
	item.ImageContent = "movie" + i;
	collection.Add(item);
}

// Assign the collection of Image date to Rotator's DataSource

rotator.DataSource = collection;

rotator.SelectedIndex = 2;

SetContentView(rotator);

{% endhighlight %}

![](images/rotator.png)

### Using Content

{% highlight C# %}

Context context = this;

SfRotator rotator = new SfRotator(context);

// Collection of RotatorItem

List<SfRotatorItem> collection = new List<SfRotatorItem>();

// Resource of ImageView in RotatorItem's Content

int[] images = { Resource.Drawable.movie1, Resource.Drawable.movie2, Resource.Drawable.movie3, Resource.Drawable.movie4, Resource.Drawable.movie5 };

// Resource of Button in RotatorItem's Content

string[] strings = { "ImageView1", "ImageView2", "ImageView3", "ImageView4", "ImageView5" };

for (int i = 0; i < 5; i++)
{
	SfRotatorItem sfRotatorItem = new SfRotatorItem(context);
	LinearLayout linearLayout = new LinearLayout(context);
	linearLayout.Orientation = Orientation.Vertical;
	ImageView imageView = new ImageView(context);
	imageView.SetImageResource(images[i]);
	Button button = new Button(context);
	button.Text = strings[i];
	button.TextSize = 33;
	button.SetBackgroundColor(Android.Graphics.Color.BurlyWood);
	linearLayout.AddView(button);
	linearLayout.AddView(imageView);
	sfRotatorItem.Content = linearLayout;
	collection.Add(sfRotatorItem);
}

rotator.SelectedIndex = 2;

// Assign the collection of custom view  Rotator's DataSource

rotator.DataSource = collection;

SetContentView(rotator);

{% endhighlight %}

![](images/content.png)

## Through RotatorAdapter

RotatorAdapter object acts as a bridge between an RotatorAdapterView and the underlying data for that view.

### CustomAdapter Class

{% highlight C# %}

public class AdapterClass :RotatorAdapter
{

	// Override method to get the Dotted view Rotator control.

	public override Android.Views.View GetItemView(SfRotator p0, int p1)
	{
	    return base.GetItemView(p0, p1);
	} 
	// Override method to get the Thumbnail view Rotator control.
		
	public override Android.Views.View GetThumbnailView(SfRotator p0, int p1)
	{
		return base.GetThumbnailView(p0, p1);
	}

}

{% endhighlight %}

### In MainActivity.cs

{% highlight C# %}

public class MainActivity : Activity
{
	protected override void OnCreate(Bundle savedInstanceState)
	{
		
	base.OnCreate(savedInstanceState);

	Context context = this;

	SfRotator rotator = new SfRotator(context);

	List<SfRotatorItem> collection = new List<SfRotatorItem>();
	collection.Add(new SfRotatorItem(this));
	collection.Add(new SfRotatorItem(this));
	collection.Add(new SfRotatorItem(this));
	collection.Add(new SfRotatorItem(this));
	collection.Add(new SfRotatorItem(this));
	
	// Determines the count of custom view will reflect on Rotator control

	rotator.DataSource = collection;

	rotator.SelectedIndex = 2;

	// Resources of used custom view in Adapter

	int[] images = { Resource.Drawable.movie1, Resource.Drawable.movie2, Resource.Drawable.movie3, Resource.Drawable.movie4, Resource.Drawable.movie5 };

	// RotatorAdapter usage

	rotator.Adapter = new AdapterClass(this,images);

	SetContentView(rotator);

	}
}

{% endhighlight %}

![](images/rotator.png)

## Set Navigation Mode

SfRotator provides option to display the navigating items either in Thumbnail or Dots mode. The navigation mode for navigating items can be decided using `NavigationStripMode` property.

{% highlight C# %}	

SfRotator rotator = new SfRotator(this);

rotator.NavigationStripMode = NavigationStripMode.Thumbnail;

{% endhighlight %}

N> Default Navigation strip mode is `Dot`.

## Customizing Position

The placement position of navigation strip items such as Thumbnail or Dots can be customized in SfRotator. This can be specified using `NavigationStripPosition` property.  

{% highlight C# %}	

SfRotator rotator = new SfRotator(this);

rotator.NavigationStripPosition = NavigationStripPosition.Right;
	
{% endhighlight %}

N> Default Navigation strip position is `Bottom`.


