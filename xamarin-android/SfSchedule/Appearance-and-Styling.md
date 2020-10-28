---
layout: post
title: Appearance & Stylings in Schedule
description: How to Customize Header and time slots.
platform: Xamarin.Android
control: SfSchedule
documentation: ug
---

# Appearance & Styling

## Header Customization

You can customize the header of the Schedule using `HeaderStyle` and `HeaderHeight` property in schedule.

### Header Height

You can customize the height for the Header in Schedule using `HeaderHeight` in schedule.

{% highlight c# %}

	schedule.HeaderHeight = 50;

{% endhighlight %}

### Labels

you can change the header format and style using `HeaderStyle` property in schedule.

#### Format

You can change the header text format and size using `ScheduleDateHeaderSize` and `ScheduleDateHeaderFormat` property in `HeaderStyle`

{% highlight c# %}

	schedule.ScheduleDateHeaderSize = 30;
	schedule.ScheduleDateHeaderFormat = "MMM yyyy";

{% endhighlight %}

#### Fonts and colors

You can change the background color,text style and text size using properties such as `BackgroundColor`,`TextStyle`, `TextSize` of Header using `HeaderStyle` property in schedule.

{% highlight c# %}

	HeaderStyle headerStyle = new HeaderStyle();
	headerStyle.BackgroundColor = Color.Rgb(251, 211, 201);
	headerStyle.TextStyle = Typeface.DefaultBold;
	headerStyle.TextSize= 12;
    headerStyle.TextColor = Color.White;
	schedule.HeaderStyle = headerStyle;

{% endhighlight %}

## View Header Customization

You can customize the header of the Schedule using `ViewHeaderStyle` and `ViewHeaderHeight` property in schedule.

### Labels

#### Fonts and Colors

You can change the background color,text style and text size using properties such as `BackgroundColor`,`DateTextStyle`, `DayTextStyle`, `DayTextColor`, `DateTextColor`,`DateTextSize`, `DayTextSize` of ViewHeader using `ViewHeaderStyle` property in schedule.

{% highlight c# %}

	ViewHeaderStyle viewHeaderStyle = new ViewHeaderStyle(schedule);
	viewHeaderStyle.BackgroundColor = Color.Rgb(251, 211, 201);
	viewHeaderStyle.DayTextColor= Color.White;
	viewHeaderStyle.DateTextColor= Color.White;
	viewHeaderStyle.DateTextSize = 15;
	viewHeaderStyle.DayTextSize = 10;
	viewHeaderStyle.DateTextStyle = Typeface.Default;
	viewHeaderStyle.DayTextStyle = Typeface.DefaultBold;
	schedule.ViewHeaderStyle = viewHeaderStyle;

{% endhighlight %}

### ViewHeader Height

You can customize the height for the Header in Schedule using `HeaderHeight` in schedule.

{% highlight c# %}

	schedule.ViewHeaderHeight = 50;

{% endhighlight %}

![](Appearance_images/Header.png)

## Timeslots customization

### Custom Day View

#### Non-Working Hours 

You can differentiate working hours with non-working hour timeslots by its color using `NonWorkingHoursTimeSlotBorderColor`, `NonWorkingHoursTimeSlotColor` properties of `DayViewSettings`.

{% highlight c# %}

	//creating new instance for schedule
	SfSchedule schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.DayView;

	//setting day view settings properties
	DayViewSettings dayViewSettings = new DayViewSettings();
	dayViewSettings.NonWorkingHoursTimeSlotBorderColor = Color.Gray;
	dayViewSettings.NonWorkingHoursTimeSlotColor = Color.Silver;
	schedule.DayViewSettings=dayViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

#### Timeslots 

You can differentiate working hours with non-working hour timeslots by its color using  `TimeSlotColor`,`TimeSlotBorderColor` and `TimeSlotBorderStrokeWidth` properties of `DayViewSettings`.

{% highlight c# %}

	//creating new instance for schedule
	SfSchedule schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.DayView;

	//setting day view settings properties
	DayViewSettings dayViewSettings = new DayViewSettings();
	dayViewSettings.TimeSlotColor = Color.Yellow;
	dayViewSettings.TimeSlotBorderColor = Color.Aqua;
	dayViewSettings.TimeSlotBorderStrokeWidth = 5;
	schedule.DayViewSettings=dayViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

#### Lines

You can differentiate the timeslot panel using `VerticalLineColor` and `VerticalLineStrokeWidth` properties of `DayViewSettings`.

{% highlight c# %}

	//creating new instance for schedule
	SfSchedule schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.DayView;

	//setting day view settings properties
	DayViewSettings dayViewSettings = new DayViewSettings();
	dayViewSettings.VerticalLineColor = Color.Green;
	dayViewSettings.VerticalLineStrokeWidth = 5;
	schedule.DayViewSettings=dayViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

#### Labels

You can change the format , colors, size, style of text using `DateFormat` and `DayFormat`, `DateLabelSize`,`DayLabelSize`,`TimeFormat`, `TimeLabelColor`,`TimeLabelSize` properties of `DayLabelSettings` in `DayViewSettings`.

{% highlight c# %}

	//creating new instance for schedule
	SfSchedule schedule = new SfSchedule(this);
	
	//setting schedule view
	schedule.ScheduleView = ScheduleView.DayView;

	DayViewSettings dayViewSettings = new DayViewSettings();
	DayLabelSettings dayLabelSettings = new DayLabelSettings();
	dayLabelSettings.DateFormat = "d/M/yyyy";
	dayLabelSettings.DateLabelSize = 10;
	dayLabelSettings.DayLabelSize = 10;
	dayLabelSettings.DayFormat = "ddd";
	dayLabelSettings.TimeFormat = "hh mm";
	dayLabelSettings.TimeLabelColor = Color.Blue;
	dayLabelSettings.TimeLabelSize = 10;
	dayViewSettings.DayLabelSettings = dayLabelSettings;
	schedule.DayViewSettings = dayViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

#### All Day Appointments color

You can change the all day appointment panel color using the property `AllDayAppointmentBackgroundColor` of `DayViewSettings`.

{% highlight c# %}

	//creating new instance for schedule
	SfSchedule schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.DayView;

	//setting day view settings properties
	DayViewSettings dayViewSettings = new DayViewSettings();
	dayViewSettings.AllDayAppointmentBackgroundColor = Color.Pink;
	schedule.DayViewSettings=dayViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

![](Appearance_images/Day_Nonworking.png)

### Custom Week View

#### Non-Working Hours 

You can differentiate working hours with non-working hour timeslots by its color using `NonWorkingHoursTimeSlotBorderColor`, `NonWorkingHoursTimeSlotColor` properties of `WeekViewSettings`.

{% highlight c# %}

	//creating new instance for schedule
	SfSchedule schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.WeekView;

	//setting week view settings properties
	WeekViewSettings weekViewSettings = new WeekViewSettings();
	weekViewSettings.NonWorkingHoursTimeSlotBorderColor = Color.Gray;
	weekViewSettings.NonWorkingHoursTimeSlotColor = Color.Silver;
	schedule.WeekViewSettings = weekViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

#### Timeslots 

You can differentiate working hours with non-working hour timeslots by its color using `TimeSlotColor`,`TimeSlotBorderColor` and `TimeSlotBorderStrokeWidth` properties of `WeekViewSettings`.

{% highlight c# %}

	//creating new instance for schedule
	SfSchedule schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.WeekView;

	//setting week view settings properties
	WeekViewSettings weekViewSettings = new WeekViewSettings();
	weekViewSettings.TimeSlotBorderColor = Color.Aqua;
	weekViewSettings.TimeSlotColor = Color.Yellow;
	weekViewSettings.TimeSlotBorderStrokeWidth = 5;

	schedule.WeekViewSettings = weekViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

#### Lines

You can differentiate the timeslot panel using `VerticalLineColor` and `VerticalLineStrokeWidth` properties of `WeekViewSettings`.

{% highlight c# %}

	//creating new instance for schedule
	SfSchedule schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.WeekView;

	WeekViewSettings weekViewSettings = new WeekViewSettings ();
	weekViewSettings.VerticalLineColor = Color.Green;
	weekViewSettings.VerticalLineStrokeWidth = 5;
	schedule.WeekViewSettings = weekViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

#### Labels

You can change the format , colors, size, style of text using `DateFormat` and `DayFormat`, `DateLabelSize`,`DayLabelSize`,`TimeFormat`, `TimeLabelColor`,`TimeLabelSize` properties of `WeekLabelSettings` in `WeekViewSettings`.

{% highlight c# %}

	//creating new instance for schedule
	SfSchedule schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.WeekView;

	WeekViewSettings weekViewSettings = new WeekViewSettings();
	WeekLabelSettings weekLabelSettings = new WeekLabelSettings();
	weekLabelSettings.DateFormat = "d/M/yyyy";
	weekLabelSettings.DateLabelSize = 10;
	weekLabelSettings.DayLabelSize = 10;
	weekLabelSettings.DayFormat = "ddd";
	weekLabelSettings.TimeFormat = "hh mm";
	weekLabelSettings.TimeLabelColor = Color.Blue;
	weekLabelSettings.TimeLabelSize = 10;
	weekViewSettings.WeekLabelSettings = weekLabelSettings;
	schedule.WeekViewSettings = weekViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

#### All Day Appointments Color

You can change the all day appointment panel color using the property `AllDayAppointmentBackgroundColor` of `WeekViewSettings`.

{% highlight c# %}

	//creating new instance for schedule
	SfSchedule schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.WeekView;

	//setting week view settings properties
	WeekViewSettings weekViewSettings = new WeekViewSettings();
	weekViewSettings.AllDayAppointmentBackgroundColor = Color.Pink;
	schedule.WeekViewSettings = weekViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

![](Appearance_images/Week_Nonworking.png)

### Custom Work Week View

#### Non-Working Hours 

You can also differentiate working hours with non-working hour timeslots by its color using `NonWorkingHoursTimeSlotBorderColor`, `NonWorkingHoursTimeSlotColor` properties of `WorkWeekViewSettings`.

{% highlight c# %}

	//creating new instance for schedule
	SfSchedule schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.WorkWeekView;

	//setting workweek view settings properties
	WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings ();
	workWeekViewSettings.NonWorkingHoursTimeSlotBorderColor = Color.Gray;
	workWeekViewSettings.NonWorkingHoursTimeSlotColor = Color.Silver;
	schedule.WorkWeekViewSettings = workWeekViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

#### Timeslots

You can also differentiate working hours with non-working hour timeslots by its color using `TimeSlotColor`,`TimeSlotBorderColor` and `TimeSlotBorderStrokeWidth` properties of `WorkWeekViewSettings`.

{% highlight c# %}

	//creating new instance for schedule
	SfSchedule schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.WorkWeekView;

	//setting workweek view settings properties
	WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings ();
	workWeekViewSettings.TimeSlotBorderColor = Color.Aqua;
	workWeekViewSettings.TimeSlotColor = Color.Yellow;
	workWeekViewSettings.TimeSlotBorderStrokeWidth = 5;
	schedule.WorkWeekViewSettings = workWeekViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

#### Lines

You can differentiate the timeslot panel using `VerticalLineColor` and `VerticalLineStrokeWidth` properties of `WorkWeekViewSettings`.

{% highlight c# %}

	//creating new instance for schedule
	SfSchedule schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.WorkWeekView;

	WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings ();
	workWeekViewSettings.VerticalLineColor = Color.Green;
	workWeekViewSettings.VerticalLineStrokeWidth = 5;
	schedule.WorkWeekViewSettings = workWeekViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

#### Labels

You can change the format , colors, size, style of text using `DateFormat` and `DayFormat`, `DateLabelSize`,`DayLabelSize`,`TimeFormat`, `TimeLabelColor`,`TimeLabelSize` properties of `WorkWeekLabelSettings` in `WorkWeekViewSettings`.

{% highlight c# %}

	//creating new instance for schedule
	SfSchedule schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.WorkWeekView;

	WorkWeekViewSettings workweekViewSettings = new WorkWeekViewSettings();
	WorkWeekLabelSettings workWeekLabelSettings = new WorkWeekLabelSettings();
	workWeekLabelSettings.DateFormat = "d/M/yyyy";
	workWeekLabelSettings.DateLabelSize = 10;
	workWeekLabelSettings.DayLabelSize = 10;
	workWeekLabelSettings.DayFormat = "ddd";
	workWeekLabelSettings.TimeFormat = "hh mm";
	workWeekLabelSettings.TimeLabelColor = Color.Blue;
	workWeekLabelSettings.TimeLabelSize = 10;
	workweekViewSettings.WorkWeekLabelSettings = workWeekLabelSettings;
	schedule.WorkWeekViewSettings = workweekViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

#### All Day Appointments Panel

You can change the all day appointment panel color using the property `AllDayAppointmentBackgroundColor` of `WorkWeekViewSettings`.

{% highlight c# %}

	//creating new instance for schedule
	SfSchedule schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.WorkWeekView;

	//setting workweek view settings properties
	WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
	workWeekViewSettings.AllDayAppointmentBackgroundColor = Color.Pink;
	schedule.WorkWeekViewSettings = workWeekViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

![](Appearance_images/WorkWeek_Nonworking.png)

### Interval

You can change the time interval and time interval height using `TimeInterval` and `TimeIntervalHeight` in schedule.

{% highlight c# %}

	schedule.TimeInterval = 120;
	schedule.TimeIntervalHeight = 100;

{% endhighlight %}

>**NOTE** : `TimeInterval` value should be given in minutes.

![](Appearance_images/TimeInterval.png)