---
layout: post
title: Visual customization | SfCheckBox | Syncfusion | Xamarin.Android
description: Learn how to customize the SfCheckBox CornerRadius, CheckedColor, UncheckedColor, BorderWidth, and Text.
platform: Xamarin.Android
control: SfCheckBox
documentation: ug 
keywords: button, SfCheckBox, CheckBox

---

# Visual Customization

## Customizing shape
The check box shape can be customized using the [`CornerRadius`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html#Syncfusion_Android_Buttons_SfCheckBox_CornerRadius) property. This property specifies uniform radius value for every corner of the check box.

{% tabs %}
{% highlight c# %}
SfCheckBox checkBox = new SfCheckBox(this);
checkBox.Text = "CheckBox";
checkBox.Checked = true;
checkBox.CornerRadius = 5.0f;
{% endhighlight %}
{% endtabs %}

![CheckBox CornerRadius](Images/Radius.png)

## Customizing state color
The default state colors can be customized using the [`ButtonTintList`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html) property. The checked/unchecked/indeterminate state color is updated with `ColorStateList` to the [`ButtonTintList`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html).
{% tabs %}
{% highlight c# %}
int[][] states ={new int[]{ Android.Resource.Attribute.StateChecked },                            
                new int[]{Syncfusion.Buttons.Android.Resource.Attribute.state_indeterminate},
		new int[]{-Android.Resource.Attribute.StateChecked }};
int[] colors = { Color.Green,  Color.Purple, Color.Violet};

SfCheckBox check = new SfCheckBox(this);
check.Text = "CheckBox";
check.Checked = true;            
check.ButtonTintList = new ColorStateList(states, colors);
SfCheckBox uncheck = new SfCheckBox(this);
uncheck.Text = "CheckBox";            
uncheck.ButtonTintList = new ColorStateList(states, colors);
SfCheckBox indeterminate = new SfCheckBox(this);
indeterminate.Checked = null;
indeterminate.IsThreeState = true;
indeterminate.Text = "CheckBox";
indeterminate.ButtonTintList = new ColorStateList(states, colors);
{% endhighlight %}
{% endtabs %}

![CheckedColor and UncheckedColor in Checkbox](Images/StateColor.png)

## BorderWidth
The border thickness of the tick box in the checkbox can be customized with the [`BorderWidth`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html#Syncfusion_Android_Buttons_SfCheckBox_BorderWidth) property.

{% tabs %}
{% highlight c# %}
//unchecked state and its color
int[][] states = { new int[] { -Android.Resource.Attribute.StateChecked } };
int[] colors = { Color.Blue};

SfCheckBox normalSizedCheckBox = new SfCheckBox(this)
{
Text = "Hello",
BorderWidth = 2,
TextSize = 20,
ButtonTintList = new Android.Content.Res.ColorStateList(states,colors)
};

SfCheckBox mediumSizedCheckBox = new SfCheckBox(this)
{
Text = "Hello",
BorderWidth = 4,
TextSize = 25,
ButtonTintList = new Android.Content.Res.ColorStateList(states, colors)
};

SfCheckBox maximumSizedCheckBox = new SfCheckBox(this)
{
Text = "Hello",
BorderWidth = 6,
TextSize = 30,
ButtonTintList = new Android.Content.Res.ColorStateList(states, colors)
};

{% endhighlight %}
{% endtabs %}

![CheckBox BorderWidth](Images/BorderWidth.png)

## Setting caption text appearance 
You can customize the display text appearance of the [`SfCheckBox`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html) control using the following properties:

* [`SetTextColor`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html): Changes the color of the text.
* [`TextAlignment`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html): Changes the horizontal alignment of the caption text.
* [`Typeface`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html): Changes the font family of the text and sets font attributes(bold/italic/none) of the caption text.
* [`TextSize`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.Buttons.SfCheckBox.html): Sets font size of the caption text.

{% tabs %}
{% highlight c# %}
SfCheckBox caption = new SfCheckBox(this);
caption.Checked = true;
caption.Text = "CheckBox";
caption.SetTextColor(Color.Violet);
caption.TextAlignment = TextAlignment.Center;
caption.Typeface = Typeface.Create("Arial", TypefaceStyle.Bold);
caption.TextSize = 20;
{% endhighlight %}
{% endtabs %}

![CheckBox TextAppearance](Images/CaptionAppearance.png)
