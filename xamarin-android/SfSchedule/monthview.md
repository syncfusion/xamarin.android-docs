---   
layout: post   
title: Customize MonthView at Syncfusion SfSchedule for Xamarin.Android
description: This section explains the schedule month view, appointment indicator, agenda view, week number, first day Of week in Xamarin.Android.
platform: xamarin.android   
control: SfSchedule   
documentation: ug   
---   
    
# Month View in Xamarin Scheduler (SfSchedule)
`MonthView` of `SfSchedule` used to display entire dates of the specific month, current month will be displayed by default initially. Current date color is differentiated with other dates of the current month, also the color differentiation for dates will be applicable for previous and next month dates.

{% tabs %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.MonthView;
{% endhighlight %}
{% endtabs %}

![Month view in schedule xamarin android](monthview_images/monthview.png)

## Month Appointment indicator
In `MonthView`, appointments are not viewed in the month cell instead appointment indicators are drawn. You can customize the number of appointment indicators displayed in month cell using  [AppointmentIndicatorCount](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthViewSettings.html#Com_Syncfusion_Schedule_MonthViewSettings_AppointmentIndicatorCount) property of [MonthViewSettings](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthViewSettings.html) in `SfSchedule`, by default Appointment indicator count is 3.

{% tabs %}
{% highlight c# %}
//creating new instance for MonthViewSettings
MonthViewSettings monthViewSettings = new MonthViewSettings();
monthViewSettings.AppointmentIndicatorCount = 2;
schedule.MonthViewSettings = monthViewSettings;
{% endhighlight %}
{% endtabs %}

![Month appointment indicator count in schedule xamarin android](monthview_images/appointmentindicator.png)

>**NOTE**
If appointments count are lesser than the AppointmentIndicatorCount value in the particular day, then according to number of appointments available, indicator will be displayed in the month cell.Maximum number of appointment indicators drawn in the month cell is 6.

## Month Inline View
You can use [ShowAppointmentsInline](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthViewSettings.html#Com_Syncfusion_Schedule_MonthViewSettings_ShowAppointmentsInline) bool property in [MonthViewSettings](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthViewSettings.html) to enable / disable the month inline view, by setting `ShowAppointmentsInline` property as `true` you can view the Appointments in the specific date. 

{% tabs %}
{% highlight c# %}
//creating new instance for MonthViewSettings
MonthViewSettings monthViewSettings = new MonthViewSettings();
monthViewSettings.ShowAppointmentsInline = true;
schedule.MonthViewSettings = monthViewSettings;
{% endhighlight %}
{% endtabs %}

![Month show inline appointment in schedule xamarin android](monthview_images/appointmentindicator.png)

>**NOTE**
If appointments not there in the selected day, Inline view displays the text as "No Events"

## Agenda View
The Schedule month view displays a divided agenda view which is used to show the selected date’s appointments below the month. You can show agenda view by setting [ShowAgendaView](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthViewSettings.html#Com_Syncfusion_Schedule_MonthViewSettings_ShowAgendaView) property as true.

{% tabs %}
{% highlight c# %}
SfSchedule schedule = new SfSchedule(context);
schedule.ScheduleView = ScheduleView.MonthView;
MonthViewSettings monthViewSettings = new MonthViewSettings();
monthViewSettings.ShowAgendaView = true;
schedule.MonthViewSettings = monthViewSettings; 
{% endhighlight %}
{% endtabs %}

![Month agendar view appointment in schedule xamarin android](monthview_images/AgendaView-android.png)

>**NOTE**
- An agenda view displays text as “No Selected Date” until no date is selected.
- If there is no appointment in a selected day, agenda view displays the text as “No Events”.
- If you enable ShowAgendaView and ShowAppointmentsInline properties together, both of the views (Agenda View and Appointment Inline View) will be displayed in schedule month view.

### Agenda View Appearance
You can customize the Agenda view appointment and Selected Date Text by setting [AgendaViewStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthViewSettings.html#Com_Syncfusion_Schedule_MonthViewSettings_AgendaViewStyle) property of `MonthViewSettings`. Agenda view [DateTextColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.AgendaViewStyle.html#Com_Syncfusion_Schedule_AgendaViewStyle_DateTextColor) , [HeaderHeight](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.AgendaViewStyle.html#Com_Syncfusion_Schedule_AgendaViewStyle_HeaderHeight) , [DateTextFormat](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.AgendaViewStyle.html#Com_Syncfusion_Schedule_AgendaViewStyle_DateTextFormat) , [DateTextStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.AgendaViewStyle.html#Com_Syncfusion_Schedule_AgendaViewStyle_DateTextStyle) , [DateTextSize](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.AgendaViewStyle.html#Com_Syncfusion_Schedule_AgendaViewStyle_DateTextSize) , [TimeTextColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.AgendaViewStyle.html#Com_Syncfusion_Schedule_AgendaViewStyle_TimeTextColor) , [TimeTextStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.AgendaViewStyle.html#Com_Syncfusion_Schedule_AgendaViewStyle_TimeTextStyle) , [TimeTextSize](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.AgendaViewStyle.html#Com_Syncfusion_Schedule_AgendaViewStyle_TimeTextSize) , [TimeTextFormat](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.AgendaViewStyle.html#Com_Syncfusion_Schedule_AgendaViewStyle_TimeTextFormat) , [SubjectTextColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.AgendaViewStyle.html#Com_Syncfusion_Schedule_AgendaViewStyle_SubjectTextColor) , [SubjectTextStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.AgendaViewStyle.html#Com_Syncfusion_Schedule_AgendaViewStyle_SubjectTextStyle) , [SubjectTextSize](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.AgendaViewStyle.html#Com_Syncfusion_Schedule_AgendaViewStyle_SubjectTextSize) , [BackgroundColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.AgendaViewStyle.html#Com_Syncfusion_Schedule_AgendaViewStyle_BackgroundColor) can be customized using AgendaViewStyle properties.

{% tabs %}
{% highlight c# %}
SfSchedule schedule = new SfSchedule(context);
schedule.ScheduleView = ScheduleView.MonthView;
MonthViewSettings monthViewSettings = new MonthViewSettings();
monthViewSettings.ShowAgendaView = true;
schedule.MonthViewSettings = monthViewSettings;
AgendaViewStyle agendaViewStyle = new AgendaViewStyle();
// Customize selected Date Text
agendaViewStyle.DateTextColor = Color.Purple;
agendaViewStyle.HeaderHeight = 50;
agendaViewStyle.DateTextFormat = "dd MMMM, yyyy";
agendaViewStyle.DateTextStyle = Typeface.Default;
agendaViewStyle.DateTextSize = 18;
// Customize appointment
agendaViewStyle.TimeTextColor = Color.Red;
agendaViewStyle.TimeTextStyle = Typeface.Default;
agendaViewStyle.TimeTextSize = 13;
agendaViewStyle.TimeTextFormat = "hh a";
agendaViewStyle.SubjectTextColor = Color.Blue;
agendaViewStyle.SubjectTextStyle = Typeface.Default;
agendaViewStyle.SubjectTextSize = 16;
agendaViewStyle.BackgroundColor = Color.LightBlue;
schedule.MonthViewSettings.AgendaViewStyle = agendaViewStyle;
{% endhighlight %}
{% endtabs %}

![Month agenda view appointment customization in schedule xamarin android](monthview_images/AgendaViewStyle.png)

## Month Navigation direction
MonthView of Schedule can be navigated in both horizontal and vertical direction. You can change the direction of navigation through [MonthNavigationDirection](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthViewSettings.html#Com_Syncfusion_Schedule_MonthViewSettings_MonthNavigationDirection) property of `MonthViewSettings` in `SfSchedule`, by default Month navigation direction is `Horizontal`.

{% tabs %}
{% highlight c# %}
monthViewSettings.MonthNavigationDirection = MonthNavigationDirections.Vertical;
{% endhighlight %}
{% endtabs %}

## Restricted days in Month
You can disable the interaction for certain date in Month view by using [BlackoutDates](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthViewSettings.html#Com_Syncfusion_Schedule_MonthViewSettings_BlackoutDates) of `MonthViewSettings`, using this you can allocate / restrict the specific date for predefined events.

{% tabs %}
{% highlight c# %}
//creating new instance for MonthViewSettings
MonthViewSettings monthViewSettings = new MonthViewSettings();
//setting black out dates
ObservableCollection<Calendar> blackoutDateCollection = new ObservableCollection<Calendar>();

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

blackoutDateCollection.Add(blockedDate1);
blackoutDateCollection.Add(blockedDate2);
blackoutDateCollection.Add(blockedDate3);
monthViewSettings.BlackoutDates = blackoutDateCollection;
schedule.MonthViewSettings = monthViewSettings;
{% endhighlight %}
{% endtabs %}

![black out dates in schedule xamarin android](monthview_images/blackoutdate.png)

## First day of Week in Month
You can set First day of week using [FirstDayOfWeek](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_FirstDayOfWeek) property of `SfSchedule`, by default schedule control will rendered with `Sunday` as the first day of the week. 

{% tabs %}
{% highlight c# %}
//setting FirstDayOfWeek
schedule.FirstDayOfWeek = 2; // Monday
{% endhighlight %}
{% endtabs %}

![First day of week in schedule xamarin android](monthview_images/firstdayofweek.png)

## Week Number of the Year in Month
You can display the Week Number of the year in Month View by setting [ShowWeekNumber](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthViewSettings.html#Com_Syncfusion_Schedule_MonthViewSettings_ShowWeekNumber) property of `MonthViewSettings` as `true`, by default it is `false`.

{% tabs %}
{% highlight c# %}
monthViewSettings.ShowWeekNumber = true;
{% endhighlight %}
{% endtabs %}

![Week number support in schedule xamarin android](monthview_images/showweeknumber.png)

## Week Number Appearance
You can customize the Week Number appearance by using [WeekNumberStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthViewSettings.html#Com_Syncfusion_Schedule_MonthViewSettings_WeekNumberStyle) property of `MonthViewSettings`. Week number [BackgroundColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekNumberStyle.html#Com_Syncfusion_Schedule_WeekNumberStyle_BackgroundColor), [TextColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekNumberStyle.html#Com_Syncfusion_Schedule_WeekNumberStyle_TextColor), [TextSize](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekNumberStyle.html#Com_Syncfusion_Schedule_WeekNumberStyle_TextSize) and [TextStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekNumberStyle.html#Com_Syncfusion_Schedule_WeekNumberStyle_TextStyle) can be customized using `WeekNumberStyle` properties.

{% tabs %}
{% highlight c# %}
//creating new instance for WeekNumberStyle
WeekNumberStyle weekNumberStyle = new WeekNumberStyle();
weekNumberStyle.TextStyle = Typeface.Create("Arial", TypefaceStyle.BoldItalic);
weekNumberStyle.BackgroundColor = Color.Blue;
weekNumberStyle.TextColor = Color.White;
weekNumberStyle.TextSize = 12;
monthViewSettings.WeekNumberStyle = weekNumberStyle;
schedule.MonthViewSettings = monthViewSettings;
{% endhighlight %}
{% endtabs %}

![Week number customization in schedule xamarin android](monthview_images/weeknumberstyle.png)

## Month Label Formatting 
You can change the Format of the Month date and day labels string in the Schedule using [DateFormat](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthLabelSettings.html#Com_Syncfusion_Schedule_MonthLabelSettings_DateFormat), [DayFormat](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthLabelSettings.html#Com_Syncfusion_Schedule_MonthLabelSettings_DayFormat) properties of [MonthLabelSettings](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthViewSettings.html#Com_Syncfusion_Schedule_MonthViewSettings_MonthLabelSettings) in `MonthViewSettings`.
{% tabs %}
{% highlight c# %}
//creating new instance for MonthLabelSettings
MonthLabelSettings monthLabelSettings = new MonthLabelSettings();
monthLabelSettings.DayFormat = "EEEE";
monthLabelSettings.DateFormat = "dd";
monthViewSettings.MonthLabelSettings = monthLabelSettings;
{% endhighlight %}
{% endtabs %}

![Month label formatting in schedule xamarin android](monthview_images/monthlabelformat.png)

## View Header Appearance  
You can customize the View Header appearance by using [ViewHeaderStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.ViewHeaderStyle.html) property in SfSchedule. View Header [BackgroundColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.ViewHeaderStyle.html#Com_Syncfusion_Schedule_ViewHeaderStyle_BackgroundColor), [DayTextColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.ViewHeaderStyle.html#Com_Syncfusion_Schedule_ViewHeaderStyle_DayTextColor), [DayTextSize](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.ViewHeaderStyle.html#Com_Syncfusion_Schedule_ViewHeaderStyle_DayTextSize) and [DayTextStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.ViewHeaderStyle.html#Com_Syncfusion_Schedule_ViewHeaderStyle_DayTextStyle) can be customized using `ViewHeaderStyle` properties.

{% tabs %}
{% highlight c# %}
//creating new instance for viewHeaderStyle
ViewHeaderStyle viewHeaderStyle = new ViewHeaderStyle();
viewHeaderStyle.DayTextStyle = Typeface.Create("Arial", TypefaceStyle.Italic);
viewHeaderStyle.DayTextSize = 15;
viewHeaderStyle.DayTextColor = Color.White;
viewHeaderStyle.BackgroundColor = Color.Blue;
schedule.ViewHeaderStyle = viewHeaderStyle;
{% endhighlight %}
{% endtabs %}

![Month view header customization in schedule xamarin android](monthview_images/viewheaderstyle.png)

### ViewHeader Date Format
You can customize the date and day format of `SfSchedule` ViewHeader by using [DateFormat](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthLabelSettings.html#Com_Syncfusion_Schedule_MonthLabelSettings_DateFormat) and [DayFormat](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthLabelSettings.html#Com_Syncfusion_Schedule_MonthLabelSettings_DayFormat) properties of `MonthLabelSettings`.

{% tabs %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.MonthView;
//Creating new instance of MonthViewSettings
MonthViewSettings monthViewSettings = new MonthViewSettings();
//Creating new instance of MonthLabelSettings
MonthLabelSettings monthLabelSettings = new MonthLabelSettings();
//Customizing date format
monthLabelSettings.DateFormat = "dd";
monthLabelSettings.DayFormat = "EEEE";
monthViewSettings.MonthLabelSettings = monthLabelSettings;
schedule.MonthViewSettings = monthViewSettings;
{% endhighlight %}
{% endtabs %}

![Month view header format in schedule xamarin android](monthview_images/DateFormat_Month.png)

### ViewHeader Tapped Event
You can handle single tap action of ViewHeader by using [ViewHeaderTapped](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html) event of `SfSchedule`. This event will be triggered when the ViewHeader is Tapped. This event contains [ViewHeaderTappedEventArgs](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.ViewHeaderTappedEventArgs.html) argument which holds [Calendar](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.HeaderTappedEventArgs.html#Com_Syncfusion_Schedule_HeaderTappedEventArgs_Calendar) details in it.

{% tabs %}
{% highlight c# %}
//Creating  new instance of Schedule
SfSchedule schedule = new SfSchedule();
schedule.ScheduleView = ScheduleView.MonthView;
schedule.ViewHeaderTapped += Handle_ViewHeaderTapped;

...

void Handle_ViewHeaderTapped(object sender, ViewHeaderTappedEventArgs e)
{
    var calendar = e.Calendar;
}
{% endhighlight %}
{% endtabs %}

## MonthCell Appearance 
You can customize the Month view cell in three ways,

* [Customize month cell using style](#customize-month-cell-using-style)
* [Customize month cell using event](#customize-month-cell-using-event)
* [Customize month cell with custom UI](#customize-month-cell-with-custom-ui)

### Customize month cell using style
By using [MonthCellStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthCellStyle.html) of `SfSchedule` you can customize the month cell properties such as [BackgroundColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthCellStyle.html#Com_Syncfusion_Schedule_MonthCellStyle_BackgroundColor), [NextMonthBackgroundColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthCellStyle.html#Com_Syncfusion_Schedule_MonthCellStyle_NextMonthBackgroundColor), [NextMonthTextColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthCellStyle.html#Com_Syncfusion_Schedule_MonthCellStyle_NextMonthTextColor), [PreviousMonthBackgroundColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthCellStyle.html#Com_Syncfusion_Schedule_MonthCellStyle_PreviousMonthBackgroundColor), [PreviousMonthTextColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthCellStyle.html#Com_Syncfusion_Schedule_MonthCellStyle_PreviousMonthTextColor), [TextColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthCellStyle.html#Com_Syncfusion_Schedule_MonthCellStyle_TextColor), [TextSize](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthCellStyle.html#Com_Syncfusion_Schedule_MonthCellStyle_TextSize), [TextStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthCellStyle.html#Com_Syncfusion_Schedule_MonthCellStyle_TextStyle), [TodayBackgroundColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthCellStyle.html#Com_Syncfusion_Schedule_MonthCellStyle_TodayBackgroundColor) and [TodayTextColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthCellStyle.html#Com_Syncfusion_Schedule_MonthCellStyle_TodayTextColor).
   
{% tabs %}
{% highlight c# %}
//creating new instance for MonthCellStyle
MonthCellStyle monthCellStyle = new MonthCellStyle();
monthCellStyle.TextSize = 15;
monthCellStyle.TextColor = Color.White;
monthCellStyle.TextStyle = Typeface.Create("Arial", TypefaceStyle.BoldItalic);
monthCellStyle.BackgroundColor = Color.Blue;
monthCellStyle.TodayTextColor = Color.White;
monthCellStyle.TodayBackgroundColor = Color.Red;
monthCellStyle.PreviousMonthTextColor = Color.White;
monthCellStyle.PreviousMonthBackgroundColor = Color.LightGray;
monthCellStyle.NextMonthTextColor = Color.White;
monthCellStyle.NextMonthBackgroundColor = Color.LightGray;
schedule.MonthCellStyle = monthCellStyle;
{% endhighlight %}
{% endtabs %}

![Month cell customization using styling in schedule xamarin android](monthview_images/monthcellstyle.png)
    
### Customize month cell using event
By using [MonthCellLoaded](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html) event in `SfSchedule`, you can customize the month cell properties in the run time. In `MonthCellLoaded` event, arguments such as [CellStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthCellLoadedEventArgs.html#Com_Syncfusion_Schedule_MonthCellLoadedEventArgs_CellStyle), [Appointments](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthCellLoadedEventArgs.html#Com_Syncfusion_Schedule_MonthCellLoadedEventArgs_Appointments), [Calendar](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthCellLoadedEventArgs.html#Com_Syncfusion_Schedule_MonthCellLoadedEventArgs_Calendar), [Bounds](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthCellLoadedEventArgs.html#Com_Syncfusion_Schedule_MonthCellLoadedEventArgs_Bounds), [View](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthCellLoadedEventArgs.html#Com_Syncfusion_Schedule_MonthCellLoadedEventArgs_View) and boolean properties such as [IsToday](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthCellLoadedEventArgs.html#Com_Syncfusion_Schedule_MonthCellLoadedEventArgs_IsToday), [IsNextMonthDate](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthCellLoadedEventArgs.html#Com_Syncfusion_Schedule_MonthCellLoadedEventArgs_IsNextMonthDate), [IsPreviousMonthDate](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthCellLoadedEventArgs.html#Com_Syncfusion_Schedule_MonthCellLoadedEventArgs_IsPreviousMonthDate) and [IsBlackOutDate](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthCellLoadedEventArgs.html#Com_Syncfusion_Schedule_MonthCellLoadedEventArgs_IsBlackoutDate) are in the [MonthCellLoadedEventArgs](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthCellLoadedEventArgs.html). 

{% tabs %}
{% highlight c# %}
schedule.MonthCellLoaded += Schedule_MonthCellLoaded;

...

void Schedule_MonthCellLoaded(object sender, MonthCellLoadedEventArgs e)
{
    e.CellStyle = new CellStyle():
    if (e.IsToday)
    {
        e.CellStyle.TextSize = 15;
        e.CellStyle.BackgroundColor = Color.Red;
        e.CellStyle.TextColor = Color.White;
        e.CellStyle.TextStyle = Typeface.Create("Arial", TypefaceStyle.Bold);
    }
    else if (e.IsNextMonthDate)
    {
        e.CellStyle.TextSize = 12;
        e.CellStyle.BackgroundColor = Color.White;
        e.CellStyle.TextColor = Color.Gray;
        e.CellStyle.TextStyle = Typeface.Create("Arial", TypefaceStyle.Normal);
    }
    else if (e.IsPreviousMonthDate)
    {
        e.CellStyle.TextSize = 12;
        e.CellStyle.BackgroundColor = Color.White;
        e.CellStyle.TextColor = Color.Gray;
        e.CellStyle.TextStyle = Typeface.Create("Arial", TypefaceStyle.Normal);
    }
    else if (e.IsBlackoutDate)
    {
        e.CellStyle.TextSize = 15;
        e.CellStyle.BackgroundColor = Color.Black;
        e.CellStyle.TextColor = Color.White;
        e.CellStyle.TextStyle = Typeface.Create("Arial", TypefaceStyle.Bold);
    }
    else
    {
        e.CellStyle.TextSize = 15;
        e.CellStyle.BackgroundColor = Color.Blue;
        e.CellStyle.TextColor = Color.White;
        e.CellStyle.TextStyle = Typeface.Create("Arial", TypefaceStyle.BoldItalic);
    }
}
{% endhighlight %}
{% endtabs %}

![Month cell customization using events in schedule xamarin android](monthview_images/monthcellstyle_event.png)

#### Customize month cell with custom UI 
You can set the Custom UI for the month cell using [View](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthCellLoadedEventArgs.html#Com_Syncfusion_Schedule_MonthCellLoadedEventArgs_View) property of `MonthCellLoadedEventArgs` in the `MonthCellLoaded` event of `SfSchedule`.

{% tabs %}
{% highlight c# %}
schedule.MonthCellLoaded += Schedule_MonthCellLoaded;

...

void Schedule_MonthCellLoaded(object sender, MonthCellLoadedEventArgs e)
{
    Button button = new Button(this);
    button.Text = e.Calendar.Time.GetDate().ToString();
    button.SetTextColor(Color.White);
    button.SetBackgroundColor(Color.Blue);
    e.View = button;
    if (e.IsToday)
    {
        button.SetBackgroundColor(Color.Red);
        button.SetTextColor(Color.White);
    }
}
{% endhighlight %}
{% endtabs %}

![Month cell customization using custom view in schedule xamarin android](monthview_images/monthcellcustomview.png)

## Getting Inline Appointment details
Using [ScheduleAppointment](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthInlineAppointmentTappedEventArgs.html#Com_Syncfusion_Schedule_MonthInlineAppointmentTappedEventArgs_ScheduleAppointment) argument in the [MonthInlineAppointmentTappedEventArgs](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthInlineAppointmentTappedEventArgs.html) of [MonthInlineAppointmentTapped](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html) event, you can get the details Month Inline Appointments details while tapping the specific appointment. You can do the required functions while tapping the inline appointment using this event. 

{% tabs %}
{% highlight c# %}
schedule.MonthInlineAppointmentTapped += Schedule_MonthInlineAppointmentTapped;

...

void Schedule_MonthInlineAppointmentTapped(object sender, MonthInlineAppointmentTappedEventArgs e)
{
    var appointment = (e.ScheduleAppointment as ScheduleAppointment);
    Toast.MakeText(this, appointment.Subject + " * " + appointment.StartTime.Time.ToString(), ToastLength.Long).Show();
}
{% endhighlight %}
{% endtabs %}

![Month inline appointment details using MonthInlineAppointmentTapped in schedule xamarin android](monthview_images/inlineappointmentdetails.png)

## InlineView Appearance  
By using [MonthInlineLoaded](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html) in `SfSchedule`, you can customize the month inline view properties in the run time. In `MonthInlineLoadedEvent`, arguments such as [MonthInlineViewStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthInlineViewStyle.html), [Appointments](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthInlineLoadedEventArgs.html#Com_Syncfusion_Schedule_MonthInlineLoadedEventArgs_Appointments) and [Calendar](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthInlineLoadedEventArgs.html#Com_Syncfusion_Schedule_MonthInlineLoadedEventArgs_Calendar) are in the MonthInlineLoadedEventArgs.

{% tabs %}
{% highlight c# %}
schedule.MonthInlineLoaded += Schedule_MonthInlineLoaded;

...

void Schedule_MonthInlineLoaded(object sender, MonthInlineLoadedEventArgs e)
{
    MonthInlineViewStyle monthInlineViewStyle = new MonthInlineViewStyle();
    monthInlineViewStyle.TextSize = 20;
    monthInlineViewStyle.BackgroundColor = Color.Blue;
    monthInlineViewStyle.TextColor = Color.Green;
    monthInlineViewStyle.TextStyle = Typeface.Create("Arial", TypefaceStyle.BoldItalic);
    monthInlineViewStyle.TimeTextColor = Color.Red;
    monthInlineViewStyle.TimeTextSize = 12;
    monthInlineViewStyle.TimeTextFormat = "hh a";
    e.MonthInlineViewStyle = monthInlineViewStyle;
}
{% endhighlight %}
{% endtabs %}

![Month inline appointment details formatting and appearance in schedule xamarin android](monthview_images/inlineviewstyle.png)

## Inline Appointment Appearance 
You can customize the Month inline view Appointment by using [MonthInlineAppointmentLoaded](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html) in `SfSchedule`, using [View](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthInlineAppointmentLoadedEventArgs.html#Com_Syncfusion_Schedule_MonthInlineAppointmentLoadedEventArgs_View) of [MonthInlineAppointmentLoadedEventArgs](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthInlineAppointmentLoadedEventArgs.html) argument. You can get the details of Appointment in the [Appointment](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthInlineAppointmentLoadedEventArgs.html#Com_Syncfusion_Schedule_MonthInlineAppointmentLoadedEventArgs_Appointment) argument.

{% tabs %}
{% highlight c# %}
schedule.MonthInlineAppointmentLoaded += Schedule_MonthInlineAppointmentLoaded;

...

void Schedule_MonthInlineAppointmentLoaded(object sender, MonthInlineAppointmentLoadedEventArgs e)
{
    var appointment = (e.Appointment as ScheduleAppointment);
    Button button = new Button(this);
    button.Text = "Appointment :" + appointment.Subject;
    button.SetBackgroundColor(Color.Blue);
    button.SetTextColor(Color.White);
    e.View = button;
}
{% endhighlight %}
{% endtabs %}

![Custom month inline appointment in schedule xamarin android](monthview_images/inlinecustomview.png)

## Selection
You can customize the default appearance of selection UI in the month cells.

* [Selection text color customization](#selection-text-color-customization)
* [Selection customization using style](#selection-customization-using-style)
* [Selection customization using custom View](#selection-customization-using-custom-view)

### Selection text color customization
Month cell Selection Text Color can be customized using [SelectionTextColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthViewSettings.html#Com_Syncfusion_Schedule_MonthViewSettings_SelectionTextColor) property of `MonthViewSettings`.

{% tabs %}
{% highlight c# %}
//creating new instance for MonthViewSettings
MonthViewSettings monthViewSettings = new MonthViewSettings();
monthViewSettings.SelectionTextColor = Color.Red;
schedule.MonthViewSettings = monthViewSettings;
{% endhighlight %}
{% endtabs %}

![Month selection text color customization in schedule xamarin android](monthview_images/selectiontextcolor.png)

### Selection customization using style
You can customize the month cell selection by using [SelectionStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_SelectionStyle) property of `SfSchedule`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.MonthView;
//Create new instance of SelectionStyle
SelectionStyle selectionStyle = new SelectionStyle();
selectionStyle.BackgroundColor = Color.Blue;
selectionStyle.BorderColor = Color.Black;
selectionStyle.BorderThickness = 5;
selectionStyle.CornerRadius = 5;
schedule.SelectionStyle = selectionStyle;
{% endhighlight %}
{% endtabs %}

![Month selection style customization in schedule xamarin android](monthview_images/SelectionStyle_Month.png)

### Selection customization using custom View
You can replace the default selection UI with your custom view by setting [SelectionView](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_SelectionView) property of `SfSchedule`.

{% tabs %}
{% highlight C# %}
schedule.ScheduleView = ScheduleView.MonthView;
//Add the CustomView
Button customView = new Button(this);
customView.Text = "+NewEvent";
customView.SetBackgroundColor(Color.Rgb(255, 152, 0));
customView.SetTextColor(Color.White);
schedule.SelectionView = customView;
{% endhighlight %}
{% endtabs %}

![custom month selection in schedule xamarin android](monthview_images/SelectionView_Month.png)

### Programmatic selection
You can programmatically select the specific cell by setting corresponding date to [SelectedDate](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_SelectedDate) property of `SfSchedule`. By default, it is null.

{% tabs %}
{% highlight C# %}
// Creating instance of calendar
Calendar calendar = Calendar.Instance;

// Setting a date and time to select
currentDate.Set(2017, 09, 04);
schedule.SelectedDate = currentDate;
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

![Month programatic selection in schedule xamarin android](monthview_images/selection_Month.png)

## Today Background Color
You can customize the current date background of  `SfSchedule`  by using [TodayBackgroundColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSchedule.XForms.MonthViewSettings.html#Syncfusion_SfSchedule_XForms_MonthViewSettings_TodayBackground) property of `MonthViewSettings`.

{% tabs %}
{% highlight c# %}
schedule.ScheduleView = ScheduleView.MonthView;
//Creating new instance of MonthViewSettings
MonthViewSettings monthViewSettings = new MonthViewSettings();
//Customizing background color
monthViewSettings.TodayBackgroundColor = Color.Red;
schedule.MonthViewSettings = monthViewSettings;
{% endhighlight %}
{% endtabs %}

![Month today background color customization in schedule xamarin android](monthview_images/TodayBackground.png)

## Custom Font

You can change the appearance of Font by setting the TextStyle property of following classes.

* [ViewHeaderStyle](https://help.syncfusion.com/xamarin-android/sfschedule/dayview#viewheader-appearance) - You can change the appearance of [ViewHeaderStyle](https://help.syncfusion.com/xamarin-android/sfschedule/dayview#viewheader-appearance) by setting the [DayTextStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.ViewHeaderStyle.html#Com_Syncfusion_Schedule_ViewHeaderStyle_DayTextStyle) and [DateTextStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.ViewHeaderStyle.html#Com_Syncfusion_Schedule_ViewHeaderStyle_DateTextStyle) properties of Schedule `ViewHeaderStyle`.
* [MonthCellStyle](https://help.syncfusion.com/xamarin-android/sfschedule/monthview#monthcell-appearance) - You can change the appearance of [MonthCellStyle](https://help.syncfusion.com/xamarin-android/sfschedule/monthview#monthcell-appearance) by setting the [TextStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthCellStyle.html#Com_Syncfusion_Schedule_MonthCellStyle_TextStyle) property of Schedule `MonthCellStyle`.
* [MonthInlineViewStyle](https://help.syncfusion.com/xamarin-android/sfschedule/monthview#inlineview-appearance) - You can change the appearance of [MonthInlineViewStyle](https://help.syncfusion.com/xamarin-android/sfschedule/monthview#inlineview-appearance) by setting the [TextStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.MonthCellStyle.html#Com_Syncfusion_Schedule_MonthCellStyle_TextStyle) property of Schedule `MonthInlineViewStyle`.
* [WeekNumberStyle](https://help.syncfusion.com/xamarin-android/sfschedule/monthview#week-number-appearance) - You can change the appearance of [WeekNumberStyle](https://help.syncfusion.com/xamarin-android/sfschedule/monthview#week-number-appearance) by setting the [TextStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.WeekNumberStyle.html#Com_Syncfusion_Schedule_WeekNumberStyle_TextStyle) property of Schedule `WeekNumberStyle`.

{% tabs %}
{% highlight c# %}
viewHeaderStyle.DayTextStyle = Typeface.CreateFromAsset(Assets,"Lobster-Regular.ttf");
{% endhighlight %}
{% endtabs %}

![Month view header custom font support in schedule xamarin android](monthview_images/customfontviewheader_month.png)

{% tabs %}
{% highlight c# %}
monthCellStyle.TextStyle = Typeface.CreateFromAsset(Assets,"Lobster-Regular.ttf");
{% endhighlight %}
{% endtabs %}

![Month view cell custom font support in schedule xamarin android](monthview_images/customfontmonthcell.png)

{% tabs %}
{% highlight c# %}
schedule.MonthInlineLoaded += Schedule_MonthInlineLoaded;

...

void Schedule_MonthInlineLoaded(object sender, MonthInlineLoadedEventArgs e)
{
	MonthInlineViewStyle monthInlineViewStyle = new MonthInlineViewStyle();
	monthInlineViewStyle.TextStyle = Typeface.CreateFromAsset(Assets,"Lobster-Regular.ttf");
	e.MonthInlineViewStyle = monthInlineViewStyle;
}
{% endhighlight %}
{% endtabs %}

![Month view inline custom font support in schedule xamarin android](monthview_images/customfontinline.png)

{% tabs %}
{% highlight c# %}
weekNumberStyle.TextStyle = Typeface.CreateFromAsset(Assets,"Lobster-Regular.ttf");		
{% endhighlight %}
{% endtabs %}

![Month view week number custom font support in schedule xamarin android](monthview_images/customfontweeknumber.png)

Following steps will explain how to configure the custom fonts.

### Custom Font Setting in Xamarin.Android

* Add your Custom Font[e.g. Lobster-Regular.ttf] to the Assets folder of the  Xamarin.Android project.
* Then, use the Custom Font name as text style.





