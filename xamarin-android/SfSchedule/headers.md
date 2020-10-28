---     
layout: post     
title: Header appearance and customization in Syncfusion SfSchedule control for Xamarin.Android     
description: Learn how to customize header in SfSchedule control    
platform: xamarin.Android    
control: SfSchedule     
documentation: ug
---  

# Header

You can customize the header of the Schedule using [HeaderStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_HeaderStyle) and [HeaderHeight](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_HeaderHeight) property in schedule.

## Header Height

You can customize the height for the Header in Schedule using `HeaderHeight` in schedule.

{% tabs %}
{% highlight c# %}
schedule.HeaderHeight = 50;
{% endhighlight %}
{% endtabs %}

## Appearance

You can change the header format and style using `HeaderStyle` property in schedule.

You can change the background color,text style and text size using properties such as [BackgroundColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.HeaderStyle.html#Com_Syncfusion_Schedule_HeaderStyle_BackgroundColor),[TextStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.HeaderStyle.html#Com_Syncfusion_Schedule_HeaderStyle_TextStyle), [TextSize](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.HeaderStyle.html#Com_Syncfusion_Schedule_HeaderStyle_TextSize),[TextColor](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.HeaderStyle.html#Com_Syncfusion_Schedule_HeaderStyle_TextColor) of Header using `HeaderStyle` property in schedule.

{% tabs %}
{% highlight c# %}
HeaderStyle headerStyle = new HeaderStyle();
headerStyle.BackgroundColor = Color.FromRgb(250, 219, 216);
headerStyle.TextStyle = Font.Default;
headerStyle.TextSize = 15;
headerStyle.TextColor=Color.White;
schedule.HeaderStyle = headerStyle;
{% endhighlight %}
{% endtabs %}

![](Header_images/HeaderStyle.png) 

### Customize Font Appearance

You can change the appearance of Font by setting the [TextStyle](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.HeaderStyle.html#Com_Syncfusion_Schedule_HeaderStyle_TextStyle) property of [HeaderStyle](https://help.syncfusion.com/xamarin-android/sfschedule/headers#appearance) property in Schedule.
{% tabs %}
{% highlight c# %}
headerStyle.TextStyle = Typeface.CreateFromAsset(Assets, "Lobster-Regular.ttf");
{% endhighlight %}
{% endtabs %}

![](Header_images/customfontheader.png)

Refer [this](https://help.syncfusion.com/xamarin-android/sfschedule/monthview#custom-font-setting-in-xamarinandroid) to configure the custom fonts in Xamarin.Android.

## Loading Custom Headers

You can collapse the default header of schedule by setting `HeaderHeight` property of `SfSchedule` as 0. Instead you can use your own custom header for it. While navigating views in schedule, text labels available in the header will be changed based on it visible dates, so while using custom header, respective text value can be obtained from the `VisibleDatesChanged` event of `SfSchedule`.

{% tabs %}
{% highlight c# %}
//triggering visible dates changed event.
schedule.VisibleDatesChanged += Schedule_VisibleDatesChanged;

IList<Calendar> visibleDates;
void Schedule_VisibleDatesChanged(object sender, VisibleDatesChangedEventArgs e)
{
	visibleDates = e.VisibleDates;
	var headerString = string.Empty;
	SimpleDateFormat dateFormat = new SimpleDateFormat("MMMM, yyyy", Locale.Us);
	if (schedule.ScheduleView == ScheduleView.DayView)
	{
		headerString = dateFormat.Format(visibleDates[0].Time);
	}
	else 
	{
		headerString = dateFormat.Format(visibleDates[visibleDates.Count / 2].Time);
	}
}
{% endhighlight %}
{% endtabs %}

You can get the complete sample for customizing the Header of Schedule [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Header_Android_Sample-935057749.zip)

## Header Date Format

You can customize the date format of SfSchedule Header by using [ScheduleDateHeaderFormat](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_ScheduleDateHeaderFormat) property of `SfSchedule`.

{% tabs %}
{% highlight c# %}
//Creating instance of Schedule
SfSchedule schedule = new SfSchedule();
//Customizing date format
schedule.ScheduleDateHeaderFormat = "LLL yy";
{% endhighlight %}
{% endtabs %}

![](Header_images/HeaderDateFormat.png)

## Header Tapped Event

You can handle single tap action of Header by using [HeaderTapped](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html) event of `SfSchedule`. This event will be triggered when the Header is Tapped. This event contains [HeaderTappedEventArgs](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.HeaderTappedEventArgs.html) argument which holds [Calendar](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.HeaderTappedEventArgs.html#Com_Syncfusion_Schedule_HeaderTappedEventArgs_Calendar) details in it.

{% tabs %}
{% highlight c# %}
//Creating  new instance of Schedule
SfSchedule schedule = new SfSchedule();
schedule.HeaderTapped += Handle_HeaderTapped;

...

void Handle_HeaderTapped(object sender, HeaderTappedEventArgs e)
{
    var calendar = e.Calendar;
}
{% endhighlight %}
{% endtabs %}
