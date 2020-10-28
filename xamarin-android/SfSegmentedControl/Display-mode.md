---
layout: post
title: Display mode  in Syncfusion segmented control for Xamarin.Android
description: Learn how to display segmented items with icons,text or a combination of both icon and text in Segmented control
platform: Xamarin.Android
control: SegmentedControl
documentation: ug
---

# Display mode in Xamarin.Android Segmented control (SfSegmentedControl)

Depending on the application, different scenarios may require icons, text, or a combination of both for effective communication. The segmented control supports these three options.

## Text

Items populated in the segmented control will be displayed as text by default.

{% highlight c# %}

[C#]

SfSegmentedControl segmentedControl = new SfSegmentedControl(this);
segmentedControl.SelectionTextColor = Color.ParseColor("#FFFFFF");
segmentedControl.VisibleSegmentsCount = 3;
segmentedControl.BackColor = Color.ParseColor("#048EAC");
segmentedControl.CornerRadius = 15;
segmentedControl.DisplayMode = SegmentDisplayMode.Text;
segmentedControl.BorderColor = Color.ParseColor("#929292");
segmentedControl.SelectedIndex = 0;
segmentedControl.FontColor = Color.Black;
segmentedControl.SegmentBackgroundColor = Color.Transparent;
segmentedControl.ItemsSource = new ObservableCollection<SfSegmentItem>
{
    new SfSegmentItem(){ Text = "Day"},
    new SfSegmentItem(){Text = "Week"},
    new SfSegmentItem(){ Text = "Month"},
};

SelectionIndicatorSettings selectionIndicator = new SelectionIndicatorSettings()
{
    Color = Color.White
};
    
{% endhighlight %}

![Xamarin.Android SfSegmentedControl with Text display mode](images/Display-mode/Xamarin_Android_Text.png)

## Image 

Items populated in the segmented control can be displayed as icons.

{% highlight c# %}

[C#]

SfSegmentedControl segmentedControl = new SfSegmentedControl(this);
...
segmentedControl.DisplayMode = SegmentDisplayMode.Image;
segmentedControl.ItemsSource = new ObservableCollection<SfSegmentItem>
{
    new SfSegmentItem(){IconFont = "6", FontIconFontColor=Color.ParseColor("#FFFFFF"), FontColor=Color.ParseColor("#FFFFFF")},    
    new SfSegmentItem(){IconFont = "6", FontIconFontColor=Color.ParseColor("#FFFFFF"), FontColor=Color.ParseColor("#FFFFFF")},     
    new SfSegmentItem(){IconFont = "6", FontIconFontColor=Color.ParseColor("#FFFFFF"), FontColor=Color.ParseColor("#FFFFFF")}       
};  
        
{% endhighlight %}

![Xamarin.Android SfSegmentedControl with Image display mode](images/Display-mode/Xamarin_Android_Image.png)

## Image with text

Items populated in the segmented control can be displayed as icons with accompanying text.

{% highlight c# %}

[C#]

SfSegmentedControl segmentedControl = new SfSegmentedControl(this);
...
segmentedControl.DisplayMode = SegmentDisplayMode.ImageWithText;
segmentedControl.ItemsSource = new ObservableCollection<SfSegmentItem>
{
    new SfSegmentItem(){IconFont = "6", FontIconFontColor=Color.ParseColor("#FFFFFF"), FontColor=Color.ParseColor("#FFFFFF"), Text = "Day"},     
    new SfSegmentItem(){IconFont = "6", FontIconFontColor=Color.ParseColor("#FFFFFF"), FontColor=Color.ParseColor("#FFFFFF"), Text = "Week"}    
    new SfSegmentItem(){IconFont = "6", FontIconFontColor=Color.ParseColor("#FFFFFF"), FontColor=Color.ParseColor("#FFFFFF"), Text = "Month"}
};
   
{% endhighlight %}

![Xamarin.Android SfSegmentedControl with Image and Text display mode](images/Display-mode/Xamarin_Android_ImagewithText.png)

## How to generate font icons

The segmented control enables the user to use font icons for the items in the data source collection. For this we have to first give the desired font icon and its font family using [`IconFont`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentItem.html#Syncfusion_Android_Buttons_SfSegmentItem_IconFont) and [`FontIconTypeface`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfSegmentItem.html#Syncfusion_Android_Buttons_SfSegmentItem_FontIconTypeface) property.

N> Font family must be added to the respective folders based on the platforms 
Android -> Add the font family inside Resource-> drawable

{% highlight c# %}

[C#]

segmentedControl.FontIconTypeface = "segment.ttf";

{% endhighlight %}

