---

layout: post
title: Tooltip in Syncfusion Rating control for Xamarin.Android
description: Learn how to change the tooltip of rating control
platform: Xamarin.Android
control: Rating
documentation: ug

---

# Tooltip

Tooltip provides additional information about objects that are unfamiliar to users and are not directly displayed in UI. In the Xamarin.Forms SfRating control, tooltip shows the data of `Value`. It will be displayed when the mouse is hovered over the rating items and will be disappeared when a rating item is selected.

## Set tooltip placement

Using the `ToolTipPlacement` property, you can define where the tooltip needs to be displayed. The `TooTipPlacement` property have the following three types:

*BottomRight
*None
*TopLeft

N> By default, value of the `ToolTipPlacement` property is set to None.

### TopLeft 

The tooltip will be displayed on top of the rating stars. 

{% tabs %}

{% highlight C# %}

	   rating.TooltipPlacement = TooltipPlacement.TopLeft;

{% endhighlight %}

{% endtabs %}

![Tooltip at top](images/leftTop.jpg) 

### BottomRight

The tooltip will be displayed on bottom of the rating stars.

{% tabs %}

{% highlight C# %}

	   rating.TooltipPlacement = TooltipPlacement.BottomRight;

{% endhighlight %}

{% endtabs %}

![Tooltip at bottom](images/rightBottom.jpg)

### None

The tooltip will be disappeared when setting ToolTipPlacement to None.

{% tabs %}

{% highlight C# %}

	   rating.TooltipPlacement = TooltipPlacement.None;

{% endhighlight %}

{% endtabs %}

![No tooltip](images/null.jpg)

## Set tooltip precision

The `ToolTipPrecision` property sets the number precisions to be displayed after decimal point in tooltip.

N> The default value of this property is 1. 

{% tabs %}

{% highlight C# %}

       rating.TooltipPrecision = 6;

{% endhighlight %}

{% endtabs %}

![Tooltip Precision](images/toolTipPrecision.jpg)

