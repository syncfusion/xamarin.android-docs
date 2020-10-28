---
layout: post
title: Getting Started with Syncfusion MaskedEdit control for Xamarin.Android
description: A quick tour to initial users on Syncfusion SfMaskedEdit control for Xamarin.Android platform 
platform: Xamarin.Android
control: SfMaskedEdit
documentation: ug
---


# Getting Started
This section explains you the steps required to configure a SfMaskedEdit control in a real-time scenario and provides a walk-through on some of the customization features available in `SfMaskedEdit` control.

##  Reference Essential Studio components in your solution

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add masked edit to your project, open the NuGet package manager in Visual Studio, and search for "[syncfusion.xamarin.sfmaskededit.android](https://www.nuget.org/packages/Syncfusion.Xamarin.SfMaskedEdit.Android)", and then install it. 

![Xamarin.Android masked edit nuget](SfMaskedEditImages/nuget.png) 

## Create a Simple SfMaskedEdit

The SfMaskedEdit control is configured entirely in C# code. The following steps explain how to create a SfMaskedEdit and configure its elements:

### Add namespace for referred assemblies

{% tabs %}
{% highlight c# %}
using Syncfusion.Android.MaskedEdit;
{% endhighlight %}
{% endtabs %}
  
N> Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion license key in your Xamarin application to use our components.
 
### Create a sample with simple SfMaskedEdit

{% tabs %}
{% highlight c# %}
using Android.App;
using Android.Widget;
using Android.OS;
using Syncfusion.Android.MaskedEdit;

namespace MaskEdit
{
    [Activity(Label = "MaskEdit", MainLauncher = true, Icon = "@mipmap/icon")]
    public class MainActivity : Activity
    {
        int count = 1;

        protected override void OnCreate(Bundle savedInstanceState)
        {
            base.OnCreate(savedInstanceState);

            // Set our view from the "main" layout resource
            SetContentView(Resource.Layout.Main);
            LinearLayout linearLayout = FindViewById<LinearLayout>(Resource.Id.layout);
            SfMaskedEdit maskedEdit = new SfMaskedEdit(this);
            linearLayout.AddView(maskedEdit);
        }
    }
}
{% endhighlight %}
{% endtabs %}

## Masking the input

To mask the input, set the Mask properties as follows:

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit(this);
maskedEdit.Mask = "00/00/0000";
{% endhighlight %}
{% endtabs %}

This mask expression allows only numeric inputs in the places of 0.

Refer to this [link](MaskType) to know more about the Mask characters and Mask Types available in SfMaskedEdit control.

Run the project and check if you get the following output to make sure that you have configured your project properly to add `SfMaskedEdit`.

![Xamarin.Android masked edit](SfMaskedEditImages/GettingStarted.png)

You can find the complete getting started sample from this [link](http://files2.syncfusion.com/Xamarin.Android/Samples/MaskedEdit_GettingStarted.zip).
