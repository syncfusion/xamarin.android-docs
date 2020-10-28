---
layout: post
title: Right-to-left | Schedule for Xamarin.Android | Syncfusion
description: Describes how to enable right-to-left localization schedule.
platform: Xamarin.Android
control: SfSchedule
documentation: ug
---

# Right to left(RTL)
Schedule supports to change the layout direction of the control in the `RightToLeft` direction by setting the [LayoutDirection](https://developer.xamarin.com/api/type/Android.Views.LayoutDirection/) to `Rtl`.  Schedule also supports right-to-left when device layout direction and device language is changed.

{% tabs %}
{% highlight c# %}
schedule.LayoutDirection = LayoutDirection.Rtl;
{% endhighlight %}
{% endtabs %}

>**Note**
Add `android:supportsRtl="true"` to your application tag in your `AndroidManifest.xml` file, and make sure your `MinSDKVersion` is 17+. For android settings you can refer [here](https://docs.microsoft.com/en-us/xamarin/android/app-fundamentals/localization#right-to-left-rtl-languages).

{% tabs %}
{% highlight xml %}
<manifest ... >
<uses-sdk android:minSdkVersion="17" />
<application ... android:supportsRtl="true">
</application>
</manifest>
{% endhighlight %}
{% endtabs %}

