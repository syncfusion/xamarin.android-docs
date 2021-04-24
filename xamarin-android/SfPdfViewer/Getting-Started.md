---
layout: post
title:  View & review PDF using PDF Viewer Xamarin.Android | Syncfusion
description: Getting started section demonstrates how to create an application that displays a PDF file using Xamarin.Android PDF Viewer
platform: Xamarin.Android
control: SfPdfViewer
documentation: ug
---

# Getting started about SfPdfViewer

This section demonstrates how to create an application that displays a PDF file using SfPdfViewer control.

## Assemblies Required

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Essential Studio Installed location}\Essential Studio\{Essential Studio version}\Xamarin\lib\android\

Example: C:\Program Files (x86)\Syncfusion\Essential Studio\15.3.0.28\Xamarin\lib\android\

For creating a PDF Viewer for android, the following assemblies need to be referenced in your Android project.

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>Xamarin.Android</td>
<td>Syncfusion.Compression.Portable.dll<br/>Syncfusion.Pdf.Portable.dll<br/>Syncfusion.SfPdfViewer.Android.dll<br/>Syncfusion.SfBusyIndicator.Android.dll<br/>Syncfusion.SfRangeSlider.Android.dll<br/>Syncfusion.Licensing.dll<br/>Syncfusion.SfProgressBar.Android.dll<br/></td>
</tr>
</table>

N> Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [this link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion license key in your Xamarin.Android application to use our components.

## Create a simple PDF Viewer

Create a new blank application for Android using Visual Studio and name it as “GettingStartedDroid”. Refer the above-mentioned assemblies to the project. 

Add a PDF document you need to display in the PDF Viewer (here GIS Succinctly.pdf is used) and set the build action property as “AndroidAsset”.

Add the below code in the Main.axml to include PDF Viewer control.
   
{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent">
  <Syncfusion.SfPdfViewer.Android.SfPdfViewer
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:id="@+id/pdfviewercontrol" />
</LinearLayout>

{% endhighlight %}
{% endtabs %}

Please add the below code snippet in the MainActivity class

* In the MainActivity.cs class, declare an instance of SfPdfViewer globally. 
* In the override method OnCreate, set the content view to Main, locate the PDF viewer and load the PDF document.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer;

protected override void OnCreate(Bundle bundle)
{
    base.OnCreate(bundle);
    SetContentView(Resource.Layout.Main);
    pdfViewer = FindViewById<SfPdfViewer>(Resource.Id.pdfviewercontrol);
    Stream PdfStream = Assets.Open("GIS Succinctly.pdf");
    pdfViewer.LoadDocument(PdfStream);
}

{% endhighlight %}
{% endtabs %}

Deploying this project in the Android device would display the PDF document and allow you to scroll and zoom through the pages.

## Unloading PDF document from the Viewer

The SfPdfViewer control allows you to unload the PDF document from the viewer, when the PDF document is not in use anymore. This releases the PDF document and all its associated resources of the application.

You need to call the Unload method of SfPdfViewer control as in the below code snippet to achieve the same.

{% tabs %}   
{% highlight c# %}

pdfViewerControl.Unload();

{% endhighlight %}
{% endtabs %}

## How to get & set the current page number?

PageChanged event of the PDF viewer can be used to track the change in the current page being displayed in the PDF viewer. 

This below code snippet demonstrates how to track the current page number being viewed using PageChanged event and how to navigate to the respective page in the PDF Viewer.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:id="@+id/parentview">
  <FrameLayout
        android:id="@+id/parent"
        android:layout_width="match_parent"
        android:layout_height="50dp">
    <GridLayout
            android:id="@+id/toolbarGrid"
            android:background="#E9E9E9"
            android:layout_width="match_parent"
            android:columnCount="1"
            android:layout_height="50dp">
    <EditText
          android:id="@+id/pagenumberentry"
          android:layout_width="50dp"
          android:layout_height="30dp"
          android:layout_marginLeft="10dip"
          android:layout_marginTop="10dip"
          android:textAlignment="center"
          android:background="@drawable/edittextbg"
          android:textColor="@android:color/black"
          android:inputType="number"
          android:selectAllOnFocus="true"
          android:gravity="center" />
    </GridLayout>
  </FrameLayout>

  <Syncfusion.SfPdfViewer.Android.SfPdfViewer
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:id="@+id/pdfviewercontrol" />
</LinearLayout>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

EditText pageNumberEntry;
SfPdfViewer pdfViewer;

protected override void OnCreate(Bundle bundle)
{
    base.OnCreate(bundle);
    SetContentView(Resource.Layout.Main);
    
    //Access the controls in the design.
    pdfViewer = FindViewById<SfPdfViewer>(Resource.Id.pdfviewercontrol);
    pageNumberEntry = FindViewById<EditText>(Resource.Id.pagenumberentry);

    //Wire up PageChanged event with PdfViewer_PageChanged
    pdfViewer.PageChanged += PdfViewer_PageChanged;
    //Wire up KeyPress event with PageNumberEntry_KeyPress
    pageNumberEntry.KeyPress += PageNumberEntry_KeyPress;
}

private void PdfViewer_PageChanged(object sender, PageChangedEventArgs args)
{
    //Set the text of PageNumberEntry EditText control to the PageNumber event argument of PageChanged event.
    pageNumberEntry.Text = args.PageNumber.ToString();
}

private void PageNumberEntry_KeyPress(object sender, Android.Views.View.KeyEventArgs e)
{
    e.Handled = false;
    if (e.Event.Action == KeyEventActions.Down && e.KeyCode == Keycode.Enter)
    {
        int pageNumber = 0;
        //Validated the entered text input is integer or validate.
        if (int.TryParse((pageNumberEntry.Text), out pageNumber))
        {
            if ((pageNumber > 0) && (pageNumber <= pdfViewer.PageCount))
                pdfViewer.GoToPage(pageNumber);
        }
         pageNumberEntry.ClearFocus();
        InputMethodManager inputMethodManager = (InputMethodManager)mainView.Context.GetSystemService(Context.InputMethodService);
        inputMethodManager.HideSoftInputFromWindow(mainView.WindowToken, HideSoftInputFlags.None);
    }
}

{% endhighlight %}
{% endtabs %}

N>When a page number which is not in the bounds (1 – page count) is provided as an input to the GoToPage method, no action will be performed.

## How to dispose the managed resources of SfPdfViewer

The [`SfPdfViewer`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfPdfViewer.Android.SfPdfViewer.html) control allows you to dispose the managed resources which are associated with the viewer. You need to call the `Dispose` method of the [`SfPdfViewer`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfPdfViewer.Android.SfPdfViewer.html) control as shown in the following code sample to achieve the same.

{% tabs %}
{% highlight c# %}

//Disposes all the managed resources of SfPdfViewer
pdfViewer.Dispose();

{% endhighlight %}
{% endtabs %}

## How to clear the undo and redo stack

The [`SfPdfViewer`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfPdfViewer.Android.SfPdfViewer.html) control allows you to clear the undo and redo stacks that contain the changes that are made to the annotations in the PDF document, by calling the `ClearUndoRedoStack` API. When this method is called, the `CanUndo` and `CanRedo` properties will be set to `false`.

{% tabs %}
{% highlight c# %}

//To clear the undo and redo stack 
pdfViewer.ClearUndoRedoStack();

{% endhighlight %}
{% endtabs %}

## How to get the total page number?

PageCount property of the PDF viewer can be used to acquire the total number of pages in the PDF document that is being loaded. The PageCount property of the PDF viewer will be updated only after loading the PDF document, it can be tracked using DocumentLoaded event of the PDF viewer.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:id="@+id/parentview">
  <FrameLayout
        android:id="@+id/parent"
        android:layout_width="match_parent"
        android:layout_height="50dp">
    <GridLayout
            android:id="@+id/toolbarGrid"
            android:background="#E9E9E9"
            android:layout_width="match_parent"
            android:columnCount="1"
            android:layout_height="50dp">
    <TextView
          android:id="@+id/pagecounttext"
          android:layout_width="50dp"
          android:textAlignment="center"
          android:textColor="@android:color/black"
          android:layout_marginLeft="10dip"
          android:layout_marginTop="10dip"
          android:textSize="18dp"
          android:gravity="center"
          android:text="0" />
    </GridLayout>
  </FrameLayout>

  <Syncfusion.SfPdfViewer.Android.SfPdfViewer
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:id="@+id/pdfviewercontrol" />
</LinearLayout>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

TextView pageCountText;
SfPdfViewer pdfViewer;

protected override void OnCreate(Bundle bundle)
{
    base.OnCreate(bundle);
    SetContentView(Resource.Layout.Main);
    
    //Access the controls in the design.
    pdfViewer = FindViewById<SfPdfViewer>(Resource.Id.pdfviewercontrol);
    pageCountText = FindViewById<TextView>(Resource.Id.pagecounttext);

    //Wire up DocumentLoaded event with PdfViewer_DocumentLoaded
    pdfViewer.DocumentLoaded += PdfViewer_DocumentLoaded;
}

private void PdfViewer_DocumentLoaded(object sender, System.EventArgs args)
{
    //Set the text of the PageCountText TextView to PageCount of PDF viewer
    pageCountText.Text = pdfViewer.PageCount.ToString();
}

{% endhighlight %}
{% endtabs %}

## How to navigate to next page and previous page?

GoToPreviousPage and GoToNextPage methods of PDF viewer can be used to perform page navigation operations. 

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:id="@+id/parentview">
  <FrameLayout
        android:id="@+id/parent"
        android:layout_width="match_parent"
        android:layout_height="50dp">
    <GridLayout
            android:id="@+id/toolbarGrid"
            android:background="#E9E9E9"
            android:layout_width="match_parent"
            android:columnCount="2"
            android:layout_height="50dp">
      <ImageButton
          android:id="@+id/pagedownbutton"
          android:background="#E9E9E9"
          android:layout_marginLeft="10dip"
          android:layout_marginTop="10dip"
          android:src="@drawable/pagedown" />
      <ImageButton
          android:id="@+id/pageupbutton"
          android:background="#E9E9E9"
          android:src="@drawable/pageup"
          android:layout_marginLeft="10dip"
          android:layout_marginTop="10dip" />
    </GridLayout>
  </FrameLayout>

  <Syncfusion.SfPdfViewer.Android.SfPdfViewer
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:id="@+id/pdfviewercontrol" />
</LinearLayout>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

ImageButton pageDownButton;
ImageButton pageUpButton;
SfPdfViewer pdfViewer;

protected override void OnCreate(Bundle bundle)
{
    base.OnCreate(bundle);
    SetContentView(Resource.Layout.Main);
    
    //Access the controls in the design.
    pdfViewer = FindViewById<SfPdfViewer>(Resource.Id.pdfviewercontrol);
    pageDownButton = FindViewById<ImageButton>(Resource.Id.pagedownbutton);
    pageUpButton = FindViewById<ImageButton>(Resource.Id.pageupbutton);

    pageDownButton.Click += PageDownButton_Click;
    pageUpButton.Click += PageUpButton_Click;
}

private void PageUpButton_Click(object sender, System.EventArgs e)
{
    //Method navigates to the previous page of the PDF document
    pdfViewer.GoToPreviousPage();
}

private void PageDownButton_Click(object sender, System.EventArgs e)
{
    //Method navigates to the next page of the PDF document
    pdfViewer.GoToNextPage();
}

{% endhighlight %}
{% endtabs %}

N>When the current page is the first page, GoToPreviousPage method will not have any effect. Similarly, when in last page, GoToNextPage method will not have any effect.

## Rendering the appearance content of annotations

By  default,  the  PDF  viewer  does  not  render  the  appearance  content  of annotations. But the appearance can be rendered by flattening the annotations before loading the PDF. This can be achieved by setting the [Flatten](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfPdfViewer.Android.AnnotationSettings.html#Syncfusion_SfPdfViewer_Android_AnnotationSettings_Flatten) API to true. The default value of the API is set to false.

{% tabs %}
{% highlight c# %}

//Sets a value whether the annotations should be flattened when the PDF is loaded or not.
pdfViewerControl.AnnotationSettings.Flatten = true;

//Loads the PDF. 
pdfViewerControl.LoadDocument(stream);

{% endhighlight %}
{% endtabs %}

N>Annotations are only flattened when the page is rendered in the viewer only  for  viewing  the  appearance  of  annotations.  Once,  the  annotations  have flattened  the  interactions  such  as  select,  edit,  resize,  and  remove  cannot  be performed.  Setting  the  [Flatten](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfPdfViewer.Android.AnnotationSettings.html#Syncfusion_SfPdfViewer_Android_AnnotationSettings_Flatten)  API  to  true  does  not  affect  the  save  and annotation export operations and the annotations will not be flattened in these operations.

## Designing a toolbar

This section depicts how to design a toolbar for the PDF viewer and include functionalities such as page navigation options. This simple toolbar consists of options such as current page number, total page count in the PDF document, go to previous page and go to next page.

In Main.axml, please add this code snippet to design the toolbar to add the page navigation options.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:id="@+id/parentview">
  <FrameLayout
        android:id="@+id/parent"
        android:layout_width="match_parent"
        android:layout_height="50dp">
    <GridLayout
            android:id="@+id/toolbarGrid"
            android:background="#E9E9E9"
            android:layout_width="match_parent"
            android:columnCount="2"
            android:layout_height="50dp">
      <ImageButton
          android:id="@+id/pagedownbutton"
          android:background="#E9E9E9"
          android:layout_marginLeft="10dip"
          android:layout_marginTop="10dip"
          android:src="@drawable/pagedown" />
      <ImageButton
          android:id="@+id/pageupbutton"
          android:background="#E9E9E9"
          android:src="@drawable/pageup"
          android:layout_marginLeft="10dip"
          android:layout_marginTop="10dip" />
    </GridLayout>
  </FrameLayout>

  <Syncfusion.SfPdfViewer.Android.SfPdfViewer
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:id="@+id/pdfviewercontrol" />
</LinearLayout>

{% endhighlight %}
{% endtabs %}

In MainActivity.cs, please add the below code snippet which contains the implementation for the following operations

* Access & display the current page number being displayed and navigate to the specified page.
* Display the total number of pages
* Navigate to the previous page
* Navigate to the next page

{% tabs %}
{% highlight c# %}

using Android.App;
using Android.Widget;
using Android.OS;
using Syncfusion.SfPdfViewer.Android;
using System.IO;
using Android.Views;
using Android.Views.InputMethods;
using Android.Content;

namespace GettingStartedDroid
{
    [Activity(Label = "GettingStartedDroid", MainLauncher = true, Icon = "@drawable/icon")]
    public class MainActivity : Activity
    {
        SfPdfViewer pdfViewer;
        EditText pageNumberEntry;
        TextView pageCountText;
        ImageButton pageDownButton;
        ImageButton pageUpButton;
        LinearLayout mainView;
        protected override void OnCreate(Bundle bundle)
        {
            base.OnCreate(bundle);
            SetContentView(Resource.Layout.Main);

            //Access the controls in the design.
            pdfViewer = FindViewById<SfPdfViewer>(Resource.Id.pdfviewercontrol);
            pageNumberEntry = FindViewById<EditText>(Resource.Id.pagenumberentry);
            pageCountText = FindViewById<TextView>(Resource.Id.pagecounttext);
            pageDownButton = FindViewById<ImageButton>(Resource.Id.pagedownbutton);
            pageUpButton = FindViewById<ImageButton>(Resource.Id.pageupbutton);
            mainView = FindViewById<LinearLayout>(Resource.Id.parentview);

            //Wire up events.
            pageNumberEntry.KeyPress += PageNumberEntry_KeyPress;
            pageDownButton.Click += PageDownButton_Click;
            pageUpButton.Click += PageUpButton_Click;
            pdfViewer.DocumentLoaded += PdfViewer_DocumentLoaded;
            pdfViewer.PageChanged += PdfViewer_PageChanged;

            //Access the document in the resource as stream and load it in the PDF viewer.
            Stream PdfStream = Assets.Open("GIS Succinctly.pdf");
            pdfViewer.LoadDocument(PdfStream);
        }

        private void PdfViewer_PageChanged(object sender, PageChangedEventArgs args)
        {
            pageNumberEntry.Text = args.PageNumber.ToString();
        }

        private void PdfViewer_DocumentLoaded(object sender, System.EventArgs args)
        {
            //Set the text of the PageCountText TextView to PageCount of PDF viewer
            pageCountText.Text = pdfViewer.PageCount.ToString();
        }

        private void PageUpButton_Click(object sender, System.EventArgs e)
        {
            //Method navigates to the previous page of the PDF document
            pdfViewer.GoToPreviousPage();
        }

        private void PageDownButton_Click(object sender, System.EventArgs e)
        {
            //Method navigates to the next page of the PDF document
            pdfViewer.GoToNextPage();
        }

        private void PageNumberEntry_KeyPress(object sender, Android.Views.View.KeyEventArgs e)
        {
            e.Handled = false;
            if (e.Event.Action == KeyEventActions.Down && e.KeyCode == Keycode.Enter)
            {
                int pageNumber = 0;
                if (int.TryParse((pageNumberEntry.Text), out pageNumber))
                {
                    //Validated the entered text input is integer or validate.
                    if ((pageNumber > 0) && (pageNumber <= pdfViewer.PageCount))
                        pdfViewer.GoToPage(pageNumber);
                    else
                    {
                        DisplayAlertDialog();
                        pageNumberEntry.Text = pdfViewer.PageNumber.ToString();
                    }
                }
                pageNumberEntry.ClearFocus();
                InputMethodManager inputMethodManager = (InputMethodManager)mainView.Context.GetSystemService(Context.InputMethodService);
                inputMethodManager.HideSoftInputFromWindow(mainView.WindowToken, HideSoftInputFlags.None);
            }
        }

        void DisplayAlertDialog()
        {
            AlertDialog.Builder alertDialog = new AlertDialog.Builder(mainView.Context);
            alertDialog.SetTitle("Error");
            alertDialog.SetMessage("Please enter the valid page number");
            alertDialog.SetPositiveButton("OK", (senderAlert, args) => { });
            Dialog dialog = alertDialog.Create();
            dialog.Show();
        }
    }
}

{% endhighlight %}
{% endtabs %}

The final output will look as like in the below screenshot.

![SfPdfViewer](pdfviewer_images/gettingstarted.png)

This demo can be downloaded from the below link.

http://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStartedDroid-1943126494.zip