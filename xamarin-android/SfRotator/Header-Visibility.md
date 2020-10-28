---
layout: post
title: Various features in Syncfusion Rotator control for Xamarin.Android 
description: Learn how to set the autoplay option, loop the items, enable Text Area  and choose the navigation direction in Rotator control for Xamarin.Android 
platform: Xamarin.Android 
control: Rotator
documentation: ug
---

# Header Visibility

The `TextVisible` property can be used to enable the text area visibility in bottom area of SfRotator for providing additional information of items. TextVisible property is used to change the visibility of the Text panel that is displayed when SfRotatorItem collection is set.

N> By default, the property value is false.

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

// Used Resource folder images's name will display at the bottom of Rotator control.

rotator.TextVisible = true;

rotator.SelectedIndex = 2;

SetContentView(rotator);

{% endhighlight %}
