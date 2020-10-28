---

layout: post
title: Customize WeekView at Syncfusion SfSchedule for Xamarin.Android
description: Learn how to Customize the schedule WeekView in SfSchedule control in Xamarin.Android
platform: xamarin.Android
control: SfSchedule
documentation: ug

---


# WeekView
To view all the seven days of a particular week, by default if will be current week. Appointments arranged in timeslots based on its duration with respective day of the week.

## ViewHeader Appearance
You can customize the default appearance of view header in [WeekView](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.Enums.ScheduleView.html) by using [ViewHeaderStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_ViewHeaderStyle) property of [SfSchedule](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html).

{% tabs %}
{% highlight c# %}
//Create new instance of Schedule
SfSchedule schedule = new SfSchedule(this);
schedule.ScheduleView = ScheduleView.WeekView;
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

![Week view view header appearance customization in schedule for Xamarin.Android](daymodule_images/viewheader_appearance_week.png)

You can customize the height of the ViewHeader in `WeekView` by setting [ViewHeaderHeight](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_ViewHeaderHeight) property of `SfSchedule`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WeekView;
schedule.ViewHeaderHeight = 50;
{% endhighlight %}
{% endtabs %}

![Week view view header height customization for schedule in Xamarin.Android](daymodule_images/viewheaderheight_week.png)

### Customize Font Appearance

You can change the appearance of Font by setting the [DayTextStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.ViewHeaderStyle.html#Com_Syncfusion_Schedule_ViewHeaderStyle_DayTextStyle) and [DateTextStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.ViewHeaderStyle.html#Com_Syncfusion_Schedule_ViewHeaderStyle_DateTextStyle)  properties of [ViewHeaderStyle](https://help.syncfusion.com/xamarin-android/sfschedule/dayview#viewheader-appearance) property in Schedule.

{% tabs %}
{% highlight c# %}
viewHeaderStyle.DayTextStyle = Typeface.CreateFromAsset(Assets, "Lobster-Regular.ttf");
viewHeaderStyle.DateTextStyle = Typeface.CreateFromAsset(Assets, "Lobster-Regular.ttf");		
{% endhighlight %}
{% endtabs %}


![Week view custom font for view header for schedule in Xamarin.Android](daymodule_images/customfontviewheader_week.png)

Refer [this](https://help.syncfusion.com/xamarin-android/sfschedule/monthview#custom-font-setting-in-xamarinandroid) to configure the custom fonts in Xamarin.Android.

### ViewHeader Date Format
You can customize the date and day format of `SfSchedule` ViewHeader by using [DateFormat](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekLabelSettings.html#Com_Syncfusion_Schedule_WeekLabelSettings_DateFormat) and [DayFormat](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekLabelSettings.html#Com_Syncfusion_Schedule_WeekLabelSettings_DayFormat) properties of `WeekLabelSettings`

{% tabs %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.WeekView;
//Creating new instance of WeekViewSettings
WeekViewSettings weekViewSettings = new WeekViewSettings();
//Creating new instance of WeekLabelSettings
WeekLabelSettings weekLabelSettings = new WeekLabelSettings();
//Customizing date format
weekLabelSettings.DateFormat = "dd";
weekLabelSettings.DayFormat = "EEEE";
weekViewSettings.WeekLabelSettings = weekLabelSettings;
schedule.WeekViewSettings = weekViewSettings;
{% endhighlight %}
{% endtabs %}

![Week view header date format customization for schedule in Xamarin.Android](daymodule_images/DateFormat_Week.png)


### ViewHeader Tapped Event
You can handle single tap action of ViewHeader by using [ViewHeaderTapped](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html) event of `SfSchedule`. This event will be triggered when the ViewHeader is Tapped. This event contains [ViewHeaderTappedEventArgs](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.ViewHeaderTappedEventArgs.html) argument which holds [Calendar](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.HeaderTappedEventArgs.html#Com_Syncfusion_Schedule_HeaderTappedEventArgs_Calendar) details in it.

{% tabs %}
{% highlight c# %}
//Creating  new instance of Schedule
SfSchedule schedule = new SfSchedule();
schedule.ScheduleView = ScheduleView.WeekView;
schedule.ViewHeaderTapped += Handle_ViewHeaderTapped;

...

void Handle_ViewHeaderTapped(object sender, ViewHeaderTappedEventArgs e)
{
    var calendar = e.Calendar;
}
{% endhighlight %}
{% endtabs %}

## Change Time Interval
You can customize the interval of timeslots in `WeekView` by setting [TimeInterval](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_TimeInterval) property of `SfSchedule`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WeekView;
schedule.TimeInterval = 120;
{% endhighlight %}
{% endtabs %}

![Week view time interval customization for schedule in Xamarin.Android](daymodule_images/timeinterval_week.png)

>**NOTE**
If you modify the `TimeInterval` value (in minutes), you need to change the time labels format by setting the `TimeFormat` value as "hh:mm". By default, TimeFormat value is `"h a"`. You can refer [here](https://help.syncfusion.com/xamarin-android/sfschedule/weekview#time-label-formatting) for changing TimeFormat value.

## Change Time Interval Height
You can customize the interval height of timeslots in `WeekView` by setting [TimeIntervalHeight](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_TimeIntervalHeight)  property of `SfSchedule`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WeekView;
schedule.TimeIntervalHeight = 180;
{% endhighlight %}
{% endtabs %}

![Week view time interval height customization for schedule in Xamarin.Android](daymodule_images/weekview_height.png)

## Change Working hours

Working hours in `WeekView` of Schedule control will be differentiated with non-working hours by separate color. By default, working hours will be between 09 to 18. You can customize the working hours by setting [WorkStartHour](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekViewSettings.html#Com_Syncfusion_Schedule_WeekViewSettings_WorkStartHour) and [WorkEndHour](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekViewSettings.html#Com_Syncfusion_Schedule_WeekViewSettings_WorkEndHour) properties of [WeekViewSettings](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_WeekViewSettings). You can also customize the working hours along with minutes by setting double value which will be converted to time.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WeekView;
//Create new instance of WeekViewSettings
WeekViewSettings weekViewSettings = new WeekViewSettings();
WeekLabelSettings weekLabelSettings = new WeekLabelSettings();
WeekLabelSettings.TimeFormat = "hh:mm";
weekViewSettings.WorkStartHour = 11.5;
weekViewSettings.WorkEndHour = 17.5;
weekViewSettings.WeekLabelSettings = weekLabelSettings;
schedule.WeekViewSettings = weekViewSettings;
{% endhighlight %}
{% endtabs %}

![Week view working hours customization for schedule in Xamarin.Android](daymodule_images/changeworkinghours_week.png)

>**NOTE**
No need to specify the decimal point values for `WorkStartHour` and `WorkEndHour`, if you don’t want to set the minutes.

## Changing StartHour and EndHour

Default value for [StartHour](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekViewSettings.html#Com_Syncfusion_Schedule_WeekViewSettings_StartHour) and [EndHour](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekViewSettings.html#Com_Syncfusion_Schedule_WeekViewSettings_EndHour) value is 0 to 24 to show all the time slots in DayView. You need to set StartHour and EndHour property of `WeekView`, to show only the required time duration for end users. You can also set `StartHour` and `EndHour` in double value which will be converted to time to show required time duration in minutes.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WeekView;
//Create new instance of WeekViewSettings
WeekViewSettings weekViewSettings = new WeekViewSettings();
WeekLabelSettings weekLabelSettings = new WeekLabelSettings();
WeekLabelSettings.TimeFormat = "hh:mm";
weekViewSettings.StartHour = 7.5;
weekViewSettings.EndHour = 18.5;
weekViewSettings.WeekLabelSettings = weekLabelSettings;
schedule.WeekViewSettings = weekViewSettings;
{% endhighlight %}
{% endtabs %}

![Week view customizing start and end hour for schedule in Xamarin.Android](daymodule_images/changestartendhour_week.png)

>**NOTE**
* `StartHour` must be greater than or equal to 0 and `EndHour` must be lesser than or equal to 24, otherwise `InvalidDataException` will be thrown.
* `EndHour` value must be greater than `StartHour`, otherwise `InvalidDataException` will be thrown.
* Schedule UI such as Appointments and NonAccessibleBlocks which does not fall within the `StartHour` and `EndHour` will not be visible and if it falls partially, it will be clipped.
* No need to specify the decimal point values for `StartHour` and `EndHour`, if you don’t want to set the minutes.
* The number of time slots will be calculated based on total minutes of a day and time interval (total minutes of a day ((start hour - end hour) * 60) / time interval).
* If the custom time interval is given, then the number of time slots calculated based on given time interval should result in integer value, otherwise given time interval will be neglected and default time interval (60 minutes) will be considered.
* If the custom start hour and end hour is given, then the number of time slots calculated based on given start hour, end hour should result in integer value, otherwise given end hour will be rounded off. For example, if StartHour is 7.2 (07:12AM), EndHour is 18.6 (06:36AM) and TimeInterval is 60 minutes, then EndHour will be rounded off to 18.2 (06:12PM).

## Timeslot Appearance
You can customize the appearance of timeslots in `WeekView`.

 * [Timeslot customization in Work hours](#timeslot-customization-in-work-hours)
* [Timeslot customization in Non Working hours](#timeslot-customization-in-non-working-hours)

### Timeslot customization in Work hours
You can customize the appearance of the working hour timeslots by its color using [TimeSlotColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekViewSettings.html#Com_Syncfusion_Schedule_WeekViewSettings_TimeSlotColor),[TimeSlotBorderColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekViewSettings.html#Com_Syncfusion_Schedule_WeekViewSettings_TimeSlotBorderColor), [VerticalLineStrokeWidth](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekViewSettings.html#Com_Syncfusion_Schedule_WeekViewSettings_VerticalLineStrokeWidth), [VerticalLineColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekViewSettings.html#Com_Syncfusion_Schedule_WeekViewSettings_VerticalLineColor) and [TimeSlotBorderStrokeWidth](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekViewSettings.html#Com_Syncfusion_Schedule_WeekViewSettings_TimeSlotBorderStrokeWidth) properties of `WeekViewSettings`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WeekView;
//Create new instance of WeekViewSettings
WeekViewSettings weekViewSettings = new WeekViewSettings();
weekViewSettings.TimeSlotBorderColor = Color.Aqua;
weekViewSettings.VerticalLineColor = Color.Blue;
weekViewSettings.TimeSlotColor = Color.Yellow;
weekViewSettings.TimeSlotBorderStrokeWidth = 5;
weekViewSettings.VerticalLineStrokeWidth = 5;
schedule.WeekViewSettings = weekViewSettings;
{% endhighlight %}
{% endtabs %}

![Week view time slot appearance customization for schedule in Xamarin.Android](daymodule_images/timeslotappearance_week.png)

### Timeslot customization in Non Working hours

You can customize the appearance of the non-working hour timeslots by its color using [NonWorkingHoursTimeSlotBorderColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekViewSettings.html#Com_Syncfusion_Schedule_WeekViewSettings_NonWorkingHoursTimeSlotBorderColor),[NonWorkingHoursTimeSlotColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekViewSettings.html#Com_Syncfusion_Schedule_WeekViewSettings_NonWorkingHoursTimeSlotColor),[VerticalLineStrokeWidth](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekViewSettings.html#Com_Syncfusion_Schedule_WeekViewSettings_VerticalLineStrokeWidth), [VerticalLineColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekViewSettings.html#Com_Syncfusion_Schedule_WeekViewSettings_VerticalLineColor) and [TimeSlotBorderStrokeWidth](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekViewSettings.html#Com_Syncfusion_Schedule_WeekViewSettings_TimeSlotBorderStrokeWidth) properties of `WeekViewSettings`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WeekView;
//Create new instance of WeekViewSettings
WeekViewSettings weekViewSettings = new WeekViewSettings();
weekViewSettings.NonWorkingHoursTimeSlotBorderColor = Color.Aqua;
weekViewSettings.VerticalLineColor = Color.Blue;
weekViewSettings.NonWorkingHoursTimeSlotColor = Color.Yellow;
weekViewSettings.TimeSlotBorderStrokeWidth = 5;
weekViewSettings.VerticalLineStrokeWidth = 5;
schedule.WeekViewSettings = weekViewSettings;
{% endhighlight %}
{% endtabs %}

![Week view non working hours customization for schedule in Xamarin.Android](daymodule_images/non-working hours_week.png)

>**NOTE**
`TimeSlotBorderStrokeWidth`and ` VerticalLineStrokeWidth` properties are common to both Working hours and Non-Working hour time slot customization.

## Non-Accessible timeslots

You can restrict or allocate certain timeslot as Non-accessible blocks by using[NonAccessibleBlocks](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekViewSettings.html#Com_Syncfusion_Schedule_WeekViewSettings_NonAccessibleBlocks) of `WeekViewSettings` so that you can allocate those timeslots for predefined events/activities like Lunch hour.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WeekView;
//Create new instance of NonAccessibleBlock
NonAccessibleBlock nonAccessibleBlock = new NonAccessibleBlock();
//Create new instance of NonAccessibleBlocksCollection
NonAccessibleBlocksCollection nonAccessibleBlocksCollection = new NonAccessibleBlocksCollection();
WeekViewSettings weekViewSettings = new WeekViewSettings();
nonAccessibleBlock.StartTime = 13;
nonAccessibleBlock.EndTime = 14;
nonAccessibleBlock.Text = "LUNCH";
nonAccessibleBlock.Color = Color.Black;
nonAccessibleBlocksCollection.Add(nonAccessibleBlock);
weekViewSettings.NonAccessibleBlocks = nonAccessibleBlocksCollection;
schedule.WeekViewSettings = weekViewSettings;
{% endhighlight %}
{% endtabs %}

![Non accessible block support in schedule week view for Xamarin.Android](daymodule_images/non-accessibleblock_week.png)

>**NOTE**
Selection and related events will not be working in this blocks.

## Change first day of week

By default, schedule control will be rendered with Sunday as the first day of the week, it can be customized to any day of the week by using[FirstDayOfWeek](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_FirstDayOfWeek) property of `SfSchedule`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WeekView;
schedule.FirstDayOfWeek = 3;
{% endhighlight %}
{% endtabs %}

![First day of week for week view in schedule for Xamarin.Android](daymodule_images/firstdayofweek_week.png)

## Time Label Formatting
You can customize the format for the labels which are mentioning the time, by setting [TimeFormat](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekLabelSettings.html#Com_Syncfusion_Schedule_WeekLabelSettings_TimeFormat) property of [WeekLabelSettings](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekViewSettings.html#Com_Syncfusion_Schedule_WeekViewSettings_WeekLabelSettings) in `WeekViewSettings`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WeekView;
WeekViewSettings weekViewSettings = new WeekViewSettings();
WeekLabelSettings weekLabelSettings = new WeekLabelSettings();
weekLabelSettings.TimeFormat = "hh mm";
weekViewSettings.WeekLabelSettings = weekLabelSettings;
schedule.WeekViewSettings = weekViewSettings;
{% endhighlight %}
{% endtabs %}

![Week view time label customization for schedule in Xamarin.Android](daymodule_images/timelabelformat_week.png)

## Time Label Appearance

You can customize the color for the labels which are mentioning the time, by setting [TimeLabelColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekLabelSettings.html#Com_Syncfusion_Schedule_WeekLabelSettings_TimeLabelColor) property of `WeekLabelSettings` in `WeekViewSettings`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WeekView;
//Create new instance of WeekViewSettings
WeekViewSettings weekViewSettings = new WeekViewSettings();
//Create new instance of WeekLabelSettings
WeekLabelSettings weekLabelSettings = new WeekLabelSettings();
weekLabelSettings.TimeLabelColor = Color.Blue;
weekViewSettings.WeekLabelSettings = weekLabelSettings;
schedule.WeekViewSettings = weekViewSettings;
{% endhighlight %}
{% endtabs %}

![Week view time label appearance customization for schedule in Xamarin.Android](daymodule_images/timelabelappearance_week.png)

## Selection
You can customize the default appearance of selection UI in the timeslots.

* [Selection customization using style](#selection-customization-using-style)
* [Selection customization using custom View](#selection-customization-using-custom-view)

### Selection customization using style
You can customize the timeslot selection by using [SelectionStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_SelectionStyle) property of `SfSchedule`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WeekView;
//Create new instance of SelectionStyle 
SelectionStyle selectionStyle = new SelectionStyle();
selectionStyle.BackgroundColor = Color.Blue;
selectionStyle.BorderColor = Color.Black;
selectionStyle.BorderThickness = 5;
selectionStyle.CornerRadius = 5;
schedule.SelectionStyle = selectionStyle;
{% endhighlight %}
{% endtabs %}

![Selection style for schedule Week view in Xamarin.Android](daymodule_images/selectionstyle_week.png)

### Selection customization using custom View
You can replace the default selection UI with your custom view by setting [SelectionView](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_SelectionView) property of `SfSchedule`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.WeekView;
//Add the CustomView
Button customView = new Button(this);
customView.Text = "+NewEvent";
customView.SetBackgroundColor(Color.Rgb(255, 152, 0));
customView.SetTextColor(Color.White);
schedule.SelectionView = customView;
{% endhighlight %}
{% endtabs %}

![Custom selection view support for schedule Week view in Xamarin.Android](daymodule_images/selectioncustomview_week.png)

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

![Programmatic selection support for schedule week view in Xamarin.Android](daymodule_images/selection_Week.png)


