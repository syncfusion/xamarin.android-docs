---
layout: post
title: Treemap elements in Syncfusion TreeMap control for Xamarin.Android
description: Describes the elements in the tree map control
platform: Xamarin.Android
control: TreeMap
documentation: ug
---

# TreeMap Elements

The TreeMap contains the following elements:

* Legends
* Headers
* Labels

## Legend

You can set the color value of leaf nodes using the [`LegendSettings`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Treemap.SfTreeMap.html#Com_Syncfusion_Treemap_SfTreeMap_LegendSettings) property. This legend is appropriate only for the tree map whose leaf nodes are colored using [`RangeColorMapping`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Treemap.RangeColorMapping.html).

The visibility of legend can be enabled by setting the [`ShowLegend`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Treemap.LegendSetting.html#Com_Syncfusion_Treemap_LegendSetting_ShowLegend) property to true.

### TreeMap legends

You can set the size of legend icons by setting the [`IconSize`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Treemap.LegendSetting.html#Com_Syncfusion_Treemap_LegendSetting_IconSize) property of `LegendSettings` in TreeMap.

### Labels for legends

You can customize the labels of the legend items using the [`LegendLabel`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Treemap.Range.html#Com_Syncfusion_Treemap_Range_LegendLabel) property of [`RangeColorMapping`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Treemap.RangeColorMapping.html). 

{% tabs %}

{% highlight c# %}

    LegendSetting legendSettings = new LegendSetting();
    legendSettings.IconSize = new Size(15, 15);
            legendSettings.ShowLegend = true;
            legendSettings.LegendSize = new Size(700, 45);
            legendSettings.LabelStyle = new Style() { TextColor = Color.Black };
            treeMap.LegendSettings = legendSettings;

{% endhighlight %}

{% endtabs %} 

![Treemap legend](Getting-Started_images/GettingStarted.jpg)

## Header

You can set headers for each level by setting the [`ShowHeader`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Treemap.TreeMapLevel.html#Com_Syncfusion_Treemap_TreeMapLevel_ShowHeader) property of each **TreeMap** level. The [`HeaderHeight`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Treemap.TreeMapLevel.html#Com_Syncfusion_Treemap_TreeMapLevel_HeaderHeight) property helps you set the height of header, and the [`GroupPath`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Treemap.TreeMapFlatLevel.html#Com_Syncfusion_Treemap_TreeMapFlatLevel_GroupPath) value determines the header value. 

{% tabs %}

{% highlight c# %}

          TreeMapFlatLevel flatLevel = new TreeMapFlatLevel();
            flatLevel.HeaderHeight = 20;
            flatLevel.GroupPath = "Continent";
            flatLevel.GroupGap = 5;
            flatLevel.ShowHeader = true;
            flatLevel.GroupStrokeColor = Color.Gray;
            flatLevel.GroupStrokeWidth = 1;
            flatLevel.HeaderStyle = new Style() { TextColor = Color.Black };
            treeMap.Levels.Add(flatLevel);

{% endhighlight %} 

{% endtabs %} 

![TreeMap header](Getting-Started_images/Trim.png)

## Data labels

The [`ShowLabels`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Treemap.LeafItemSetting.html#Com_Syncfusion_Treemap_LeafItemSetting_ShowLabels) property is used to enable or disable the labels in leaf nodes. The [`LabelPath`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Treemap.LeafItemSetting.html#Com_Syncfusion_Treemap_LeafItemSetting_LabelPath) property allows you to set values to labels.

{% tabs %}

{% highlight c# %}

            LeafItemSetting leafItemSetting = new LeafItemSetting();
            leafItemSetting.ShowLabels = true;
            leafItemSetting.Gap = 2;
            leafItemSetting.LabelPath = "Country";
            treeMap.LeafItemSettings = leafItemSetting;
 
{% endhighlight %}

{% endtabs %} 

![Providing visibility for data labels in TreeMap](Getting-Started_images/Trim.png)

### Avoid overlap in data labels

The [`OverflowMode`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Treemap.LeafItemSetting.html#Com_Syncfusion_Treemap_LeafItemSetting_OverflowMode) property aligns data labels within leaf node boundaries using the `Trim`, `Wrap`, and `Hide` options. The default value of the `OverflowMode` property is Trim.

#### Trim

You can trim the data labels inside the leaf node boundaries using the `Trim` option.

{% tabs %}

{% highlight c# %}

   treeMap.LeafItemSettings.OverflowMode = LabelOverflowMode.Trim;
 
{% endhighlight %}

{% endtabs %}

![Data label trim support in Xamarin.Forms TreeMap](Getting-Started_images/Trim.png)

#### Wrap

You can wrap the data labels inside the leaf node boundaries using the `Wrap` option.

{% tabs %}

{% highlight c# %}

    treeMap.LeafItemSettings.OverflowMode = LabelOverflowMode.Wrap;
 
{% endhighlight %}

{% endtabs %}

![Data label wrap support in Xamarin.Forms TreeMap](Getting-Started_images/Wrap.png)

#### Hide

You can hide the data labels inside the leaf node boundaries using the `Hide` option. 

{% tabs %}

{% highlight c# %}

   treeMap.LeafItemSettings.OverflowMode = LabelOverflowMode.Hide;
 
{% endhighlight %}

{% endtabs %}

![Data label hide support in TreeMap](Getting-Started_images/Hide.png)

### Customize data labels

You can customize the data labels using the [`LabelStyle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Treemap.LeafItemSetting.html#Com_Syncfusion_Treemap_LeafItemSetting_LabelStyle) property of LeafItemSettings. The text color, size, and style can be customized using the [`TextColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Treemap.Style.html#Com_Syncfusion_Treemap_Style_TextColor), [`TextSize`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Treemap.Style.html#Com_Syncfusion_Treemap_Style_TextSize), and [`TextStyle`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Treemap.Style.html#Com_Syncfusion_Treemap_Style_TextStyle) properties, respectively.

{% tabs %}

{% highlight c# %}

         treeMap.LeafItemSettings.LabelStyle = new Style() { TextColor = Color.Red, TextSize = 12 };
 
{% endhighlight %}

{% endtabs %}

![Customizing the data labels support in TreeMap](Getting-Started_images/LabelCustomization.png)
