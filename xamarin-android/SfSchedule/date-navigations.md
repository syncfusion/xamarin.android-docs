---
layout: post
title: Dates, Navigations and Gestures of Syncfusion Xamarin.Android Schedule 
description: How to Navigate date, enable or disable navigation and other functionalities of Schedule control in Xamarin.Android.
platform: Xamarin.Android
control: SfSchedule
documentation: ug
---


# Date Navigations

## Enabling Navigation 
By default, Schedule views can be moved backwards and forwards using touch swipe gesture. This navigation gesture can be enabled or disabled by setting [EnableNavigation](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_EnableNavigation) property of `SfSchedule`. By default, it is enabled.

{% tabs %}
{% highlight c# %}
//disabling navigation gesture
schedule.EnableNavigation = false;
{% endhighlight %}
{% endtabs %}


## Programmatically change to specific dates 
Visible dates can be moved to specific date using [MoveToDate](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_MoveToDate) property available in `SfSchedule`. It will move to any specific date if the schedule view is Day View, similarly it will move to the specific week if it is week view and to specific month if it is month view

{% tabs %}
{% highlight c# %}
Calendar moveToSpecificDate = Calendar.Instance;
moveToSpecificDate.Set(2017, 7, 25);
schedule.MoveToDate = moveToSpecificDate;
{% endhighlight %}
{% endtabs %}


>**NOTE**
The specified date should lies between `MinDisplayDate` and `MaxDisplayDate` , if  the specified date is greater than `MaxDisplayDate` then the view moved to `MaxDisplayDate` similarly if the specified date is lesser than the `MinDisplayDate` then the view moved to `MinDisplayDate`.

## Programmatically change to adjacent dates.
By default the date can be navigated to next and previous view using touch gesture, by swiping the control in right to left and right to left direction. The view can be also changed programmatically using [Forward](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_Forward) and [Backward](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_Backward) method available in `SfSchedule`. 

*  	Forward
*	Backward

### Forward
You can use the `Forward` method for viewing the next immediate visible dates in the SfSchedule. It will move to next month if the schedule view is month, similarly it will move to next week for week view and next day for day view.

{% tabs %}
{% highlight c# %}
//Viewing next immediate visible dates
schedule.Forward();
{% endhighlight %}
{% endtabs %}


>**NOTE**
It can be navigated until it reaches the Min Max dates.

### Backward
You can use the `Backward` method for viewing the previous immediate visible dates in the `SfSchedule`. It will move to previous month if the schedule view is month, similarly it will move to previous week for week view and previous day for day view.

{% tabs %}
{% highlight c# %}
//Viewing previous immediate visible dates
schedule.Backward();
{% endhighlight %}
{% endtabs %}


>**NOTE**
It can be navigated until it reaches the Min Max dates.

## Range for visible dates
Visible dates can be restricted between certain range of dates, using [MinDisplayDate](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_MinDisplayDate)  and [MaxDisplayDate](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_MaxDisplayDate)  property in `SfSchedule`. It is applicable in all the schedule views.

### Minimum Display Date
`MinDisplayDate` will restrict date navigations features of `Backward`, `MoveToDate` and also can’t swipe the control using touch gesture beyond the min max date range. Thus, Inline and selection feature in month view will works only within the min max date range.

{% tabs %}
{% highlight c# %}
Calendar currentDate = Calendar.Instance;
Calendar minDate = (Calendar)currentDate.Clone();
minDate.Set(2015, 5, 12);
schedule.MinDisplayDate = minDate;
{% endhighlight %}
{% endtabs %}


### Maximum Display Date
`MaxDisplayDate` will restrict date navigations features of `Forward`, `MoveToDate` and also can’t swipe the control using touch gesture beyond the max date range. Thus, Inline and selection in month view will works only within the max date range.

{% tabs %}
{% highlight c# %}
Calendar currentDate = Calendar.Instance;
Calendar maxDate = (Calendar)currentDate.Clone();
maxDate.Set(2025, 11, 12);
schedule.MaxDisplayDate = maxDate;
{% endhighlight %}
{% endtabs %}

## VisibleDatesChanged event

You can get the visible dates of the Schedule using [VisibleDatesChanged](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html) event in `SfSchedule`. It is applicable in all the schedule views.The event handler receives an argument of type [VisibleDatesChangedEventArgs](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.VisibleDatesChangedEventArgs.html) containing [VisibleDates](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.VisibleDatesChangedEventArgs.html#Com_Syncfusion_Schedule_VisibleDatesChangedEventArgs_VisibleDates).

{% tabs %}
{% highlight c# %}
schedule.VisibleDatesChanged += Schedule_VisibleDatesChanged;

...

void Schedule_VisibleDatesChanged(object sender, VisibleDatesChangedEventArgs e)
{
    var visibleDates = e.VisibleDates;
}
{% endhighlight %}
{% endtabs %}

`VisibleDatesChanged` event will be triggered when view is swiped back or forth and also when schedule view is switched dynamically.

You can add appointments on demand based on the visible date range in this event by setting Appointments property to schedule in the VisibleDatesChanged event.

{% tabs %}
{% highlight c# %}
void Schedule_VisibleDatesChanged(object sender, VisibleDatesChangedEventArgs e)
{
    schedule.Appointments = scheduleAppointmentCollection;
}
{% endhighlight %}
{% endtabs %}


You can also move to specific time of the day or current time of day when view is swiped by setting specific time in MoveToDate property in the VisibleDatesChanged event. Such that when the schedule view is swiped, it moves to the mentioned time.  

{% tabs %}
{% highlight c# %}
schedule.VisibleDatesChangedEvent += Schedule_VisibleDatesChangedEvent;

...

void Schedule_VisibleDatesChangedEvent(object sender, VisibleDatesChangedEventArgs e)
{
    var visibleDate = e.VisibleDates[0];
    Calendar moveToSpecificTime = (Calendar)visibleDate.Clone();

    //setting start time for the event
    moveToSpecificTime.Set(visibleDate.Get(CalendarField.Year),
                           visibleDate.Get(CalendarField.Month),
                           visibleDate.Get(CalendarField.DayOfMonth),
                           visibleDate.Get(CalendarField.HourOfDay),
                           visibleDate.Get(CalendarField.Minute),
                           visibleDate.Get(CalendarField.Second));
    schedule.MoveToDate = moveToSpecificTime;
}
{% endhighlight %}
{% endtabs %}
