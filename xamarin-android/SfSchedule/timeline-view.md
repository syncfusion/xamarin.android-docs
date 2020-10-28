---

layout: post
title: Timeline view scheduler | Xamarin.Android | Syncfusion
description: Xamarin.Android scheduler timeline view displays the dates in a horizontal time axis with desired days count, displays events accurately across the time slots.
platform: xamarin.Android
control: SfSchedule
documentation: ug

---

# Timeline view

`TimelineView` displays the dates in horizontal time axis with the desired day's count. You can see the past or future dates by scrolling to the right or left. Each view displays events accurately across the time slots with an intuitive drag-and-drop feature. It provides support to highlight the selected region of time slots and handle interaction.

{% tabs %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.Timeline;
{% endhighlight %}
{% endtabs %}

![Timeline view in xamarin android](timeline-view-images/xamarin-android-timeline-view.png)

## Timeline view days count

You can customize the number of days in `TimelineView` using the [DaysCount](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.TimelineViewSettings.html#Com_Syncfusion_Schedule_TimelineViewSettings_DaysCount) property of [TimelineViewSettings](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_TimelineViewSettings). By default, value of the timeline days count is -1, and single day will be visible.

{% tabs %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.Timeline;
//Creating new instance of TimelineViewSettings
TimelineViewSettings timelineViewSettings = new TimelineViewSettings();
//Customizing days count
timelineViewSettings.DaysCount = 10;
schedule.TimelineViewSettings = timelineViewSettings;
{% endhighlight %}
{% endtabs %}

![Timeline view in xamarin android](timeline-view-images/xamarin-android-timeline-view-days-count.png)

## Timeline view based on day, week, work week, and month.
 
You can achieve timeline day, timeline week, timeline work week, and timeline month view with the default value of `DaysCount` by dynamically switching between day, week, work week, and month view to timeline view with respective visible dates. 
 
>**NOTE**
For other value of `DaysCount`, only timeline view visible dates will be displayed as mentioned days count on dynamic view switching.

## Customized working hours

You can customize the [StartHour](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.TimelineViewSettings.html#Com_Syncfusion_Schedule_TimelineViewSettings_StartHour) and [EndHour](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.TimelineViewSettings.html#Com_Syncfusion_Schedule_TimelineViewSettings_EndHour) properties of `TimelineView` to show only the required time duration for end users. You can also set `StartHour` and `EndHour` in double value, which will be converted to time to show the required time duration in minutes. The default value for `StartHour` and `EndHour` value is 0 to 24 to show all the time slots in `TimelineView`.

{% tabs %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.Timeline;
//Creating new instance of TimelineViewSettings
TimelineViewSettings timelineViewSettings = new TimelineViewSettings();
timelineViewSettings.StartHour = 09;
timelineViewSettings.EndHour = 13;
schedule.TimelineViewSettings = timelineViewSettings;
{% endhighlight %}
{% endtabs %}

![Working hours customization in xamarin android Timeline view](timeline-view-images/xamarin-android-timeline-view-time-slot-customisation.png)

>**NOTE**
* `StartHour` must be greater than or equal to 0 and `EndHour` must be lesser than or equal to 24, otherwise `InvalidDataException` will be thrown.
* `EndHour` value must be greater than `StartHour`, otherwise `InvalidDataException` will be thrown.
* Schedule UI such as Appointments and NonAccessibleBlocks which does not fall within the `StartHour` and `EndHour` will not be visible and if it falls partially, it will be clipped.
* No need to specify the decimal point values for `StartHour` and `EndHour`, if you don’t want to set the minutes.
* The number of time slots will be calculated based on total minutes of a day and time interval (total minutes of a day ((start hour - end hour) * 60) / time interval).
* If the custom time interval is given, then the number of time slots calculated based on given time interval should result in integer value, otherwise given time interval will be neglected and default time interval (60 minutes) will be considered.
* If the custom start hour and end hour is given, then the number of time slots calculated based on given start hour, end hour should result in integer value, otherwise given end hour will be rounded off. For example, if StartHour is 7.2 (07:12AM), EndHour is 18.6 (06:36AM) and TimeInterval is 60 minutes, then EndHour will be rounded off to 18.2 (06:12PM).

## Special time regions

You can restrict user interaction such as selection and highlight specific region of time in `TimelineView` by adding `SpecialTimeRegion` in the [SpecialTimeRegions](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_SpecialTimeRegions) property of `SfSchedule`. You need to set the [StartHour](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.TimeRegionSettings.html#Com_Syncfusion_Schedule_TimeRegionSettings_StartHour) and [EndHour](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.TimeRegionSettings.html#Com_Syncfusion_Schedule_TimeRegionSettings_EndHour) properties of [TimeRegionSettings](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.TimeRegionSettings.html) to create `SpecialTimeRegion`. You can also set `StartHour` and `EndHour` in double value, which will be converted to time to show the required time duration in minutes. By default, the values of `StartHour` and `EndHour` are 0.

### Special time region appearance

You can customize the appearance of `SpecialTimeRegion` using the [Color](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.TimeRegionSettings.html#Com_Syncfusion_Schedule_TimeRegionSettings_Color) and [TextColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.TimeRegionSettings.html#Com_Syncfusion_Schedule_TimeRegionSettings_TextColor) properties of `TimeRegionSettings`.

### Selection restriction in time slots

You can enable/disable the touch interaction of `SpecialTimeRegion` using [CanEdit](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.TimeRegionSettings.html#Com_Syncfusion_Schedule_TimeRegionSettings_CanEdit) property of `TimeRegionSettings`. By default, its value is true.

{% tabs %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.Timeline;
ObservableCollection<TimeRegionSettings> specialTimeRegions = new ObservableCollection<TimeRegionSettings>();
//Setting Special time regions property
TimeRegionSettings timeRegionSettings = new TimeRegionSettings();
timeRegionSettings.StartHour = 12;
timeRegionSettings.EndHour = 13;
timeRegionSettings.Text = "Lunch";
timeRegionSettings.Color = Color.Rgb(234, 234, 234);
timeRegionSettings.TextColor = Color.Black;
timeRegionSettings.CanEdit = false;
specialTimeRegions.Add(timeRegionSettings);
schedule.SpecialTimeRegions = specialTimeRegions;
{% endhighlight %}
{% endtabs %}

![Special time region in xamarin android Timeline view](timeline-view-images/xamarin-android-timeline-view-special-time-region.png)

## Time interval

You can customize the interval of time slots in `TimelineView` by setting [TimeInterval](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_TimeInterval) property of `SfSchedule`.

{% tabs %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.Timeline; 
schedule.TimeInterval = 180;
{% endhighlight %}
{% endtabs %}

![Time interval in xamarin android Timeline view](timeline-view-images/xamarin-android-timeline-view-time-interval.png)

>**NOTE**
If you modify the `TimeInterval` value (in minutes), you need to change the time labels format by setting the `TimeFormat` as “hh:mm”. By default, `TimeFormat` is "hh a".


## Time interval height 

You can customize the interval height of time slots in `TimelineView` by setting the [TimeIntervalHeight](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_TimeIntervalHeight) property of `SfSchedule`.

{% tabs %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.Timeline; 
schedule.TimeIntervalHeight = 180;
{% endhighlight %}
{% endtabs %}

![Time interval height in xamarin android Timeline view](timeline-view-images/xamarin-android-timeline-view-time-interval-height.png)

## Nonworking days

You can add the non-working days in `TimelineView` using [NonWorkingsDays](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.TimelineViewSettings.html#Com_Syncfusion_Schedule_TimelineViewSettings_NonWorkingDays) property of `TimelineViewSettings`. By default, there is no non-working day in `TimelineView`.

{% tabs %}
{% highlight c# %}
var nonWorkingDays = new ObservableCollection<int>();
nonWorkingDays.Add(2);
nonWorkingDays.Add(6);
var timelineViewSettings = new TimelineViewSettings();
timelineViewSettings.NonWorkingDays = nonWorkingDays;
schedule.TimelineViewSettings = timelineViewSettings;
{% endhighlight %}
{% endtabs %}

## First day of week

By default, schedule control will be rendered with Sunday as the first day of the week. It can be customized to any day of the week using the `FirstDayOfWeek` property of `SfSchedule`.

{% tabs %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.Timeline; 
schedule.FirstDayOfWeek = 3;
{% endhighlight %}
{% endtabs %}

![First day of week in xamarin android Timeline view](timeline-view-images/xamarin-android-timeline-view-first-day-of-week.png)

>**NOTE**
In Timeline view, `FirstDayOfWeek` will be applied only when `DayCounts` property of `TimelineViewSettings` is 7.

## Appointment height

You can customize the height of the appointment in `TimelineView` using the [AppointmentHeight](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.TimelineViewSettings.html#Com_Syncfusion_Schedule_TimelineViewSettings_AppointmentHeight) property of `TimelineViewSettings`. By default, its value is 50.

{% tabs %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.Timeline;
//Create new instance of TimelineViewSettings
TimelineViewSettings timelineViewSettings = new TimelineViewSettings();
timelineViewSettings.AppointmentHeight = 100;
schedule.TimelineViewSettings = timelineViewSettings;
{% endhighlight %}
{% endtabs %}

![Appointment height in xamarin android Timeline view](timeline-view-images/xamarin-android-timeline-view-appointment-height.png)

>**NOTE**
When a greater number of appointments is added in the same time slot, appointment height will be calculated automatically without considering the `AppointmentHeight` property to display all the appointment in the view.

## View header tapped event

You can handle single tap action of ViewHeader using the `ViewHeaderTapped` event of `SfSchedule`. This event occurs when the `ViewHeader` is tapped. This event contains `ViewHeaderTappedEventArgs` argument, which holds the details of `Calendar` in it.

{% tabs %}
{% highlight c# %}
//Creating new instance of Schedule 
SfSchedule schedule = new SfSchedule(); 
schedule.ScheduleView = ScheduleView.Timeline; 
schedule.ViewHeaderTapped += OnViewHeaderTapped;
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
private void OnViewHeaderTapped(object sender, ViewHeaderTappedEventArgs e)
{
     var calendar = e.Calendar;
}
{% endhighlight %}
{% endtabs %}

## View header customization

You can customize the default appearance of view header in `TimelineView` by using `ViewHeaderStyle` property of `SfSchedule`.

{% tabs %}
{% highlight c# %}
//Create new instance of Schedule
SfSchedule schedule = new SfSchedule();
schedule.ScheduleView = ScheduleView.Timeline;
//Customize the schedule view header
ViewHeaderStyle viewHeaderStyle = new ViewHeaderStyle();
viewHeaderStyle.BackgroundColor = Color.Rgb(169, 177, 252);
viewHeaderStyle.DateTextColor = Color.Black;
schedule.ViewHeaderStyle = viewHeaderStyle;
{% endhighlight %}
{% endtabs %}

![View header customization in xamarin android Timeline view](timeline-view-images/xamarin-android-timeline-view-view-header-customization.png)


You can customize the height of `ViewHeader` in `TimelineView` by setting the `ViewHeaderHeight` property of `SfSchedule.`

{% tabs %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.Timeline; 
schedule.ViewHeaderHeight = 50;
{% endhighlight %}
{% endtabs %}

![View header height in xamarin android Timeline view](timeline-view-images/xamarin-android-timeline-view-view-header-height.png)

### View header date format

You can customize the date format of `ViewHeader` in `TimelineView` using the [DateFormat](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.TimelineLabelSettings.html#Com_Syncfusion_Schedule_TimelineLabelSettings_DateFormat) property of `TimelineLabelSettings`.

{% tabs %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.Timeline;
//Creating new instance of TimelineViewSettings
TimelineViewSettings timelineViewSettings = new TimelineViewSettings();
//Creating new instance of TimelineLabelSettings
TimelineLabelSettings labelSettings = new TimelineLabelSettings();
//Customizing date format
labelSettings.DateFormat = "d EEE";
timelineViewSettings.LabelSettings = labelSettings;
schedule.TimelineViewSettings = timelineViewSettings;
{% endhighlight %}
{% endtabs %}

![View header date format in xamarin android Timeline view](timeline-view-images/xamarin-android-timeline-view-view-header-date-format.png)

## Timeslot customization

You can customize the appearance of time slots using the [Color](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.TimelineViewSettings.html#Com_Syncfusion_Schedule_TimelineViewSettings_Color), [BorderColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.TimelineViewSettings.html#Com_Syncfusion_Schedule_TimelineViewSettings_BorderColor) and [BorderWidth](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.TimelineViewSettings.html#Com_Syncfusion_Schedule_TimelineViewSettings_BorderWidth) properties of `TimelineViewSettings`.

{% tabs %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.Timeline;
//Create new instance of TimelineViewSettings
TimelineViewSettings timelineViewSettings = new TimelineViewSettings();
timelineViewSettings.BorderColor = Color.Rgb(132, 144, 249);
timelineViewSettings.Color = Color.Rgb(232, 234, 249);
timelineViewSettings.BorderWidth = 2;
schedule.TimelineViewSettings = timelineViewSettings;
{% endhighlight %}
{% endtabs %}

![Time slot customization in xamarin android Timeline view](timeline-view-images/xamarin-android-timeline-view-time-slot-customization.png)

## Time label customization

You can customize the format for the labels that mention the time by setting the [TimeFormat](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.TimelineLabelSettings.html#Com_Syncfusion_Schedule_TimelineLabelSettings_TimeFormat) property of [LabelSettings](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.TimelineViewSettings.html#Com_Syncfusion_Schedule_TimelineViewSettings_LabelSettings) in `TimelineViewSettings`.

{% tabs %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.Timeline;
//Creating new instance of TimelineViewSettings
TimelineViewSettings timelineViewSettings = new TimelineViewSettings();
TimelineLabelSettings labelSettings = new TimelineLabelSettings();
labelSettings.TimeFormat = "hh:mm";
timelineViewSettings.LabelSettings = labelSettings;
schedule.TimelineViewSettings = timelineViewSettings;
{% endhighlight %}
{% endtabs %}

![Time label format in xamarin android Timeline view](timeline-view-images/xamarin-android-timeline-view-time-label-format.png)

### Time label appearance

You can customize the color for the labels that mention the time by setting the [TimeLabelColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.TimelineLabelSettings.html#Com_Syncfusion_Schedule_TimelineLabelSettings_TimeLabelColor) property of `LabelSettings` in `TimelineViewSettings`.

{% tabs %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.Timeline;
//Creating new instance of TimelineViewSettings
TimelineViewSettings timelineViewSettings = new TimelineViewSettings();
TimelineLabelSettings labelSettings = new TimelineLabelSettings();
labelSettings.TimeLabelColor = Color.Rgb(132, 144, 249);
timelineViewSettings.LabelSettings = labelSettings;
schedule.TimelineViewSettings = timelineViewSettings;
{% endhighlight %}
{% endtabs %}

![Time label appearance in xamarin android Timeline view](timeline-view-images/xamarin-android-timeline-view-time-label-appearance.png)

### Time Label size

You can customize the size of the labels that mention the time by setting the [TimeLabelSize](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.TimelineLabelSettings.html#Com_Syncfusion_Schedule_TimelineLabelSettings_TimeLabelSize) property of `LabelSettings` in `TimelineViewSettings`.

{% tabs %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.Timeline;
//Creating new instance of TimelineViewSettings
TimelineViewSettings timelineViewSettings = new TimelineViewSettings();
TimelineLabelSettings labelSettings = new TimelineLabelSettings();
labelSettings.TimeLabelSize = 10;	
timelineViewSettings.LabelSettings = labelSettings;
schedule.TimelineViewSettings = timelineViewSettings;
{% endhighlight %}
{% endtabs %}

![Time label size in xamarin android Timeline view](timeline-view-images/xamarin-android-timeline-view-time-label-size.png)

## Selection
You can customize the default appearance of selection UI in the timeslots.

* [Selection customization using style](#selection-customization-using-style)
* [Selection customization using custom View](#selection-customization-using-custom-view)
* [Programmatic selection](#programmatic-selection)

### Selection customization using style
You can customize the timeslot selection by using [SelectionStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_SelectionStyle) property of `SfSchedule`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.Timeline;
//Create new instance of SelectionStyle
SelectionStyle selectionStyle = new SelectionStyle();
selectionStyle.BackgroundColor = Color.Rgb(132, 144, 249);
selectionStyle.BorderColor = Color.Black;
selectionStyle.BorderThickness = 5;
selectionStyle.CornerRadius = 5;
schedule.SelectionStyle = selectionStyle;
{% endhighlight %}
{% endtabs %}

![Selection style in xamarin android Timeline view](timeline-view-images/xamarin-android-timeline-view-selection-style.png)

### Selection customization using custom View
You can replace the default selection UI with your custom view by setting [SelectionView](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_SelectionView) property of `SfSchedule`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.Timeline;
//Add the CustomView
Button customView = new Button(this);
customView.Text = "+NewEvent";
customView.SetBackgroundColor(Color.Rgb(255, 152, 0));
customView.SetTextColor(Color.White);
schedule.SelectionView = customView;
{% endhighlight %}
{% endtabs %}

![Custom selection view in xamarin android Timeline view](timeline-view-images/xamarin-android-timeline-view-custom-selection-view.png)

### Programmatic selection
You can programmatically select the specific timeslot by setting corresponding date and time value to [SelectedDate](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_SelectedDate) property of `SfSchedule`. By default, it is null.

{% tabs %}
{% highlight C# %}
// Creating instance of calendar
Calendar calendar = Calendar.Instance;

// Setting a date and time to select
calendar.Set(2017, 09, 04, 10, 0, 0);
schedule.SelectedDate = calendar;
{% endhighlight %}
{% endtabs %}

You can clear the selection by setting `SelectedDate` as null.

{% tabs %}
{% highlight C# %}
// Setting null value to deselect
schedule.SelectedDate = null;
{% endhighlight %}
{% endtabs %}

![Programatic selection in xamarin android Timeline view](timeline-view-images/xamarin-android-timeline-view-programatic-selection.png)

>**NOTE**
* `SfSchedule` does not support multiple selection.
* `SfSchedule` supports two-way binding of `SelectedDate` property.


