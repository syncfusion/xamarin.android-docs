---
layout: post
title: Ticks of Syncfusion RangeSlider control for Xamarin.Android
description: Learn how to set ticks in proper position for RangeSlider control in Xamarin.Android
platform: Xamarin.Android
control: RangeSlider
documentation: ug
---

# Customizing ticks

Tick marks can be placed along the track in a uniform manner or it's position can also be customized.

## TickPlacement

The `TickPlacement` property determines where to draw tick marks in relation to the track. Available options for this property are,

* BottomRight

* Inline

* None

* Outside

* TopLeft

N> The default option is Inline.

### BottomRight

Tick marks are placed either below the track in horizontal orientation or right of the track in vertical orientation.

{% highlight c# %}

	rangeSlider.TickPlacement=TickPlacement.BottomRight;

{% endhighlight %}

![TickPlacement BottomRight Xamarin.Android](images/BottomRight.png)

### TopLeft

Tick marks are placed either above the track in horizontal orientation or left of the track in vertical orientation.

{% highlight c# %}

	rangeSlider.TickPlacement=TickPlacement.TopLeft;

{% endhighlight %}

![TickPlacement TopLeft Xamarin.Android](images/TopLeft.png)

### Inline

Tick marks are placed along the track.

{% highlight c# %}

	rangeSlider.TickPlacement=TickPlacement.Inline;

{% endhighlight %}

![Tick marks Inline Xamarin.Android](images/Inline.png)

### Outside

Tick marks are placed on both sides of the track either in horizontal or vertical orientation.

{% highlight c# %}

	rangeSlider.TickPlacement=TickPlacement.Outside;

{% endhighlight %}

![Tick marks Outline Xamarin.Android](images/Outside.png)

## Customizing tick color

The range slider control provides the `TickColor` property to customize the color of ticks in tick bar.

{% highlight c# %}

namespace GettingStarted
{
      [Activity(Label = "GettingStarted", MainLauncher = true, Icon = "@mipmap/icon")]
      public class MainActivity : Activity
      {
            protected override void OnCreate(Bundle savedInstanceState)
            {
				base.OnCreate(savedInstanceState);
				LinearLayout linearLayout = new LinearLayout(this);
				linearLayout.LayoutParameters = new LayoutParams(LayoutParams.MatchParent, LayoutParams.MatchParent);
				SfRangeSlider rangeSlider = new SfRangeSlider(this);
				rangeSlider.ShowValueLabel = true;
				rangeSlider.TickColor = Color.Rgb(255, 0, 0);
				rangeSlider.TickPlacement = TickPlacement.TopLeft;
				rangeSlider.Orientation = Com.Syncfusion.Sfrangeslider.Orientation.Horizontal;
				linearLayout.AddView(rangeSlider);
				SetContentView(linearLayout);
            }
      }
}

{% endhighlight %}

![Customizing tick color Xamarin.Android](images/TickColor.png)

## Tick length

The `TickLength` property used to customize the length of the ticks.

{% highlight c# %}

	rangeSlider.TickLength = 20;

{% endhighlight %}
