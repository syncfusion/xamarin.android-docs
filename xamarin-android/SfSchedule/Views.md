---
layout: post
title: Types of Schedule Views.
description: How to create Views in Schedule control.
platform: Xamarin.Android
control: SfSchedule
documentation: ug
---

# Views

Schedule control provides four different types of views to display dates. Day view, Week view, Work Week view and Month view. It can be assigned to the schedule control by using `ScheduleView` property. Based on the user’s preference appointments can be viewed in any of the four type of view available. By default schedule control is assigned with day view.

## Day View

Day view is used to display a single day; current day will be visible by default. Appointments on a specific day will be arranged in respective timeslots based on its duration.

{% highlight c# %}

	//creating new instance for schedule
	schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.DayView;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

### Settings

#### Date Time Formating

You can format the date and time string in the schedule control using `DayLabelSettings` of  `DayViewSettings` and the size of those strings are also customizable.

You can differentiate the timeslot panel using `VerticalLineColor` and `VerticalLineStrokeWidth` properties of `DayViewSettings`.To know more about customization of working hours refer [Timeslots Customization](/xamarin-android/sfschedule/appearance-and-styling "Timeslots Customization")

{% highlight c# %}

	//creating new instance for schedule
	schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.DayView;

	//setting day view settings properties
	DayViewSettings dayViewSettings = new DayViewSettings();
	dayViewSettings.WorkStartHour=10;
	dayViewSettings.WorkEndHour=18;
	schedule.DayViewSettings=dayViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

#### Working Hours

You can modify the working hours using `WorkStartHour` and `WorkEndHour` properties of `DayViewSettings`.

You can also differentiate working hours with non-working hour timeslots by its color using `NonWorkingHoursTimeSlotBorderColor`, `NonWorkingHoursTimeSlotColor`, `TimeSlotColor`,`TimeSlotBorderColor` and `TimeSlotBorderStrokeWidth` properties of `DayViewSettings`.To know more about customization of working hours refer [Timeslots Customization](/xamarin-android/sfschedule/appearance-and-styling "Timeslots Customization")

{% highlight c# %}

	//creating new instance for schedule
	schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.DayView;

	//setting day view settings properties
	DayViewSettings dayViewSettings = new DayViewSettings();
	dayViewSettings.WorkStartHour = 10;
	dayViewSettings.WorkEndHour = 18;
	schedule.DayViewSettings=dayViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

#### All Day Appointments Color

You can view All day appointments in separate panel and the panels visibility can be enabled by setting `ShowAllDay` property of DayViewSettings as true.Also you can change the all day appointment panel color using the property `AllDayAppointmentBackgroundColor`. To know more about customization of working hours refer [Timeslots Customization](/xamarin-android/sfschedule/appearance-and-styling "Timeslots Customization")

{% highlight c# %}

	//creating new instance for schedule
	schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.DayView;

	//setting day view settings properties
	DayViewSettings dayViewSettings = new DayViewSettings();
	dayViewSettings.ShowAllDay=true;
	schedule.DayViewSettings=dayViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

![](Views_images/DayView.png)

>**Note**:These properties and customizations are applicable only for Day View. Customizations for other views are discussed under the respective views.

## Week View

To view all the seven days of a particular week, by default if will be current week. Appointments arranged in timeslots based on its duration with respective day of the week.

{% highlight c# %}

	//creating new instance for schedule
	schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.WeekView;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

### Settings

#### Date Time Formating

You can format the date and time string in the schedule control using `WeekLabelSettings` of `WeekViewSettings` and the size of those strings are also customizable.

Also you can differentiate the timeslot panel using `VerticalLineColor` and `VerticalLineStrokeWidth` properties of `WeekViewSettings`.To know more about customization of working hours refer [Timeslots Customization](/xamarin-android/sfschedule/appearance-and-styling "Timeslots Customization")

{% highlight c# %}

	//creating new instance for schedule
	schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.WeekView;

	//setting label size and formats
	WeekLabelSettings weekLabelSettings = new WeekLabelSettings();
	weekLabelSettings.TimeLabelSize = 14;
	weekLabelSettings.DateLabelSize = 25;
	weekLabelSettings.DateFormat = "dd ";
	weekLabelSettings.DayFormat = "EEEE";
	weekLabelSettings.TimeFormat = "hh:mm a ";
	weekViewSettings.WeekLabelSettings = weekLabelSettings;
	schedule.WeekViewSettings = weekViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

#### Working Hours

You can differentiate working hours with non-working hour timeslots by its color using `WorkStartHour` and `WorkEndHour` properties of `WeekViewSettings`.

You can also differentiate working hours with non-working hour timeslots by its color using `NonWorkingHoursTimeSlotBorderColor`, `NonWorkingHoursTimeSlotColor`, `TimeSlotColor`,`TimeSlotBorderColor` and `TimeSlotBorderStrokeWidth` properties of `WeekViewSettings`.To know more about customization of working hours refer [Timeslots Customization](/xamarin-android/sfschedule/appearance-and-styling "Timeslots Customization")

{% highlight c# %}

	//creating new instance for schedule
	schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.WeekView;

	//setting week view settings properties
	WeekViewSettings weekViewSettings = new WeekViewSettings ();
	weekViewSettings.WorkStartHour = 10;
	weekViewSettings.WorkEndHour = 18;
	schedule.WeekViewSettings = weekViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

#### All Day Appointments Panel

You can view All day appointments in separate panel and the panels visibility can be enabled by setting `ShowAllDay` property of `WeekViewSettings` as true. Also you can change the all day appointment panel color using the property `AllDayAppointmentBackgroundColor`.To know more about customization of working hours refer [Timeslots Customization](/xamarin-android/sfschedule/appearance-and-styling "Timeslots Customization")

{% highlight c# %}

	//creating new instance for schedule
	schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.WeekView;

	//setting week view settings properties
	WeekViewSettings weekViewSettings = new WeekViewSettings();
	weekViewSettings.ShowAllDay = true;

	schedule.WeekViewSettings = weekViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

![](Views_images/WeekView.png)

## Work Week View

To view working days of a particular week, by default current work week will be displayed. Saturday and Sunday are the non-working days by default; it can be customized with any days in a week. Appointments arranged in timeslots based on its duration with respective day of the week.

{% highlight c# %}

	//creating new instance for schedule
	schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.WorkWeekView;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

### Settings

#### Date Time Formating

You can format the date and time string in the schedule control using `WorkWeekLabelSettings` of  `WorkWeekViewSettings` and the size of those strings are also customizable.Also you can differentiate the timeslot panel using `VerticalLineColor` and `VerticalLineStrokeWidth` properties of `WorkWeekViewSettings`.To know more about customization of working hours refer [Timeslots Customization](/xamarin/sfschedule/appearance-and-styling "Timeslots Customization")

{% highlight c# %}

	//creating new instance for schedule
	schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.WorkWeekView;
	//setting label size and formats
	WorkWeekLabelSettings workWeekLabelSettings = new WorkWeekLabelSettings();
	workWeekLabelSettings.TimeLabelSize = 14;
	workWeekLabelSettings.DateLabelSize = 25;
	workWeekLabelSettings.DateFormat = "dd ";
	workWeekLabelSettings.DayFormat = "EEEE";
	workWeekLabelSettings.TimeFormat = "hh:mm a ";
	workWeekViewSettings.WorkWeekLabelSettings = workWeekLabelSettings;

	schedule.WorkWeekViewSettings = workWeekViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

#### Working Hours

You can differentiate working hours with non-working hour timeslots by its color using `WorkStartHour` and `WorkEndHour`  properties of `WorkWeekViewSettings`.

You can also differentiate working hours with non-working hour timeslots by its color using `NonWorkingHoursTimeSlotBorderColor`, `NonWorkingHoursTimeSlotColor`, `TimeSlotColor`,`TimeSlotBorderColor` and `TimeSlotBorderStrokeWidth` properties of `WorkWeekViewSettings`.To know more about customization of working hours refer [Timeslots Customization](/xamarin/sfschedule/appearance-and-styling "Timeslots Customization")

{% highlight c# %}

	//creating new instance for schedule
	schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.WorkWeekView;

	//setting workweek view settings properties
	WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings ();	
	workWeekViewSettings.WorkStartHour = 10;
	workWeekViewSettings.WorkEndHour = 18;
	schedule.WorkWeekViewSettings = workWeekViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

#### All Day Appointments Color

You can view All day appointments in separate panel and the panels visibility can be enabled by setting `ShowAllDay` property of `WorkWeekViewSettings` as true. Also you can change the all day appointment panel color using the property `AllDayAppointmentBackgroundColor`.To know more about customization of All day appointment panel refer [Timeslots Customization](/xamarin-android/sfschedule/appearance-and-styling "Timeslots Customization")

{% highlight c# %}

	//creating new instance for schedule
	schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.WorkWeekView;

	//setting workweek view settings properties
	WorkWeekViewSettings workWeekViewSettings = new WorkWeekViewSettings();
	workWeekViewSettings.ShowAllDay = true;
	schedule.WorkWeekViewSettings = workWeekViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

#### Non-Working Days

You can view the working days alone by restricting the non working days using `NonWorkingDays` property in `Schedule`.

![](Views_images/WorkWeekView.png)

## Month View

To view entire dates of a particular month, by default current month will be displayed initially. Appointments arranged within the cell based on its duration. Current date is differentiated by some color and rest of the dates in a month will be in different color., Also the color differentiation for dates will be applicable for previous and next month dates.

{% highlight c# %}

	//creating new instance for schedule
	schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.MonthView;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

### Inline

#### Show Appointments Inline 

By enabling Inline feature in month view, while touch the month view cell, appointments available in a particular day will be listed in inline view. 

{% highlight c# %}

	SfSchedule schedule = new SfSchedule(this);
	schedule.ScheduleView = ScheduleView.WeekView;

	//setting Show inline 
	schedule.MonthViewSettings.ShowAppointmentsInline = true;

{% endhighlight %}

#### Inline View Customization

By enabling the Inline view feature, while tap on the schedule month view cell it will open a inline view which can be customized accordingly. To know more about Inline view customization of Month cell refer [View Customization](/xamarin-android/sfschedule/view-customization "View Customization").

#### Inline Appointment Customization

By enabling the Inline view feature, while tap on the schedule month view cell it will open a inline view which contains list of appointments on a particular day.You can customize the inline appointments. To know more about Inline appointment customization of Month cell refer [View Customization](/xamarin-android/sfschedule/view-customization "View Customization").

#### InlineAppointmentTapped Event

You can able to know the details of appointments in inline using `InlineAppointmentTapped` event in `Schedule`. Details of the selected  appointment and the corresponding date is passed through `InlineAppointmentTappedEventArgs` as `selectedAppointment` and `selectedDate` respectively.

{% highlight C# %}

	monthViewSettings.InlineAppointmentTappedEvent += (object sender, MonthViewSettings.InlineAppointmentTappedEventArgs e) =>
	{
	var appointment = e.P2;
	var date = e.P1;
	};

{% endhighlight %}

### Month Navigation Direction

`MonthView` of Schedule can be navigated horizontally and vertically.You can change the direction of navigation through `MonthNavigationDirection` property of `MonthViewSettings`.By default MonthNavigation value is `Horizontal`

{% highlight C# %}

	MonthViewSettings monthViewSettings = new MonthViewSettings();
	//To navigate vertically
	monthViewSettings.MonthNavigationDirection =  MonthNavigationDirections.Vertical;
	schedule.MonthViewSettings = monthViewSettings;

{% endhighlight %}

### Settings

#### Date Time Formating

You can format the date and time string in the schedule control using `MonthLabelSettings` of  `MonthViewSettings`.

{% highlight c# %}

	//creating new instance for schedule
	schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.MonthView;

	//setting month view settings properties
	MonthViewSettings monthViewSettings = new MonthViewSettings();

	//setting label size and formats
	MonthLabelSettings monthLabelSettings = new MonthLabelSettings();
	monthLabelSettings.DayLabelSize=10;
	monthLabelSettings.DayFormat="E";
	monthLabelSettings.DateLabelSize=26;
	monthLabelSettings.DateFormat="dd";
	monthViewSettings.MonthLabelSettings = monthLabelSettings;
	schedule.MonthViewSettings = monthViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

#### Week number

You display the week number of the year in month view by setting `ShowWeekNumber` in property of `MonthViewSettings` are true. By default it is false.

{% highlight c# %}

	//creating new instance for schedule
	schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.MonthView;

	//setting month view settings properties
	MonthViewSettings monthViewSettings = new MonthViewSettings();
	monthViewSettings.ShowWeekNumber=true;
	schedule.MonthViewSettings = monthViewSettings;

	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

#### Visible AppointmentCount

You can customize the number of appointments to be rendered inside a month view cell using `VisibleCellAppointmentsCount` property of `MonthViewSettings`

{% highlight c# %}

	//creating new instance for schedule
	schedule = new SfSchedule(this);

	//setting schedule view
	schedule.ScheduleView = ScheduleView.MonthView;

	//setting month view settings properties
	MonthViewSettings monthViewSettings = new MonthViewSettings();
	monthViewSettings.VisibleCellAppointmentsCount = 10;
	schedule.MonthViewSettings = monthViewSettings;
	
	// Set our view from the "main" layout resource
	SetContentView(schedule);

{% endhighlight %}

### Month cell customization

You can customize the month cells of MonthView using various properties of `MonthCellStyle`. To know more about customization of MonthView refer [View Customization](/xamarin-android/sfschedule/view-customization "View Customization")

![](Views_images/MonthView.png)
