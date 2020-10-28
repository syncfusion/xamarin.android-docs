---
layout: post
title: Overview | SfPullToRefresh | Xamarin.Android | Syncfusion
description: Xamarin.Android SfPullToRefresh is a refresh control that allows to interact and refresh the loaded view as pullable content.
platform: Xamarin.Android
control: SfPullToRefresh
documentation: ug
--- 

# Overview of Xamarin.Android PullToRefresh (SfPullToRefresh)

SfPullToRefresh is a refresh control that allows to interact and refresh the loaded view as pullable content. It supports loading complex and custom layouts that can be refreshed programmatically or through interaction.

## Key Features:

* The view can be refreshed programmatically. Use [SfPullToRefresh.StartRefreshing()](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_StartRefreshing) to start the refreshing programmatically and [SfPullToRefresh.EndRefreshing()](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_EndRefreshing) to end the refreshing programmatically.

* There are two types of transition for refreshing. You can toggle between the transition using the  [SfPullToRefresh.TransitionType](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_TransitionType) property. 

* The progress view can be customized. Size, background color, stroke color, and width of the stroke can be customized using the following properties: 
  * [SfPullToRefresh.RefreshContentRadius](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_RefreshContentRadius)
  * [SfPullToRefresh.ProgressBackgroundColor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_ProgressBackgroundColor)
  * [SfPullToRefresh.ProgressStrokeColor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_ProgressStrokeColor)
  * [SfPullToRefresh.ProgressStrokeWidth](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfPullToRefresh.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_SfPullToRefresh_ProgressStrokeWidth)

<div style="text-align:center" markdown="1">
![WeatherData Refresh Image in Xamarin.Android PullToRefresh](overview_images/WeatherData_Refresh_Android.gif)
</div>
