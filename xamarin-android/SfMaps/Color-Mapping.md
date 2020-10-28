---
layout: post
title: Color mapping
description: This section describes about the color mapping.
platform: Xamarin.Android
control: SfMaps
documentation: ug
---
# Color mapping

The color mapping support enables the customization of shape colors based on the underlying value of shape received from the bounded data.

Maps provide two types of color mapping

* Equal color mapping
* Range Color mapping

## Equal color mapping

It is used to differentiate the shape’s fill based on its underlying value and color using the [`Value`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Maps.EqualColorMapping.html#Com_Syncfusion_Maps_EqualColorMapping_Value) and [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Maps.ColorMapping.html#Com_Syncfusion_Maps_ColorMapping_Color) properties.

{% tabs %}

{% highlight c# %}

  SfMaps maps = new SfMaps(this);
  maps.SetBackgroundColor(Color.White);

  ShapeFileLayer layer = new ShapeFileLayer();
  layer.Uri = "usa_state.shp";
  layer.DataSource = viewModel.Data;
  layer.ShapeIdTableField = "STATE_NAME";
  layer.ShapeIdPath = "State";
  maps.Layers.Add(layer);

  EqualColorMapping colorMapping = new EqualColorMapping();
  colorMapping.Color = Color.ParseColor("#D84444");
  colorMapping.Value = "Romney";

  EqualColorMapping colorMapping1 = new EqualColorMapping();
  colorMapping1.Color = Color.ParseColor("#316DB5");
  colorMapping1.Value = "Obama";

  ShapeSetting shapeSetting = new ShapeSetting();
  shapeSetting.ShapeValuePath = "Candidate";
  shapeSetting.ShapeColorValuePath = "Candidate";
  shapeSetting.ColorMapping.Add(colorMapping);
  shapeSetting.ColorMapping.Add(colorMapping1);
  layer.ShapeSettings = shapeSetting;

  SetContentView(maps);

{% endhighlight %}

{% endtabs %}

![Equal color mapping image](Images/ColorMapping_img1.jpeg)

## Range color mapping

It is used to differentiate the bubble fill based on its under-bound value and color ranges. 

The [`From`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Maps.RangeColorMapping.html#Com_Syncfusion_Maps_RangeColorMapping_From) and [`To`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Maps.RangeColorMapping.html#Com_Syncfusion_Maps_RangeColorMapping_To) properties are used to define the color range and color for the range that can be specified using the [`Color`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Maps.ColorMapping.html#Com_Syncfusion_Maps_ColorMapping_Color) property.

{% tabs %}

{% highlight c# %}

  SfMaps maps = new SfMaps(this);
  maps.SetBackgroundColor(Color.White);

  ShapeFileLayer layer = new ShapeFileLayer();
  layer.Uri = "usa_state.shp";
  layer.DataSource = viewModel.Data;
  layer.ShapeIdTableField = "STATE_NAME";
  layer.ShapeIdPath = "State";
  maps.Layers.Add(layer); 

  RangeColorMapping rangeColorMapping = new RangeColorMapping();
  rangeColorMapping.From = 30;
  rangeColorMapping.To = 70;
  rangeColorMapping.Color = Color.ParseColor("#397D02");

  RangeColorMapping rangeColorMapping1 = new RangeColorMapping();
  rangeColorMapping1.From = 15;
  rangeColorMapping1.To = 30;
  rangeColorMapping1.Color = Color.ParseColor("#316DB5");

  RangeColorMapping rangeColorMapping2 = new RangeColorMapping();
  rangeColorMapping2.From = 0;
  rangeColorMapping2.To = 15;
  rangeColorMapping2.Color = Color.ParseColor("#D84444");

  ShapeSetting shapeSetting = new ShapeSetting();
  shapeSetting.ShapeColorValuePath = "Electors";
  shapeSetting.ColorMapping.Add(rangeColorMapping);
  shapeSetting.ColorMapping.Add(rangeColorMapping1);
  shapeSetting.ColorMapping.Add(rangeColorMapping2);
  layer.ShapeSettings = shapeSetting;

  SetContentView(maps);   

{% endhighlight %}

{% endtabs %}

![Range color mapping image](Images/ColorMapping_img2.jpeg)


