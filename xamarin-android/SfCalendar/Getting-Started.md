---
layout: post
title: Getting Started with Syncfusion Calendar control for Xamarin.Android
description: A quick tour to initial users on Syncfusion calendar control Xamarin.Android platform 
platform: Xamarin.Android
control: Calendar
documentation: ug
---

# Getting Started

This section explains you the steps required to render the [SfCalendar](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Calendar.SfCalendar.html) control, to change selection mode, set min max dates and black out dates for the control. This section covers only the minimal features that you need to know to get started with the `SfCalendar`.

## Referencing Essential Studio Components in Your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib

N> Assemblies are available in unzipped package location in Mac.

Add the following assembly references to the Android project,

android\Syncfusion.SfCalendar.Android.dll

## Initializing the SfCalendar

* Adding namespace for the added assemblies.

{% highlight C# %}

using Com.Syncfusion.Calendar;

{% endhighlight %}

* Now add the `SfCalendar` control with a required optimal name by using the included namespace.

{% highlight C# %}
	
public class MainActivity : Activity
{
	protected override void OnCreate(Bundle savedInstanceState)
	{
		base.OnCreate(savedInstanceState);
		SfCalendar sfCalendar = new SfCalendar(this);
		SetContentView(sfCalendar);
	}
}

{% endhighlight %}

### Enabling Multiple Selection 

Dates can be selected by making a touch on month view cells. The default Selection mode is Single which allows user to select one date at a time. SfCalendar provides support to select dates in three modes such as Single , Multiple and Range selection.

To enable multiple selection, Change the selection type using `SelectionMode` property.

N> For getting SelectionMode enum values  , need to refer `using Com.Syncfusion.Calendar.Enums` assembly.

{% highlight c# %}

public class MainActivity : Activity
{
	protected override void OnCreate(Bundle savedInstanceState)
	{
		base.OnCreate(savedInstanceState);
		SfCalendar sfCalendar = new SfCalendar(this);
		sfCalendar.SelectionMode = SelectionMode.MultiSelection;
		SetContentView(sfCalendar);
	}
}
{% endhighlight %}

### Setting blackout dates

In `SfCalendar`, `BlackoutDates` refers the disabled dates that restrict the user from selecting it. These dates will be marked with slanted Stripes.

For instance add all the holiday dates to blackout dates property.

{% highlight c# %}

public class MainActivity : Activity
{
	protected override void OnCreate(Bundle savedInstanceState)
	{
		base.OnCreate(savedInstanceState);

		SfCalendar sfCalendar = new SfCalendar(this);
		List<Date> blackoutDateCollection = new List<Date>();

		Calendar currentDate = Calendar.Instance;
		Calendar blockedDate1 = (Calendar)currentDate.Clone();
		blockedDate1.Set(currentDate.Get(CalendarField.Year),
		currentDate.Get(CalendarField.Month),
		currentDate.Get(CalendarField.Date) + 1);

		Calendar blockedDate2 = (Calendar)currentDate.Clone();
		blockedDate2.Set(currentDate.Get(CalendarField.Year),
		currentDate.Get(CalendarField.Month),
		currentDate.Get(CalendarField.Date) + 2);

		Calendar blockedDate3 = (Calendar)currentDate.Clone();
		blockedDate3.Set(currentDate.Get(CalendarField.Year),
		currentDate.Get(CalendarField.Month),
		currentDate.Get(CalendarField.Date) + 3);

		blackoutDateCollection.Add(blockedDate1.Time);
		blackoutDateCollection.Add(blockedDate2.Time);
		blackoutDateCollection.Add(blockedDate3.Time);

		sfCalendar.BlackoutDates = blackoutDateCollection;
		SetContentView(sfCalendar);
	}
}
{% endhighlight %}

### Restricting Dates with Minimum and Maximum range

Visible dates can be restricted between certain range of dates using `MinDate` and `MaxDate` properties available in `SfCalendar` control. It is applicable in all the calendar views.

{% highlight c# %}

SfCalendar sfCalendar = new SfCalendar(this);
Calendar minCalendar = Calendar.Instance;
minCalendar.Set(2016, 9, 1);
Calendar maxCalendar = Calendar.Instance;
maxCalendar.Set(2020, 9, 1);
sfCalendar.MinDate = minCalendar;
sfCalendar.MaxDate = maxCalendar;
SetContentView(sfCalendar);

{% endhighlight %}

![OverView image of Xamarin.Android Calendar](images/xamarin.android-calendar-overview.png)
