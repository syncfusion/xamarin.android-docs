---

layout: post
title: Customize WorkWeekView at Syncfusion SfSchedule for Xamarin.Android
description: Learn how to Customize the schedule WorkWeekView in SfSchedule control in Xamarin.Android
platform: xamarin.Android
control: SfSchedule
documentation: ug

---


# WorkWeekView
WorkWeekView is to view only working days of a particular week. By default, Saturday and Sunday are the non-working days. You can be customize it with any days of a Week. Appointments arranged in timeslots based on its duration with respective day of the week.

## ViewHeader Appearance
You can customize the default appearance of view header in [WorkWeekView](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.Enums.ScheduleView.html) by using [ViewHeaderStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_ViewHeaderStyle) property of [SfSchedule](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html).

{% tabs %}
{% highlight c# %}
//Create new instance of Schedule
SfSchedule schedule = new SfSchedule(this);
schedule.ScheduleView = ScheduleView.WorkWeekView;
//Customize the schedule view header
ViewHeaderStyle viewHeaderStyle = new ViewHeaderStyle();
viewHeaderStyle.BackgroundColor = Color.Rgb(0, 150, 136);
viewHeaderStyle.DayTextColor = Color.Rgb(255, 255, 255);
viewHeaderStyle.DateTextColor = Color.Rgb(255, 255, 255);
viewHeaderStyle.DayTextStyle = Typeface.DefaultFromStyle(TypefaceStyle.Italic);
viewHeaderStyle.DateTextStyle = Typeface.DefaultFromStyle(TypefaceStyle.Italic);
schedule.ViewHeaderStyle = viewHeaderStyle;
{% endhighlight %}
{% endtabs %}

![Work week view view header appearance customization in schedule for Xamarin.Android](daymodule_images/viewheaderappearance_workweek.png)

You can customize the height of the ViewHeader in `WorkWeekView` by setting [ViewHeaderHeight](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_ViewHeaderHeight) property of `SfSchedule`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
schedule.ViewHeaderHeight = 50;
{% endhighlight %}
{% endtabs %}

![Work week view view header height customization for schedule in Xamarin.Android](daymodule_images/viewheaderheight_workweek.png)

### Customize Font Appearance

You can change the appearance of Font by setting the [DayTextStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.ViewHeaderStyle.html#Com_Syncfusion_Schedule_ViewHeaderStyle_DayTextStyle) and [DateTextStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.ViewHeaderStyle.html#Com_Syncfusion_Schedule_ViewHeaderStyle_DateTextStyle) properties of  [ViewHeaderStyle](https://help.syncfusion.com/xamarin-android/sfschedule/dayview#viewheader-appearance) property in Schedule.

{% tabs %}
{% highlight c# %}
viewHeaderStyle.DayTextStyle = Typeface.CreateFromAsset(Assets, "Lobster-Regular.ttf");
viewHeaderStyle.DateTextStyle = Typeface.CreateFromAsset(Assets, "Lobster-Regular.ttf");		
{% endhighlight %}
{% endtabs %}

![Week view custom font for view header for schedule in Xamarin.Android](daymodule_images/customfontviewheader_workweek.png)

Refer [this](https://help.syncfusion.com/xamarin-android/sfschedule/monthview#custom-font-setting-in-xamarinandroid) to configure the custom fonts in Xamarin.Android.

### ViewHeader Date Format
You can customize the date and day format of `SfSchedule` ViewHeader by using [DateFormat](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WorkWeekLabelSettings.html#Com_Syncfusion_Schedule_WorkWeekLabelSettings_DateFormat) and [DayFormat](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WorkWeekLabelSettings.html#Com_Syncfusion_Schedule_WorkWeekLabelSettings_DayFormat) properties of `WorkWeekLabelSettings`.

{% tabs %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
//Creating new instance of WorkWeekViewSettings
WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
//Creating new instance of WorkWeekLabelSettings
WorkWeekLabelSettings workWeekLabelSettings = new WorkWeekLabelSettings();
//Customizing date format
workWeekLabelSettings.DateFormat = "dd";
workWeekLabelSettings.DayFormat = "EEEE";
workWeekViewSettings.WorkWeekLabelSettings = workWeekLabelSettings;
schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% endtabs %}

![Work week view header date format customization for schedule in Xamarin.Android](daymodule_images/DateFormat_WorkWeek.png)

### ViewHeader Tapped Event
You can handle single tap action of ViewHeader by using [ViewHeaderTapped](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html) event of `SfSchedule`. This event will be triggered when the ViewHeader is Tapped. This event contains [ViewHeaderTappedEventArgs](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.ViewHeaderTappedEventArgs.html) argument which holds [Calendar](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.HeaderTappedEventArgs.html#Com_Syncfusion_Schedule_HeaderTappedEventArgs_Calendar) details in it.

{% tabs %}
{% highlight c# %}
//Creating  new instance of Schedule
SfSchedule schedule = new SfSchedule();
schedule.ScheduleView = ScheduleView.WorkWeekView;
schedule.ViewHeaderTapped += Handle_ViewHeaderTapped;

...

void Handle_ViewHeaderTapped(object sender, ViewHeaderTappedEventArgs e)
{
    var calendar = e.Calendar;
}
{% endhighlight %}
{% endtabs %}

## Change Time Interval
You can customize the interval of timeslots in `WorkWeekView` by setting [TimeInterval](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_TimeInterval) property of `SfSchedule`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
schedule.TimeInterval = 120;
{% endhighlight %}
{% endtabs %}

![Work week view time interval customization for schedule in Xamarin.Android](daymodule_images/timeinterval_workweek.png)


>**NOTE**
If you modify the `TimeInterval` value (in minutes), you need to change the time labels format by setting the `TimeFormat` value as "hh:mm". By default, TimeFormat value is `"h a"`. You can refer [here](https://help.syncfusion.com/xamarin-android/sfschedule/workweekview#time-label-formatting) for changing TimeFormat value.

## Change Time Interval Height
You can customize the interval height of timeslots in `WorkWeekView` by setting [TimeIntervalHeight](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_TimeIntervalHeight)  property of `SfSchedule`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
schedule.TimeIntervalHeight = 180;
{% endhighlight %}
{% endtabs %}

![Work week view time interval height customization for schedule in Xamarin.Android](daymodule_images/workweekview_height.png)

>**NOTE**
`WorkStartHour` and `WorkEndHour` should be in integer value to represent hours.

## Change Working hours

Working hours in `WorkWeekView` of Schedule control will be differentiated with non-working hours by separate color. By default, working hours will be between 09 to 18. You can customize the working hours by setting [WorkStartHour](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WorkWeekViewSettings.html#Com_Syncfusion_Schedule_WorkWeekViewSettings_WorkStartHour) and [WorkEndHour](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WorkWeekViewSettings.html#Com_Syncfusion_Schedule_WorkWeekViewSettings_WorkEndHour) properties of [WorkWeekViewSettings](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_WorkWeekViewSettings). You can also customize the working hours along with minutes by setting double value which will be converted to time.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
//Create new instance of WorkWeekViewSettings
WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
WorkWeekLabelSettings workWeekLabelSettings = new WorkWeekLabelSettings();
WeekLabelSettings.TimeFormat = "hh:mm";
workWeekViewSettings.WorkStartHour = 11.5;
workWeekViewSettings.WorkEndHour = 17.5;
workWeekViewSettings.WorkWeekLabelSettings = workWeekLabelSettings;
schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% endtabs %}

![Week view working hours customization for schedule in Xamarin.Android](daymodule_images/changeworkinghours_workweek.png)

>**NOTE**
No need to specify the decimal point values for `WorkStartHour` and `WorkEndHour`, if you don’t want to set the minutes.

## Changing StartHour and EndHour

Default value for [StartHour](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WorkWeekViewSettings.html#Com_Syncfusion_Schedule_WorkWeekViewSettings_StartHour) and [EndHour](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WorkWeekViewSettings.html#Com_Syncfusion_Schedule_WorkWeekViewSettings_EndHour) value is 0 to 24 to show all the time slots in `WorkWeekView`. You need to set [StartHour](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WorkWeekViewSettings.html#Com_Syncfusion_Schedule_WorkWeekViewSettings_StartHour) and [EndHour](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WorkWeekViewSettings.html#Com_Syncfusion_Schedule_WorkWeekViewSettings_EndHour) property of `WorkWeekView`, to show only the required time duration for end users. You can also set `StartHour` and `EndHour` in double value which will be converted to time to show required time duration in minutes.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
//Create new instance of WorkWeekViewSettings
WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
WorkWeekLabelSettings workWeekLabelSettings = new WorkWeekLabelSettings();
WeekLabelSettings.TimeFormat = "hh:mm";
workWeekViewSettings.StartHour = 7.5;
workWeekViewSettings.EndHour = 18.5;
workWeekViewSettings.WorkWeekLabelSettings = workWeekLabelSettings;
schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% endtabs %}

![Week view customizing start and end hour for schedule in Xamarin.Android](daymodule_images/changestartendhour_workweek.png)

>**NOTE**
* `StartHour` must be greater than or equal to 0 and `EndHour` must be lesser than or equal to 24, otherwise `InvalidDataException` will be thrown.
* `EndHour` value must be greater than `StartHour`, otherwise `InvalidDataException` will be thrown.
* Schedule UI such as Appointments and NonAccessibleBlocks which does not fall within the `StartHour` and `EndHour` will not be visible and if it falls partially, it will be clipped.
* No need to specify the decimal point values for `StartHour` and `EndHour`, if you don’t want to set the minutes.
* The number of time slots will be calculated based on total minutes of a day and time interval (total minutes of a day ((start hour - end hour) * 60) / time interval).
* If the custom time interval is given, then the number of time slots calculated based on given time interval should result in integer value, otherwise given time interval will be neglected and default time interval (60 minutes) will be considered.
* If the custom start hour and end hour is given, then the number of time slots calculated based on given start hour, end hour should result in integer value, otherwise given end hour will be rounded off. For example, if StartHour is 7.2 (07:12AM), EndHour is 18.6 (06:36AM) and TimeInterval is 60 minutes, then EndHour will be rounded off to 18.2 (06:12PM).

## Timeslot Appearance
You can customize the appearance of timeslots in `WorkWeekView`.

 * [Timeslot customization in Work hours](#timeslot-customization-in-work-hours)
* [Timeslot customization in Non Working hours](#timeslot-customization-in-non-working-hours)

### Timeslot customization in Work hours
You can customize the appearance of the working hour timeslots by its color using[TimeSlotColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WorkWeekViewSettings.html#Com_Syncfusion_Schedule_WorkWeekViewSettings_TimeSlotColor),[TimeSlotBorderColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WorkWeekViewSettings.html#Com_Syncfusion_Schedule_WorkWeekViewSettings_TimeSlotBorderColor), [VerticalLineStrokeWidth](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WorkWeekViewSettings.html#Com_Syncfusion_Schedule_WorkWeekViewSettings_VerticalLineStrokeWidth), [VerticalLineColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WorkWeekViewSettings.html#Com_Syncfusion_Schedule_WorkWeekViewSettings_VerticalLineColor) and [TimeSlotBorderStrokeWidth](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WorkWeekViewSettings.html#Com_Syncfusion_Schedule_WorkWeekViewSettings_TimeSlotBorderStrokeWidth) properties of `WorkWeekViewSettings`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
//Create new instance of WorkWeekViewSettings
WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
workWeekViewSettings.TimeSlotBorderColor = Color.Aqua;
workWeekViewSettings.VerticalLineColor = Color.Blue;
workWeekViewSettings.TimeSlotColor = Color.Yellow;
workWeekViewSettings.TimeSlotBorderStrokeWidth = 5;
workWeekViewSettings.VerticalLineStrokeWidth = 5;
schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% endtabs %}

![Work week view time slot appearance customization for schedule in Xamarin.Android](daymodule_images/timeslotappearance_workweek.png)

### Timeslot customization in Non Working hours

You can customize the appearance of the non-working hour timeslots by its color using[NonWorkingHoursTimeSlotBorderColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WorkWeekViewSettings.html#Com_Syncfusion_Schedule_WorkWeekViewSettings_NonWorkingHoursTimeSlotBorderColor),[NonWorkingHoursTimeSlotColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WorkWeekViewSettings.html#Com_Syncfusion_Schedule_WorkWeekViewSettings_NonWorkingHoursTimeSlotColor),`VerticalLineStrokeWidth`, `VerticalLineColor` and `TimeSlotBorderStrokeWidth` properties of `WorkWeekViewSettings`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
//Create new instance of WorkWeekViewSettings
WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
workWeekViewSettings.NonWorkingHoursTimeSlotBorderColor = Color.Aqua;
workWeekViewSettings.VerticalLineColor = Color.Blue;
workWeekViewSettings.NonWorkingHoursTimeSlotColor = Color.Yellow;
workWeekViewSettings.TimeSlotBorderStrokeWidth = 5;
workWeekViewSettings.VerticalLineStrokeWidth = 5;
schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% endtabs %}

![Work week view non working hours customization for schedule in Xamarin.Android](daymodule_images/nonworkinghours_workweek.png)

>**NOTE**
`TimeSlotBorderStrokeWidth`and ` VerticalLineStrokeWidth` properties are common to both Working hours and Non-Working hour time slot customization.

## Non-Accessible timeslots

You can restrict or allocate certain timeslot as Non-accessible blocks by using[NonAccessibleBlocks](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WorkWeekViewSettings.html#Com_Syncfusion_Schedule_WorkWeekViewSettings_NonAccessibleBlocks) of `WorkWeekViewSettings` so that you can allocate those timeslots for predefined events/activities like Lunch hour.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
//Create new instance of NonAccessibleBlock
NonAccessibleBlock nonAccessibleBlock = new NonAccessibleBlock();
//Create new instance of NonAccessibleBlocksCollection
NonAccessibleBlocksCollection nonAccessibleBlocksCollection = new NonAccessibleBlocksCollection();
WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
nonAccessibleBlock.StartTime = 13;
nonAccessibleBlock.EndTime = 14;
nonAccessibleBlock.Text = "LUNCH";
nonAccessibleBlock.Color = Color.Black;
nonAccessibleBlocksCollection.Add(nonAccessibleBlock);
workWeekViewSettings.NonAccessibleBlocks = nonAccessibleBlocksCollection;
schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% endtabs %}

![Non accessible block support in schedule work week view for Xamarin.Android](daymodule_images/nonaccessibleblock_workweek.png)

>**NOTE**
Selection and related events will not be working in this blocks.

## Change first day of week

By default, schedule control will be rendered with Sunday as the first day of the week, it can be customized to any day of the week by using[FirstDayOfWeek](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_FirstDayOfWeek) property of `SfSchedule`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
schedule.FirstDayOfWeek = 3;
{% endhighlight %}
{% endtabs %}

![First day of work week for week view in schedule for Xamarin.Android](daymodule_images/firstdayofweek_workweek.png)

## Time Label Formatting
You can customize the format for the labels which are mentioning the time, by setting [TimeFormat](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WorkWeekLabelSettings.html#Com_Syncfusion_Schedule_WorkWeekLabelSettings_TimeFormat) property of [WorkWeekLabelSettings](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WorkWeekViewSettings.html#Com_Syncfusion_Schedule_WorkWeekViewSettings_WorkWeekLabelSettings) in `WorkWeekViewSettings`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
WorkWeekViewSettings workweekViewSettings = new WorkWeekViewSettings();
WorkWeekLabelSettings workWeekLabelSettings = new WorkWeekLabelSettings();
workWeekLabelSettings.TimeFormat = "hh mm";
workweekViewSettings.WorkWeekLabelSettings = workWeekLabelSettings;
schedule.WorkWeekViewSettings = workweekViewSettings;
{% endhighlight %}
{% endtabs %}

![Work week view time label customization for schedule in Xamarin.Android](daymodule_images/timelabelformat_workweek.png)

## Time Label Appearance

You can customize the color for the labels which are mentioning the time, by setting [TimeLabelColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WorkWeekLabelSettings.html#Com_Syncfusion_Schedule_WorkWeekLabelSettings_TimeLabelColor) property of `WorkWeekLabelSettings` in `WorkWeekViewSettings`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
//Create new instance of WorkWeekViewSettings
WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
//Create new instance of WorkWeekLabelSettings
WorkWeekLabelSettings workWeekLabelSettings = new WorkWeekLabelSettings();
workWeekLabelSettings.TimeLabelColor = Color.Blue;
workWeekViewSettings.WorkWeekLabelSettings = workWeekLabelSettings;
schedule.WorkWeekViewSettings = workWeekViewSettings;
{% endhighlight %}
{% endtabs %}

![Work week view time label appearance customization for schedule in Xamarin.Android](daymodule_images/timelabelappearance_workweek.png)

## Selection
You can customize the default appearance of selection UI in the timeslots.

* [Selection customization using style](#selection-customization-using-style)
* [Selection customization using custom View](#selection-customization-using-custom-view)

### Selection customization using style
You can customize the timeslot selection by using [SelectionStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_SelectionStyle) property of `SfSchedule`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
//Create new instance of SelectionStyle
SelectionStyle selectionStyle = new SelectionStyle();
selectionStyle.BackgroundColor = Color.Blue;
selectionStyle.BorderColor = Color.Black;
selectionStyle.BorderThickness = 5;
selectionStyle.CornerRadius = 5;
schedule.SelectionStyle = selectionStyle;
{% endhighlight %}
{% endtabs %}

![Selection style for schedule Work week view in Xamarin.Android](daymodule_images/selectionstyle_workweek.png)

### Selection customization using custom View
You can replace the default selection UI with your custom view by setting [SelectionView](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_SelectionView) property of `SfSchedule`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WorkWeekView;
//Add the CustomView
Button customView = new Button(this);
customView.Text = "+NewEvent";
customView.SetBackgroundColor(Color.Rgb(255, 152, 0));
customView.SetTextColor(Color.White);
schedule.SelectionView = customView;
{% endhighlight %}
{% endtabs %}

![Custom selection view support for schedule Work week view in Xamarin.Android](daymodule_images/selectioncustomview_workweek.png)

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

You can clear the selection by setting [SelectedDate](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_SelectedDate) as null.

{% tabs %}
{% highlight C# %}
// Setting null value to deselect
schedule.SelectedDate = null;
{% endhighlight %}
{% endtabs %}

You can download the entire source code of this demo for Xamarin.Android from here [Date_Selection](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Date_Selection-303833588.zip)

>**NOTE**
* `SfSchedule` does not support multiple selection.
* `SfSchedule` supports two-way binding of `SelectedDate` property.

![Programmatic selection support for schedule Work week view in Xamarin.Android](daymodule_images/selection_WorkWeek.png)
