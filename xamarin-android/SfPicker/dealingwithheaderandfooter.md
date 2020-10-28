---
layout: post
title: Dealing with Header and Footer of Syncfusion Picker control for Xamarin.Android
description: Dealing with Header and Footer of Picker control
platform: Xamarin
control: Picker
documentation: ug
---

# Dealing with Header and Footer

This section explains about the header and footer customization of SfPicker.

## Enable or Disable Header 

SfPicker allows enabling or disabling the header section by setting `SfPicker.ShowHeader` property to True or False. Default value of `SfPicker.ShowHeader` property is True.

{% tabs %}

{% highlight c# %}
 
     protected override void OnCreate(Bundle savedInstanceState)
 
        {
            base.OnCreate(savedInstanceState);
            SfPicker picker = new SfPicker(this);
            picker.ShowHeader = false;
            SetContentView(picker);
        }
{% endhighlight %}
{% endtabs %}

## Set Custom Header 

SfPicker allows providing custom text to Header of SfPicker by setting `SfPicker.HeaderText` property. Default value of `SfPicker.HeaderText` property is Null.

{% tabs %}

{% highlight c# %}
 
    protected override void OnCreate(Bundle savedInstanceState)
 
        {
            base.OnCreate(savedInstanceState);
            SfPicker picker = new SfPicker(this);
            picker.HeaderText = "Select a Date";
            SetContentView(picker);
        }
{% endhighlight %}
{% endtabs %}

## Header Customization

SfPicker allows customizing Background, TextColor and Fonts.

### Background

Header background color can be customized  by setting `SfPicker.HeaderBackgroundColor` property of SfPicker.

{% tabs %}

{% highlight c# %}

    protected override void OnCreate(Bundle savedInstanceState)
 
        {
            base.OnCreate(savedInstanceState);
            SfPicker picker = new SfPicker(this);
            picker.HeaderBackgroundColor = Color.Green;
            SetContentView(picker);
        }
{% endhighlight %}
{% endtabs %}

### Text Color 

Header text color can be customized by setting `SfPicker.HeaderTextColor` property of SfPicker.

{% tabs %}

{% highlight c# %}

    protected override void OnCreate(Bundle savedInstanceState)
 
        {
            base.OnCreate(savedInstanceState);
            SfPicker picker = new SfPicker(this);
            picker.HeaderTextColor = Color.Red; 
            SetContentView(picker);
        }
{% endhighlight %}
{% endtabs %}

### Font 

This section explains about the customization of Header text of Font.

#### 	FontFamily

Header text FontFamily can be customized by setting `SfPicker.HeaderTypeFace` property of SfPicker.

{% tabs %}

{% highlight c# %}

    protected override void OnCreate(Bundle savedInstanceState)
 
        {
            base.OnCreate(savedInstanceState);
            SfPicker picker = new SfPicker(this);
            picker.HeaderTypeface = Typeface.Create("sans-serif", TypefaceStyle.Bold);
            SetContentView(picker);
        }
{% endhighlight %}

{% endtabs %}

#### 	FontSize

Header text FontSize can be customized by setting `SfPicker.HeaderTextSize` property of SfPicker.

{% tabs %}

{% highlight c# %}

    protected override void OnCreate(Bundle savedInstanceState)
 
        {
            base.OnCreate(savedInstanceState);
            SfPicker picker = new SfPicker(this);
            picker.HeaderTextSize = 18;
             SetContentView(picker);
        }
{% endhighlight %}

{% endtabs %}   

#### 	FontAttribute

Header text FontAttribute can be customized by setting `SfPicker.HeaderTypeFace` property of SfPicker.

{% tabs %}

{% highlight c# %}

    protected override void OnCreate(Bundle savedInstanceState)
 
        {
            base.OnCreate(savedInstanceState);
            SfPicker picker = new SfPicker(this);
            picker.HeaderTypeface = Typeface.Create("sans-serif", TypefaceStyle.Bold);
            SetContentView(picker);
        }
{% endhighlight %}

{% endtabs %}

## Enable or Disable Footer 

SfPicker allows enabling or disabling the footer section by setting `SfPicker.ShowFooter` property to True or False. Default value of `SfPicker.ShowFooter` property is False.

{% tabs %}


{% highlight c# %}

    protected override void OnCreate(Bundle savedInstanceState)
 
        {
            base.OnCreate(savedInstanceState);
            SfPicker picker = new SfPicker(this);
            picker.ShowFooter = true;
            SetContentView(picker);
        }
{% endhighlight %}

{% endtabs %}

## Set Custom Footer

SfPicker allows providing custom view to Footer of SfPicker by setting `SfPicker.FooterView` property. Default value of `SfPicker.FooterView` property is Null.

{% tabs %}

{% highlight c# %}

    protected override void OnCreate(Bundle savedInstanceState)
 
        {
            base.OnCreate(savedInstanceState);
            
            SfPicker picker = new SfPicker(this);
            
            LinearLayout linearLayout = new LinearLayout(this);
            
            Button button = new Button(this);
            
            button.Text = "Button";
            
            linearLayout.AddView(button);
            
            picker.FooterView = linearLayout;
            
            picker.ShowFooter = true;
            
            SetContentView(picker);
        }

{% endhighlight %}

{% endtabs %}

## Perform validation with default validation Button

SfPicker allows performing validation based on OK or Cancel button by hooking `SfPicker.OkButtonClicked` and `SfPicker.CancelButtonClicked`. In this event from the `SelectionChangedEvent` Argument current selected items can be obtained.


{% tabs %}

{% highlight c# %}
  
    protected override void OnCreate(Bundle savedInstanceState)
 
        {
            base.OnCreate(savedInstanceState);
            SfPicker picker = new SfPicker(this);
            picker.CancelButtonClicked += Picker_CancelButtonClicked;
            picker.OkButtonClicked += Picker_OkButtonClicked;
            SetContentView(picker);
        }
{% endhighlight %}

{% endtabs %}
