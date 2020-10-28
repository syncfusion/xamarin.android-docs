---
layout: post
title: Animation feature of Essential Xamarin.Android SfSunburstChart
description: This section describes the animation feature of sunburst chart.
platform: Xamarin.Android
control: SfSunburstChart
documentation: ug
---

# Animation

The sunburst chart provides animation on loading and whenever the item source changes. Animation can be enabled by setting the [`EnableAnimation`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfSunburstChart.Android.SfSunburstChart.html#Syncfusion_SfSunburstChart_Android_SfSunburstChart_EnableAnimation) property to true.

The following code shows enabling animation.

{% tabs %} 

{% highlight C# %} 

  SfSunburstChart sunburstChart = new SfSunburstChart(this);

  SunburstViewModel dataModel = new SunburstViewModel();
  sunburstChart.ItemsSource = dataModel.DataSource;          
  sunburstChart.ValueMemberPath = "EmployeesCount";

  sunburstChart.EnableAnimation = true;
  sunburstChart.DataLabel.ShowLabel = true;            

  sunburstChart.Levels.Add(new SunburstHierarchicalLevel() { GroupMemberPath = "Country" });
  sunburstChart.Levels.Add(new SunburstHierarchicalLevel() { GroupMemberPath = "JobDescription" });
  sunburstChart.Levels.Add(new SunburstHierarchicalLevel() { GroupMemberPath = "JobGroup" });
  sunburstChart.Levels.Add(new SunburstHierarchicalLevel() { GroupMemberPath = "JobRole" });

  SetContentView(sunburstChart);     
          
{% endhighlight %}

{% endtabs %} 

## Duration

Animation duration can be controlled using the [`AnimationDuration`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfSunburstChart.Android.SfSunburstChart.html#Syncfusion_SfSunburstChart_Android_SfSunburstChart_AnimationDuration) property.

{% tabs %} 

{% highlight C# %} 

  SfSunburstChart sunburstChart = new SfSunburstChart(this);

  SunburstViewModel dataModel = new SunburstViewModel();
  sunburstChart.ItemsSource = dataModel.DataSource;          
  sunburstChart.ValueMemberPath = "EmployeesCount";

  sunburstChart.EnableAnimation = true;
  sunburstChart.AnimationDuration = 2;
  sunburstChart.DataLabel.ShowLabel = true;            

  sunburstChart.Levels.Add(new SunburstHierarchicalLevel() { GroupMemberPath = "Country" });
  sunburstChart.Levels.Add(new SunburstHierarchicalLevel() { GroupMemberPath = "JobDescription" });
  sunburstChart.Levels.Add(new SunburstHierarchicalLevel() { GroupMemberPath = "JobGroup" });
  sunburstChart.Levels.Add(new SunburstHierarchicalLevel() { GroupMemberPath = "JobRole" });

  SetContentView(sunburstChart);  

{% endhighlight %}

{% endtabs %} 

The following screenshot depicts animation of the sunburst chart with the specified duration.

![](Animation_images/Animate.gif)

