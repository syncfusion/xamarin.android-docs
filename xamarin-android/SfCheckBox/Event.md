---
layout: post
title: Event | SfCheckBox | Syncfusion | Xamarin.Android
description: Learn how to get the notification of StateChanged event in Xamarin.Android CheckBox(SfCheckBox) control 
platform: Xamarin.Android
control: SfCheckBox
documentation: ug 
keywords: button, SfCheckBox, CheckBox

---

# Event in Xamarin.Android Chart(SfChart)

## StateChanged event
Occurs when the value(state) of the [`Checked`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html#Syncfusion_Android_Buttons_SfCheckBox_Checked) property is changed by either touching the check box or setting the value to the [`Checked`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html#Syncfusion_Android_Buttons_SfCheckBox_Checked) property using C# code. The event arguments are of type [`StateChangedEventArgs`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.StateChangedEventArgs.html) and expose the following property:

* [`IsChecked`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.StateChangedEventArgs.html#Syncfusion_Android_Buttons_StateChangedEventArgs_IsChecked): The new value(state) of the [`Checked`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html#Syncfusion_Android_Buttons_SfCheckBox_Checked) property.

{% tabs %}
{% highlight c# %}
checkBox = new SfCheckBox(this);
checkBox.Text = "Unchecked State";
checkBox.IsThreeState = true;
checkBox.StateChanged += CheckBox_StateChanged;

private void CheckBox_StateChanged(object sender, StateChangedEventArgs e)
{
    if (e.IsChecked.HasValue && e.IsChecked.Value)
    {
        checkBox.Text = "Checked State";
    }
    else if(e.IsChecked.HasValue && !e.IsChecked.Value)
    {
        checkBox.Text = "Unchecked State";
    }
    else
    {
        checkBox.Text = "Indeterminate State";
    }
}
		
{% endhighlight %}
{% endtabs %}

![CheckBox Unchecked State](Images/Unchecked_State.png)
![CheckBox Checked State](Images/Checked_State.png)
![CheckBox Indeterminate State](Images/Indeterminate_State.png)
