---
layout: post
title: Handling the segments in Xamarin.Android Syncfusion Segmented control 
description: Learn how to restrict the visible segment count and its available scrolling options in Xamarin.Android Segmented control.
platform: Xamarin.Android
control: SegmentedControl
documentation: ug
---

# Handling multiple segments in Xamarin.Android SfSegmentedControl

The segmented control handles the segmented items with the space distributed for the items on two ways.

## Visible segment counts

The segmented control displays the item for the view based on the count which is given for [`VisibleSegmentCount`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentedControl.html#Syncfusion_Android_Buttons_SfSegmentedControl_VisibleSegmentsCount). 

{% highlight c# %}

[C#]

segmentedControl.VisibleSegmentsCount = 4;
....
segmentedControl.ItemsSource = = new ObservableCollection<SfSegmentItem>
{
  new SfSegmentItem(){Text = "Item1"},          
  new SfSegmentItem(){Text = "Item2"},     
  new SfSegmentItem(){Text = "Item3"},  
  new SfSegmentItem(){Text = "Item4"},          
  new SfSegmentItem(){Text = "Item5"},     
  new SfSegmentItem(){Text = "Item6"},  
  new SfSegmentItem(){Text = "Item7"},          
};
   
{% endhighlight %}

![Xamarin.Android SfSegmentedControl with four visible segment](images/Handling-multiple-segments/visiblesegment.png)

## Scrolling

When the available space in the segmented control is not equally distributed, the items beyond the edges of the control can be viewed by scrolling the panel.




