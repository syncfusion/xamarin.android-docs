---
layout: post
title: Customization of Syncfusion Calendar control in Xamarin.Android
description: How to Perform an operation and load Sfcalendar from .axml layout.
platform: Xamarin.Android
control: Calendar
documentation: ug
---

# Customization of Calendar control

## How to Perform an Operation while a Calendar Cell is Tapped?

We can perform operation while the Calendar cell is Tapped using [CalendarTapped](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Calendar.SfCalendar.html) event. CalendarTapped event returns the date selected and the Appointments that are associated with the date selected.

{% highlight c# %}
	
 sfCalendar.CalendarTapped += (object sender, CalendarTappedChangedEventArgs e) => 
   {
     // do the operation while tapping the date cell.
   };

{% endhighlight %}

## How to Perform an Operation while Dealing with Appointments?

[InlineEventToggled](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Calendar.SfCalendar.html) event returns the selected date along with the appointments it carries. Using this event user can perform operation while dealing with appointments.

{% highlight c# %}
	
sfCalendar.InlineEventToggled += (object sender, InlineEventToggledEventArgs e) =>
{
    // do the operation while Dealing with Appointments
};

{% endhighlight %}

## How to Perform an Operation when Navigate to Next Month?

User defined operation can be performed using [MonthChanged](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Calendar.SfCalendar.html) event when navigating to next month. This event returns the details about current value and previous value of month.

{% highlight c# %}
	
sfCalendar.MonthChanged += (object sender, MonthChangedEventArgs e) =>
{
    // do the operation while month has been changed.
};

{% endhighlight %}

## How to Customize Cell or Month View?

[DrawMonthCell](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Calendar.SfCalendar.html) event allows us to customize the month view in SfCalendar control. It returns MonthCell args

{% highlight c# %}

sfCalendar.DrawMonthCell += (object sender, DrawMonthCellEventArgs e) =>
{
    //Customize Cell or Month View
};

{% endhighlight %}

## How to Customize Year View?

[DrawYearCell](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Calendar.SfCalendar.html) event allows us to customize the year view in  SfCalendar control. It returns YearCell args

{% highlight c# %}

sfCalendar.DrawYearCell += (object sender, DrawYearCellEventArgs e) =>
{
    //customize the Year View
};

{% endhighlight %}


## How to Perform an Operation when the Selected Date Get Changed?

We can perform an operation when the selected date get changed using [SelectionChanged](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Calendar.SfCalendar.html) event which returns the dates selected and dates deselected from the SfCalendar.

{% highlight c# %}

sfCalendar.SelectionChanged += (object sender, SelectionChangedEventArgs e) =>
{
    //perform an Operation when the Selected Date Get Changed
};

{% endhighlight %}

## How to create Calendar control in .axml Layout file.?

We can create a `SfCalendar` control in .axml file and accessing its property in .cs file.

### Create a control in .axml file

Reference the `SfCalendar` control view using the fully qualified name like `com.syncfusion.calendar.SfCalendar`.

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
android:orientation="vertical"
android:layout_width="match_parent"
android:layout_height="match_parent">
        <com.syncfusion.calendar.SfCalendar
            android:id="@+id/sfCalendar"
            android:layout_width="match_parent"
            android:layout_height="match_parent" />
</LinearLayout>

{% endhighlight %}

### In MainActivity.cs file

{% highlight C# %}

public class MainActivity : Activity
{
    protected override void OnCreate(Bundle savedInstanceState)
    {
    
        base.OnCreate(savedInstanceState);

        SetContentView(Resource.Layout.Main);

        SfCalendar calendar = (SfCalendar)FindViewById(Resource.Id.sfCalendar);

        calendar.ShowEventsInline = true;

        CalendarEventCollection eventsCollection = new CalendarEventCollection();
        CalendarInlineEvent events = new CalendarInlineEvent();

        Calendar currentDate = Calendar.Instance;
        Calendar startTime = (Calendar)currentDate.Clone();

        //setting start time for the event
        startTime.Set(currentDate.Get(CalendarField.Year),
        currentDate.Get(CalendarField.Month),
        currentDate.Get(CalendarField.DayOfMonth),
                                10, 0, 0);

        Calendar endTime = (Calendar)currentDate.Clone();

        //setting end time for the event
        endTime.Set(currentDate.Get(CalendarField.Year),
        currentDate.Get(CalendarField.Month),
        currentDate.Get(CalendarField.DayOfMonth),
                                12, 0, 0);

        events.StartTime = startTime;
        events.EndTime = endTime;
        events.Subject = "Business Meeting";
        events.Color = Color.Red;

        //Adding Schedule appointment in schedule appointment collection
        eventsCollection.Add(events);

        //Add collection of events as source of SfCalendar
        sfCalendar.DataSource = eventsCollection;
    }
}

{% endhighlight %}
