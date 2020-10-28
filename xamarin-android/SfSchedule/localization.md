---
layout: post
title: Localization of Syncfusion Schedule in Xamairn.Android
description: How to Localize the contents of Schedule control in Xamarin.Android.
platform: Xamarin.Android
control: SfSchedule
documentation: ug
---

# Localization 

Schedule control is available with complete localization support. Localization can be specified by setting the [Locale](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Schedule.SfSchedule.html#Com_Syncfusion_Schedule_SfSchedule_Locale) property of SfSchedule. In the format of `Language code`.

## Change default control language

Based on the `Locale` specified the strings in the control such as Date, time, days are localized accordingly.

By default, schedule control is available with en locale, which is English.

{% tabs %}
{% highlight c# %}
//creating new instance for schedule
SfSchedule schedule = new SfSchedule(this);
//setting schedule view
schedule.ScheduleView = ScheduleView.WeekView;
//setting locale for the control
schedule.Locale = new Locale("ja");
{% endhighlight %}
{% endtabs %}
   

![Localization support for schedule in Xamairn.Android](Localization_images/Localization_Android.png)   

## Change custom texts in the control.

You can localize the custom strings used in the schedule control. You can localize custom text available in the control by adding equivalent localized string in the string.xml file.

{% tabs %}
{% highlight xml %}
<resources>
	<string name="No_Appointments">Aucun événement</string>
	<string name="all_day">Toute la journée</string>
</resources>
{% endhighlight %}
{% endtabs %}

Android can select and load resources from different directories, based on the device configuration and locale, refer [here](https://developer.xamarin.com/guides/android/advanced_topics/localization/). For an example, if an application requires multiple languages you can follow the below steps.

The procedure for creating strings.xml files is as follows:

*	Translate the strings.xml file to each language.
*	Create new folders under resource as values-`ar`, values-`de`, values-`en` and values-`fr` (The original values folder already exists).
*	Place the translated strings.xml files in the respective folders.

You can download the entire source code of this demo for Xamarin.Android from
here [Localization](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Localization_Android-352507966.zip).

![Localization foldren structure for schedule in Xamairn.Android](Localization_images/localization_img2.jpeg)

>**NOTE**
The corresponding values folder loads only depends on the device configuration and locale.
