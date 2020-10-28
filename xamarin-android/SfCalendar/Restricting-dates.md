---
layout: post
title: Blackout Dates | SfCalendar | Xamarin.Android | Syncfusion
description: Learn how to add black out dates for calendar
platform: Xamarin.Android
control: Calendar
documentation: ug
---

# Restricting Dates from Selection

## Min Max dates

Visible dates can be restricted between certain range of dates using [MinDate](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Calendar.SfCalendar.html#Com_Syncfusion_Calendar_SfCalendar_MinDate) and [MaxDate](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Calendar.SfCalendar.html#Com_Syncfusion_Calendar_SfCalendar_MaxDate) properties available in `SfCalendar` control. It is applicable in all the calendar views.

The inline feature in month view will work only within the min max date range.

Beyond the min max date range, following restrictions will be applied.

* Date navigations features of MoveToDate will be restricted.
* Cannot swipe the control using touch gesture.
* Selection does not work for month view. 
* The tapped delegates will not be triggered while tapped on the month cell.  

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

## Blackout dates

In `SfCalendar`, blackout dates refers the disabled dates that restrict the user from selecting it. These dates will be marked with slanted Stripes. 

The blackout dates can be achieved in two ways. 

* A date collection can be provided to set the [BlackoutDates](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Calendar.SfCalendar.html#Com_Syncfusion_Calendar_SfCalendar_BlackoutDates) property. This is useful when one wants to block dates where holidays or any other events occur. 

* By invoking the [AddDatesInPast](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Calendar.SfCalendar.html#Com_Syncfusion_Calendar_SfCalendar_AddDatesInPast) method, all past dates will be blacked out till current date.

{% highlight c# %}

SfCalendar sfCalendar = new SfCalendar(this);
List<Date> blackoutDateCollection = new List<Date>();

Calendar currentDate = Calendar.Instance;
Calendar blockedDate1 = (Calendar)currentDate.Clone();
blockedDate1.Set(currentDate.Get(CalendarField.Year),
                  currentDate.Get(CalendarField.Month),
                  currentDate.Get(CalendarField.Date));

for (int i = 1; i <= 5;i++)
{
      blockedDate1.Set(currentDate.Get(CalendarField.Year),
      currentDate.Get(CalendarField.Month),
      currentDate.Get(CalendarField.Date)-10 + i);
     blackoutDateCollection.Add(blockedDate1.Time);
}
sfCalendar.BlackoutDates = blackoutDateCollection;
SetContentView(sfCalendar);

{% endhighlight %}

![Blackout Dates support in Xamarin.Android Calendar](images/xamarin.android-calendar-blackout_dates.png)                                        

N> This support is enabled only in month view and the dates that consists inline events will also be disabled, when they are blacked out.

### Customize the blackout dates Color
You can customize the color of [BlackoutDates](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Calendar.SfCalendar.html#Com_Syncfusion_Calendar_SfCalendar_BlackoutDates) in month view mode using the [BlackOutColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Calendar.MonthViewSettings.html#Com_Syncfusion_Calendar_MonthViewSettings_BlackoutColor) property of [MonthViewSettings](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Calendar.MonthViewSettings.html).

{% tabs %}
{% highlight c# %}
SfCalendar calendar = new SfCalendar(this); 
MonthViewSettings monthViewSettings = new MonthViewSettings();
monthViewSettings.BlackOutColor = Color.Red;
calendar.MonthViewSettings = monthViewSettings;
SetContentView(calendar);
{% endhighlight %}
{% endtabs %}
