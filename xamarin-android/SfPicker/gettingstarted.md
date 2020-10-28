---
layout: post
title: Getting Started of Syncfusion Picker control for Xamarin.Android
description: This section will explain about how to create Picker control using SfPicker in Xamarin.Android platform .
platform: Xamarin.Android
control: Picker
documentation: ug
---


# Getting Started with SfPicker

This section explains you the steps to configure a SfPicker control in a real-time scenario and provides a walk-through on some of the customization features available in SfPicker control.

## Adding SfPicker reference

Refer this [article](https://help.syncfusion.com/xamarin/introduction/download-and-installation# "") to know how to obtain and reference Essential Studio components in your solution; then refer [this](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfpicker "") link to know about the assemblies required for adding SfPicker to your project.

## Initialize SfPicker on Android

To use SfPicker in Xamarin application. Android platform project must initialize the SfPicker renderer.

### Android

The Android launches the SfPicker without any initialization and is enough to only initialize the Com.Syncfusion.SfPicker to launch the application.

### Create a simple SfPicker

This section explains how to create simple SfPicker control and configure it. SfPicker can configure using C# code. 

### Create the Xamarin.Android project 

Create new blank project (Xamarin.Android ) using Visual Studio or Xamarin Studio for Xamarin.Android. 

### Adding SfPicker in Xamarin.Android project

1. Add the required assembly reference in Android and other renderer projects as discussed in **Adding** **SfPicker** **reference** section.
2. Add SfPicker control C#.
* C# Page
  * Import SfPicker control namespace as `using Com.Syncfusion.SfPicker;` in C# ContentPage.
  * Create new SfPicker instance in ContentPage constructor and assign SfPicker instance to ContentPage Content property.

{% tabs %}

{% highlight c# %}

    using System;

    using System.Collections;

    using Android.App;

    using Android.Content;

    using Android.Runtime;

    using Android.Views;

    using Android.Widget;

    using Android.OS;

    using Com.Syncfusion.SfPicker;

    using Android.Graphics;

    using System.Collections.Generic;

    using System.ComponentModel;

    using System.Collections.ObjectModel;

    using Java.Util;


    namespace GettingStarted.Droid

    {

	    [Activity (Label = "GettingStarted.Android", MainLauncher = true, Icon = "@drawable/icon")]
	    public class MainActivity : Activity
	    {
            SfPicker picker;
            
            protected override void OnCreate(Bundle savedInstanceState)
            {
            picker = new SfPicker(this);
            base.OnCreate(savedInstanceState);
            SetContentView(picker);
            }
        } 
    }

{% endhighlight %}

{% endtabs %}

### Set Header to the SfPicker

SfPicker allows you to define header text by setting the `SfPicker.HeaderText` and enable SfPicker header by setting `SfPicker.ShowHeader` property to true. Default value of `SfPicker.ShowHeader` is True.

{% tabs %}


{% highlight c# %}

	public class MainActivity : Activity
	{
        protected override void OnCreate(Bundle savedInstanceState)
        {
            SfPicker picker = new SfPicker(this);
            base.OnCreate(savedInstanceState);
            picker.HeaderText = "Select a Color";
            SetContentView(picker);
        }
    } 

{% endhighlight %}

{% endtabs %}

### Adding SfPicker Items 

SfPicker control is a data bounded control. Hence you must create collection of data’s and bind it to SfPicker control.

* Create simple Observable Collection with string type of Data’s for the SfPicker 

{% highlight c# %}

    public class ColorInfo

        {

        private ObservableCollection<string> _color;

        public ObservableCollection<string> Colors

            {

                get { return _color; }

                set { _color = value; }

            }

        public ColorInfo()

            {

                Colors = new ObservableCollection<string>();

                Colors.Add("Red");

                Colors.Add("White");

                Colors.Add("Orange");

                Colors.Add("Blue");

                Colors.Add("Purple");

                Colors.Add("Pink");

                Colors.Add("SkyBlue");

                Colors.Add("Yellow");

            }

        }

{% endhighlight %}

* Binding the Collection to SfPicker

SfPicker allow you to bind collection of data’s by setting `SfPicker.ItemsSource` property. You can bind the collection of data’s in C#.

{% tabs %}

{% highlight c# %}

    protected override void OnCreate(Bundle savedInstanceState)

        {
            SfPicker picker = new SfPicker(this);
            base.OnCreate(savedInstanceState);
            ColorInfo info = new ColorInfo();
            picker.ItemsSource = info.Colors;
            SetContentView(picker);
        }
{% endhighlight %}

{% endtabs %}

### Set title to the Items 

SfPicker allows you to define title to the SfPicker items by setting `SfPicker.ColumnHeaderText` and enable title of the SfPicker items by setting `SfPicker.ShowColumnHeader` property to True. Default value of `SfPicker.ShowColumnHeader` is False.

{% tabs %}

{% highlight c# %}

    protected override void OnCreate(Bundle savedInstanceState)

        {
            SfPicker picker = new SfPicker(this);
            base.OnCreate(savedInstanceState);
            picker.ColumnHeaderText = "Color";
            picker.ShowColumnHeader = true;
            SetContentView(picker);
        }
{% endhighlight %}

{% endtabs %}

### Enable Validation button in Footer

In SfPicker validation button (Ok and Cancel) can be enabled by setting `SfPicker.ShowFooter` property to True. Default value of `SfPicker.ShowFooter` property is False

{% tabs %}

{% highlight c# %}  

    protected override void OnCreate(Bundle savedInstanceState)

        {
            SfPicker picker = new SfPicker(this);
            base.OnCreate(savedInstanceState);
            picker.ShowFooter = true;
            SetContentView(picker);
        }
{% endhighlight %}

{% endtabs %}

### Open as Dialog

In SfPickerSfPicker can be rendered as a dialog by setting `SfPicker.PickerMode` property to Dialog. Default value of `SfPicker.PickerMode` property is Default. 

{% tabs %}

{% highlight c# %}


    protected override void OnCreate(Bundle savedInstanceState)

        {
            SfPicker picker = new SfPicker(this);
            base.OnCreate(savedInstanceState);
            picker.PickerMode = PickerMode.Dialog;
            SetContentView(picker);
        }
{% endhighlight %}

{% endtabs %}

The picker can be opened programmatically by setting by setting `SfPicker.IsOpen` property to True. Default value of `SfPicker.IsOpen` is False.

Note: This property automatically changed to False when close the dialog by click outside of dialog SfPicker.

{% tabs %}
{% highlight c# %}

    protected override void OnCreate(Bundle savedInstanceState)

        {
            SfPicker picker = new SfPicker(this);
            base.OnCreate(savedInstanceState);
            picker.IsOpen = true;
            SetContentView(picker);
        }

{% endhighlight %}

{% endtabs %}

Screen shot for the above code

![Picker mode dailog in Xamarin.Android SfPicker](images/android_picker.png)

We have attached sample for reference. please download the sample from the below link.

Sample link:[GettingStarted](http://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStarted-946810959.zip)