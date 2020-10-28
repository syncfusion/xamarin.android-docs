---
layout: post
title: Getting Started | SfPopupLayout |Xamarin.Android | Syncfusion
description: Getting Started with SfPopupLayout
platform: Xamarin.Android
control: SfPopupLayout
documentation: ug
--- 

# Getting Started

This section provides a quick overview for working with the SfPopupLayout in Xamarin.Android. Walk through the entire process of creating a simple application with this control.

## Assembly deployment

After installing Essential Studio for Xamarin, all the required assemblies can be found in the {Syncfusion Essential Studio Installed location}\Essential Studio\16.1.0.24\Xamarin\lib installation folders. 

E.g. C:\Program Files (x86)\Syncfusion\Essential Studio\16.1.0.24\Xamarin\lib

N> Assemblies can be found in an unzipped package location in Mac.

## NuGet configuration

To install the required NuGet for the SfPopupLayout control in the application, configure the NuGet packages of the Syncfusion components.

[How to configure package source and install Syncfusion NuGet packages in an existing project?](https://www.syncfusion.com/kb/7441/how-to-configure-package-source-and-install-syncfusion-nuget-packages-in-an-existing-project)

The following NuGet package should be installed to use the SfPopupLayout control in the application.

<table>
<tr>
<th> Project </th>
<th> Required package </th>
</tr>
<tr>
<td> Xamarin.Android </td>
<td> Syncfusion.Xamarin.SfPopupLayout.Android </td>
</tr>
</table>

### Adding SfPopupLayout Reference

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfPopupLayout to your project, open the NuGet package manager in Visual Studio, and search for [Syncfusion.Xamarin.SfPopupLayout.Android](https://www.nuget.org/packages/Syncfusion.Xamarin.SfPopUpLayout.Android), and then install it.

![SfPopupLayout in nuget.org](GettingStarted_images/NuGetInstall.png)

To know more about obtaining our components, refer to this [link](https://help.syncfusion.com/xamarin-android/introduction/download-and-installation). Also, if you prefer to manually refer the assemblies instead of NuGet, refer the list of assemblies mentioned in the table below.

<table>
<tr>
<th> Project </th>
<th> Required assembly </th>
</tr>
<tr>
<td> Xamarin.Android </td>
<td> android\Syncfusion.SfPopupLayout.Android.dll </td>
</tr>
</table>


I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Create a simple pop-up

The SfPopupLayout control can be configured entirely in C# code or using designer. In this walk through, you will create a new application with SfPopupLayout. To create a sample application, follow the topics: 

* [Adding SfPopupLayout in Xamarin.Android](#adding-sfpopuplayout-in-xamarin.android) 
* [Customize positioning](#Customize-positioning) 
* [Customizing layouts](#Customizing-layouts) 
* [Customizing animations](#Customizing-animations)

Create a new Android application in Xamarin Studio or Visual Studio for Xamarin.Android.

## Adding SfPopupLayout in Xamarin.Android using designer

1. Add a new xaml file inside the layout folder. 
2. Open the newly added file and switch to designer tab.
3. Drag the SfPopupLayout control from toolbox and drop it into the designer page. Preview will not be shown since this is a hosting control. You can only see the PopupView when deployed in the device.
4. Drag the Button control from toolbox and drop it inside the SfPopupLayout in designer page.
5. Open the properties window of SfPopupLayout and set the required properties.

The following code example illustrates how to display SfPopupLayout when set as a root view.

{% tabs %}
{% highlight Axml %}
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:custom="http://schemas.android.com/apk/res-auto"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:minWidth="25px"
    android:minHeight="25px">
    <Syncfusion.Android.PopupLayout.SfPopupLayout
        android:layout_width="match_parent"
        android:layout_height="59.0dp"
        android:id="@+id/sfPopupLayout1"
        android:layout_marginBottom="65.0dp"
		custom:animationMode="slideOnBottom"
        custom:appearanceMode="twoButton"
        custom:popupViewDeclineButtonText="Cancel"
        custom:popupViewAcceptButtonText="Install">
        <Button
            android:layout_width="177.0dp"
            android:layout_height="wrap_content"
            android:id="@+id/button1"
            android:text="Click To Show Popup" />
    </Syncfusion.Android.PopupLayout.SfPopupLayout>
</LinearLayout>
{% endhighlight %}

{% highlight c# %}
namespace Custom_designer_SfPopupLayout_android
{
    [Activity(Label = "Custom_designer_sfpopuplayout_android", MainLauncher = true, Icon = "@mipmap/icon")]
    public class MainActivity : Activity
    {
        SfPopupLayout Popup;
        protected override void OnCreate(Bundle savedInstanceState)
        {
            base.OnCreate(savedInstanceState);

            // Set our view from the "main" layout resource
            SetContentView(Resource.Layout.Main);
            Popup = FindViewById<SfPopupLayout>(Resource.Id.sfPopupLayout1);
            Button button = FindViewById<Button>(Resource.Id.button1);
            button.Click += button_clicked;
        }
        void button_clicked(object sender,EventArgs args)
        {
            Popup.Show();
        }
    }
}
{% endhighlight %}
{% endtabs %}

You can download the entire source code of this sample [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Custom_designer_sfpopuplayout_android1468892514).

Refer to this link to know the properties that can be configured using designer for SfPopupLayout.

## Adding SfPopupLayout in Xamarin.Android using C# code

1. Add the required assembly references to the project as mentioned in the [Assembly deployment](#assembly-deployment) section or install the NuGet as mentioned in the [NuGet Configuration](#nuget-configuration) section.

2. Import the SfPopupLayout control under the namespace `Syncfusion.Android.PopupLayout`.

3. The SfPopupLayout can be displayed by the following cases.

### Displaying Popup when SfPopupLayout is set as root view 

The SfPopupLayout can be displayed by making it as base view or content view of the activity. For first case, set the view over which the SfPopupLayout should be displayed as the content of the SfPopupLayout using the [SfPopupLayout.Content](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.SfPopupLayout.html#Syncfusion_Android_PopupLayout_SfPopupLayout__ctor_Android_Content_Context_) property. Create an instance of the SfPopupLayout control and set it as content view of that activity. 

Refer to the following code example for displaying popup.
 

{% tabs %}
{% highlight c# %}

using Syncfusion.Android.PopupLayout;

namespace GettingStarted
{
    public class MainActivity : Activity 
    {
       SfPopupLayout popupLayout;
       Button showPopupButton;
       LinearLayout mainLayout;

        protected override void OnCreate (Bundle bundle) 
        {
            base.OnCreate (bundle); 
            mainLayout = new LinearLayout(this);
            mainLayout.Orientation = Orientation.Vertical;
            mainLayout.SetBackgroundColor(Color.White);

            showPopupButton = new Button(this);
			// If creating button instance via axml uncomment the below line code and comment the above line code
			// showPopupButton = FindViewById<Button>(Resource.Id.button1);
            showPopupButton.Click += ShowPopupButton_Click;
            showPopupButton.SetTextColor(Color.White);
            showPopupButton.Text = "Click to show Popup";

            mainLayout.AddView(showPopupButton, ViewGroup.LayoutParams.MatchParent, ViewGroup.LayoutParams.WrapContent);
            popupLayout = new SfPopupLayout(this);
			//if creating SfPopupLayout instance via axml uncomment the below line code and comment the above line code.
			// popupLayout = FindViewById<SfPopupLayout>(Resource.Id.sfPopupLayout1);
           
            popupLayout.Content = mainLayout;

            SetContentView(popupLayout);
        } 

        private void ShowPopupButton_Click(object sender, System.EventArgs e)
        {
            popupLayout.Show();
        }
    } 
}

{% endhighlight %}

{% highlight  axml %}
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:minWidth="25px"
    android:minHeight="25px">
    <Syncfusion.Android.PopupLayout.SfPopupLayout
        android:layout_width="match_parent"
        android:layout_height="59.0dp"
        android:id="@+id/sfPopupLayout1">
        <Button
            android:layout_width="375.5dp"
            android:layout_height="wrap_content"
            android:id="@+id/button1"
            android:text="Click To Show Popup" />
    </Syncfusion.Android.PopupLayout.SfPopupLayout>
</LinearLayout>
{% endhighlight %}
{% endtabs %}

### Displaying pop-up when SfPopupLayout is not set as root view 

 You can continue to keep your view as the content view of the activity and still display pop-up over your view by simply calling the SfPopupLayout.Show() method. 

 Refer to the following code example for displaying popup.
 
{% tabs %}
{% highlight c# %}

using Syncfusion.Android.PopupLayout;

namespace GettingStarted
{
    public class MainActivity : Activity 
    {
       SfPopupLayout popupLayout;
       Button showPopupButton;
       LinearLayout mainLayout;

        protected override void OnCreate (Bundle bundle) 
        {
            base.OnCreate (bundle); 
            mainLayout = new LinearLayout(this);
            mainLayout.Orientation = Orientation.Vertical;
            mainLayout.SetBackgroundColor(Color.White);

            showPopupButton = new Button(this);
            showPopupButton.Click += ShowPopupButton_Click;
            showPopupButton.SetTextColor(Color.White);
            showPopupButton.Text = "Click to show Popup";

            mainLayout.AddView(showPopupButton, ViewGroup.LayoutParams.MatchParent, ViewGroup.LayoutParams.WrapContent);
            popupLayout = new SfPopupLayout(this);
            SetContentView(mainLayout);
        } 

        private void ShowPopupButton_Click(object sender, System.EventArgs e)
        {
            popupLayout.Show();
        }
    } 
}

{% endhighlight %}

{% endtabs %}

Executing the above codes renders the following output in an android device.

![SfPopupLayout Default Appearance](GettingStarted_images/DefaultAppearance.png)

You can download the source code of this sample [here](https://www.syncfusion.com/downloads/support/directtrac/general/ze/sfpopuplayout_android-1829756829).

## Customize positioning

The SfPopupLayout allows showing the pop-up content at various positions.

The following list of options are available to position the SfPopupLayout in the desired position:

* `Center positioning`: Use the [SfPopupLayout.IsOpen](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.SfPopupLayout.html#Syncfusion_Android_PopupLayout_SfPopupLayout_IsOpen) property or [SfPopupLayout.Show()](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.SfPopupLayout.html#Syncfusion_Android_PopupLayout_SfPopupLayout_Show) to display the SfPopupLayout at the center.
* `Absolute positioning`: Use the [SfPopupLayout.Show(x-position, y-position)](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.SfPopupLayout.html#Syncfusion_Android_PopupLayout_SfPopupLayout_Show) to display the SfPopupLayout at the specified X and y positions.
* `OnTouch`: Use the [SfPopupLayout.ShowAtTouchPoint()](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.SfPopupLayout.html#Syncfusion_Android_PopupLayout_SfPopupLayout_ShowAtTouchPoint) to display the SfPopupLayout at the touch point.
* `Relative positioning`: Use the [SfPopupLayout.ShowRelativeToView(View, RelativePosition)](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.SfPopupLayout.html#Syncfusion_Android_PopupLayout_SfPopupLayout_ShowRelativeToView_Android_Views_View_Syncfusion_Android_PopupLayout_RelativePosition_Android_Views_View_) to display the SfPopupLayout at any of the 8 positions relative to the specified view.
* `Absolute relative positioning`: Use the [SfPopupLayout.ShowRelativeToView(View, RelativePosition,x position,y position)](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.SfPopupLayout.html#Syncfusion_Android_PopupLayout_SfPopupLayout_ShowRelativeToView_Android_Views_View_Syncfusion_Android_PopupLayout_RelativePosition_System_Double_System_Double_) to display the SfPopupLayout at an absolute x,y coordinate from the relative position of the specified view.

More information for pop-up positioning is in this [link](https://help.syncfusion.com/xamarin-android/sfpopuplayout/popup-positioning).

## Customizing layouts

By default, you can choose from the following layouts available in the SfPopupLayout using the property [SfPopupLayout.AppearanceMode](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.AppearanceMode.html).

* [OneButton](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.AppearanceMode.html): Shows the SfPopupLayout with one button in the footer view. This is the default value.
* [TwoButton](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.AppearanceMode.html): Shows the SfPopupLayout with two buttons in the footer view.

You can also customize the entire view of the pop-up by loading the templates or custom views individually for the header, body, and footer.

### Load a view as content view  in the popup body

Any view can be added as the pop-up content using the [SfPopupLayout.PopupView.ContentView](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.PopupView.html#Syncfusion_Android_PopupLayout_PopupView_ContentView) property to refresh it. Refer to the following code example in which a text view is added as pop-up content and  displaying pop-up when the SfPopupLayout is set as root view

{% tabs %}
{% highlight c# %}

//MainActivity.cs

protected override void OnCreate(Bundle bundle)
{
	....

	 TextView popupContentView = new TextView(this) { Text = "This is the Customized view for SfPopupLayout" };
     popupContentView.SetTextColor(Color.Black);
     popupContentView.SetBackgroundColor(Color.LightSkyBlue);
      
     // Adding ContentView of the SfPopupLayout
     popupLayout.PopupView.ContentView = popupContentView;
	....
}

{% endhighlight %}
{% endtabs %}

Executing the above codes renders the following output in an android device.

![Popup with custom view](GettingStarted_images/ContentView.png)

N> Setting the content view is same for both cases i.e. displaying the pop-up when the SfPopupLayout is set as root view and vice versa.

## Customizing animations

Built-in animations are available in the SfPopupLayout applied when the PopupView opens and closes in the screen.

By default, you can choose from the following animations available in the SfPopupLayout using the property [SfPopupLayout.AnimationMode](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.AnimationMode.html).

* [Zoom](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.AnimationMode.html): Zoom-out animation will be applied when the PopupView opens, and zoom-in animation will be applied when the PopupView closes. This is the default AnimationMode.
* [Fade](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.AnimationMode.html): Fade-out animation will be applied when the PopupView opens, and fade-in animation will be applied when the PopupView closes.
* [SlideOnLeft](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.AnimationMode.html): PopupView will be animated from left-to-right when it opens, and from right-to-left when the PopupView closes.
* [SlideOnRight](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.AnimationMode.html): PopupView will be animated from right-to-left, when it opens and from left-to-right when the PopupView closes.
* [SlideOnTop](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.AnimationMode.html): PopupView will be animated from top-to-bottom when it opens, and from bottom-to-top when the PopupView closes.
* [SlideOnBottom](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.AnimationMode.html): PopupView will be animated from bottom-to-top, when it opens and from top-to-bottom when the PopupView closes
* [None](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.PopupLayout.AnimationMode.html): Animation will not be applied.

More information for pop-up animations is in this [link](https://help.syncfusion.com/xamarin-android/sfpopuplayout/popup-animations).

## Properties configured using designer

<table>
<tr>
<th> Properties</th>
<th> Attribute Name</th>
</tr>
<tr><td>AcceptButtonBackGroundColor</td><td>popupViewAcceptButtonBackGroundColor</td></tr>
<tr><td>AcceptButtonTextColor</td><td>popupViewAcceptButtonTextColor</td></tr>
<tr><td>AcceptButtonText</td><td>popupViewAcceptButtonText</td></tr>
<tr><td>AnimationDuration</td><td>popupViewAnimationDuration</td></tr>
<tr><td>AnimationMode</td><td>AnimationMode</td></tr>
<tr><td>AppearanceMode</td><td>appearanceMode</td></tr>
<tr><td>BorderColor</td><td>popupViewBorderColor</td></tr>
<tr><td>BorderThickness</td><td>popupViewBorderThickness</td></tr>
<tr><td>CornerRadius</td><td>popupViewCornerRadius</td></tr>
<tr><td>DeclineButtonBackGroundColor</td><td>popupViewDeclineButtonBackGroundColor</td></tr>
<tr><td>DeclineButtonTextColor</td><td>DeclineButtonTextColor</td></tr>
<tr><td>DeclineButtonText</td><td>popupViewDeclineButtonText</td></tr>
<tr><td>FooterBackGroundColor</td><td>popupViewFooterBackGroundColor</td></tr>
<tr><td>FooterHeight</td><td>popupViewFooterHeight</td></tr>
<tr><td>HeaderHeight</td><td>popupViewHeaderHeight</td></tr>
<tr><td>HeaderTitle</td><td>popupViewHeaderTitle</td></tr>
<tr><td>HeaderTextGravity</td><td>popupViewHeaderTextGravity</td></tr>
<tr><td>HeightRequest</td><td>popupViewHeightRequest</td></tr>
<tr><td>IsOpen</td> <td>popupIsOpen</td></tr>
<tr><td>MessageBackGroundColor</td><td>popupViewMessageBackGroundColor</td></tr>
<tr><td>MessageTextColor</td><td>popupViewMessageTextColor</td></tr>
<tr><td>MessageTextSize</td><td>popupViewMessageTextSize</td></tr>
<tr><td>PopupMessage</td><td>popupViewPopupMessage</td></tr>
<tr><td>ShowCloseButton</td><td>showPopupViewCloseButton</td></tr>
<tr><td>ShowHeader</td><td>showPopupViewHeader</td></tr>
<tr><td>ShowFooter</td><td>showPopupViewFooter</td></tr>
<tr><td>StaysOpen</td><td>staysOpen</td></tr>
<tr><td>WidthRequest</td><td>popupViewWidthRequest</td></tr>
</table>
