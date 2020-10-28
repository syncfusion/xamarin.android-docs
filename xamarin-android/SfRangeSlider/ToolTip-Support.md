---
layout: post
title: ToolTip support for Syncfusion RangeSlider control for Xamarin.Android
description: Learn how to set tooltip for RangeSlider in Xamarin.Android
platform: Xamarin.Android
control: RangeSlider
documentation: ug
---

# ToolTip Support

The Tooltip shows the current value based on thumb position.

## Set ToolTip Precision

The `ToolTipPrecision` property is used to define the precision of the value displayed in the Tooltip.

{% tabs %}

{% highlight c# %}

	rangeSlider.ToolTipPrecision = 2;
	
{% endhighlight %}

{% endtabs %}

## Set ToolTip Placement

The position of the Tooltip in relation to the thumb can be controlled by the `ToolTipPlacement` property. It has the following options.

1. BottomRight
2. TopLeft
3. None

### BottomRight

The Tooltip will be placed either below the Thumb in horizontal orientation or right of the Thumb in vertical orientation.

{% tabs %}

{% highlight c# %}

rangeSlider.ToolTipPlacement = ToolTipPlacement.BottomRight;
	
{% endhighlight %}

{% endtabs %}

### TopLeft

The Tooltip will be placed either above the Thumb in horizontal orientation or left of the Thumb in vertical orientation.

{% tabs %}

{% highlight c# %}

rangeSlider.ToolTipPlacement = ToolTipPlacement.TopLeft;
	
{% endhighlight %}

{% endtabs %}

### None

Tooltip will be collapsed.

{% tabs %}

{% highlight c# %}

	rangeSlider.ToolTipPlacement = ToolTipPlacement.None;
	
{% endhighlight %}

{% endtabs %}

## Tooltip color

`TooltipTextColor` - Used to change the tooltip text color.
`TooltipBackgroundColor` - Used to change the tooltip background color.


