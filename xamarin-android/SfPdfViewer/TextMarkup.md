---
layout: post
title:  Add & modify text markups PDF viewer Xamarin.Android | Syncfusion
description: PDF viewer Xamarin.Android allows user to highlight, underline and strikethrough the text content in the PDF document.
platform: Xamarin.Android
control: SfPdfViewer
documentation: ug
---

# Working with text markup annotation

The PDF viewer supports to add, edit, and delete text markup annotations (highlight, underline, and strikethrough) in the PDF document.

AXML code for android layout

{% tabs %}
{% highlight axml %}

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:focusable="true"
    android:focusableInTouchMode="true"
    android:id="@+id/parentview">
   <FrameLayout
        android:id="@+id/parent"
        android:layout_width="match_parent"
        android:layout_height="50dp">
        <GridLayout
            android:id="@+id/toolbarGrid"
            android:background="#E9E9E9"
            android:layout_width="match_parent"
            android:columnCount="5"
            android:layout_height="50dp">
            <Button
                android:id="@+id/annotationButton"
                android:background="#E9E9E9"
                android:layout_width="40dp"
                android:layout_height="30dp"
                android:padding="0dp"
                android:layout_marginLeft="15dip"
                android:layout_marginTop="10dip"/>
             <Button
                android:id="@+id/annotationBackButton"
                android:layout_width="40dp"
                android:layout_height="30dp"
                android:background="#E9E9E9"
                android:text="BackButton"
                android:layout_marginLeft="10dip"
                android:layout_marginRight ="10dip"
                android:layout_marginTop="10dip" />
        </GridLayout>
   </FrameLayout>
   <Syncfusion.SfPdfViewer.Android.SfPdfViewer
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:layout_weight="1"
        android:id="@+id/pdfviewercontrol" />
</LinearLayout>

{% endhighlight %}
{% endtabs %}

C# code associated with the above axml layout

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewerControl;
Button annotationButton;
protected override void OnCreate(Bundle bundle)
{
	base.OnCreate(bundle);
	SetContentView(Resource.Layout.Main);
	pdfViewerControl=(SfPdfViewer)mainView.FindViewById(Resource.Id.pdfviewercontrol);
	annotationButton = (Button)mainView.FindViewById(Resource.Id.annotationButton);
	annotationButton.SetTextColor(Android.Graphics.Color.Rgb(103, 103, 103));
	annotationButton.TextSize = 18;
	annotationButton.Click += AnnotationButton_Click;   
	
	annotationBackButton =(Button)mainView.FindViewById(Resource.Id.annotationBackButton);
	annotationBackButton.SetTextColor(Android.Graphics.Color.Rgb(103, 103, 103));
	annotationBackButton.TextSize = 18;
	annotationBackButton.Click += AnnotationBackButton_Click;             
}

{% endhighlight %}
{% endtabs %}

## Highlight a text

The two ways to highlight a text in the PDF document are: 

1. By selecting the text and highlight option

	* Select the text in the PDF document.
    * Select “Highlight” option in the context menu that appears.
	
2. Enabling the highlight mode and selecting the text

By default, the PDF viewer will be in the scrolling and text selection mode. Once highlight annotation mode is activated, scrolling of the document will be frozen and highlight annotations will be included when you swipe over the texts in the pages of the PDF document.

C# code to switch to highlight annotation mode

{% tabs %}
{% highlight c# %}

private void AnnotationButton_Click(object sender, EventArgs e)
{
    pdfViewerControl.AnnotationMode = AnnotationMode.Highlight;        
}

{% endhighlight %}
{% endtabs %}

C# code to switch to normal mode from annotation mode.

{% tabs %}
{% highlight c# %}

private void AnnotationBackButton_Click(object sender, EventArgs e)
{
    pdfViewerControl.AnnotationMode = AnnotationMode.None;
}

{% endhighlight %}
{% endtabs %}

## Underline a text

The two ways to underline a text in the PDF document are: 

1. By selecting the text and underline option

	* Select the text in the PDF document.
    * Select “Underline” option in the context menu that appears.
	
2. Enabling the underline mode and selecting the text

By default, the PDF viewer will be in the scrolling and text selection mode. Once underline annotation mode is activated, scrolling of the document will be frozen and underline annotations will be included when you swipe over the texts in the pages of the PDF document.


C# code to switch to underline annotation mode

{% tabs %}
{% highlight c# %}

private void AnnotationButton_Click(object sender, EventArgs e)
{
	pdfViewerControl.AnnotationMode = AnnotationMode.Underline;        
}


{% endhighlight %}
{% endtabs %}

C# code to switch to normal mode from annotation mode.

{% tabs %}
{% highlight c# %}

private void AnnotationBackButton_Click(object sender, EventArgs e)
{
       pdfViewerControl.AnnotationMode = AnnotationMode.None;
}


{% endhighlight %}
{% endtabs %}

## Strikethrough a text

The two ways to strikethrough a text in the PDF document are: 

1. By selecting the text and strikethrough option

	* Select the text in the PDF document.
    * Select “Strikethrough” option in the context menu that appears.
	
2. Enabling the strikethrough mode and selecting the text

By default, the PDF viewer will be in the scrolling and text selection mode. Once strikethrough annotation mode is activated, scrolling of the document will be frozen and strikethrough annotations will be included when you swipe over the texts in the pages of the PDF document.

C# code to switch to strikethrough annotation mode

{% tabs %}
{% highlight c# %}

private void AnnotationButton_Click(object sender, EventArgs e)
{
   pdfViewerControl.AnnotationMode = AnnotationMode.Strikethrough;        
}

{% endhighlight %}
{% endtabs %}

C# code to switch to normal mode from annotation mode.
{% tabs %}
{% highlight c# %}

private void AnnotationBackButton_Click(object sender, EventArgs e)
{
	pdfViewerControl.AnnotationMode = AnnotationMode.None;
}

{% endhighlight %}
{% endtabs %}

## Deleting a text markup annotation

The PDF viewer removes a single annotation in the PDF document, removes all the annotations in a page, and removes all the annotations in the document.

### Removing a single annotation.

The following code snippet illustrates removing a single annotation from the PDF document.

C# code to removing a single annotation

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewerControl;
Button removeButton; 
TextMarkupAnnotation selectedAnnotation;
protected override void OnCreate(Bundle bundle)
{
	base.OnCreate(bundle);
	SetContentView(Resource.Layout.Main);
	pdfViewerControl=(SfPdfViewer)mainView.FindViewById(Resource.Id.pdfviewercontrol);
	pdfViewerControl.TextMarkupSelected += PdfViewerControl_TextMarkupSelected;
	annotationButton = (Button)mainView.FindViewById(Resource.Id.annotationButton);
	annotationButton.SetTextColor(Android.Graphics.Color.Rgb(103, 103, 103));
	annotationButton.TextSize = 18;
	annotationButton.Click += AnnotationButton_Click;         
}
private void PdfViewerControl_TextMarkupSelected(object sender, TextMarkupSelectedEventArgs args)
{
	selectedAnnotation = (sender as TextMarkupAnnotation);
}
private void AnnotationButton_Click(object sender, EventArgs e) 
{
	if (selectedAnnotation != null)
		pdfViewerControl.RemoveAnnotation(selectedAnnotation); 
}

{% endhighlight %}
{% endtabs %}

### Removing all the annotations in a page

The ClearAllAnnotations(int pageNumber) API can be used to remove all the annotations in a page of the PDF document. 

C# code to removing all the annotations in a page

{% tabs %}
{% highlight c# %}

private void AnnotationButton_Click(object sender, EventArgs e) 
{
	pdfViewerControl.ClearAllAnnotations(pageNumber);
}


{% endhighlight %}
{% endtabs %}

### Removing all the annotations in the PDF document

The ClearAllAnnotations API can be used to remove all the annotations in the PDF document.


C# code to removing all the annotations in the PDF document

{% tabs %}
{% highlight c# %}

private void AnnotationButton_Click(object sender, EventArgs e) 
{
	pdfViewerControl.ClearAllAnnotations();
}

{% endhighlight %}
{% endtabs %}

## Editing the color of the text markup annotation

You can edit the color of the text markup annotation before including the annotation and after including the annotation. 

### Before inclusion of the annotation or Default color

You can alter the default color of the annotation to change the color while including annotation. Refer to the following code sample. 

C# code for editing the color of the text markup annotation.

{% tabs %}
{% highlight c# %}

private void AnnotationButton_Click(object sender, EventArgs e) 
{
	pdfViewerControl.AnnotationSettings.TextMarkup.Highlight.Color = Color.Red;
	pdfViewerControl.AnnotationSettings.TextMarkup.Underline.Color = Color.Magenta;
	pdfViewerControl.AnnotationSettings.TextMarkup.Strikethrough.Color = Color.Yellow;        
}


{% endhighlight %}
{% endtabs %}

N>Setting this property will not edit the color of annotations that are included in prior.

### After inclusion of the annotation

* Select the annotation.
* TextMarkupSelected event will be triggered and you will get a copy of selected annotation. 
* Edit the copy of annotation, so that you can edit the color of the text markup annotation.          

The following code snippet illustrates the same.    
C# code for changing the selected annotation color

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewerControl;
Button colorButton; 
TextMarkupAnnotation selectedAnnotation;
protected override void OnCreate(Bundle bundle)
{
	base.OnCreate(bundle);
	SetContentView(Resource.Layout.Main);
	pdfViewerControl=(SfPdfViewer)mainView.FindViewById(Resource.Id.pdfviewercontrol);
	pdfViewerControl.TextMarkupSelected += PdfViewerControl_TextMarkupSelected;
	annotationButton = (Button)mainView.FindViewById(Resource.Id.annotationButton);
	annotationButton.SetTextColor(Android.Graphics.Color.Rgb(103, 103, 103));
	annotationButton.TextSize = 18;
	annotationButton.Click += AnnotationButton_Click;         
}
private void PdfViewerControl_TextMarkupSelected(object sender, TextMarkupSelectedEventArgs args)
{
	selectedAnnotation = (sender as TextMarkupAnnotation);
}
private void AnnotationButton_Click(object sender, EventArgs e) 
{
	if (selectedAnnotation != null)
	    selectedAnnotation.Settings.Color = Color.Red;

}

{% endhighlight %}
{% endtabs %}

## Performing undo and redo

The PDF viewer performs undo and redo for the changes made in annotations in the PDF document. In text markup annotation undo and redo actions are provided for: 

* Inclusion of new text markup annotation.
* Deletion of text markup annotation.
* Changing the color of the text markup annotation. 

Refer to the following code sample to perform undo and redo operations:  

{% tabs %}
{% highlight axml %}

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:focusable="true"
    android:focusableInTouchMode="true"
    android:id="@+id/parentview">
    <FrameLayout
       android:id="@+id/parent"
       android:layout_width="match_parent"
       android:layout_height="50dp">
    <GridLayout
        android:id="@+id/toolbarGrid"
        android:background="#E9E9E9"
        android:layout_width="match_parent"
        android:columnCount="5"
        android:layout_height="50dp">
      
       <Button
        android:id="@+id/undoAnnotationButton"
        android:layout_width="30dp"
        android:layout_height="30dp"
        android:layout_marginLeft="55dip"
        android:layout_centerHorizontal="true"
        android:layout_gravity="center_horizontal"         
        android:layout_marginTop="10dip"
        android:background="#E9E9E9"/>
      
       <Button
        android:id="@+id/redoAnnotationButton"
        android:layout_width="30dp"
        android:layout_height="30dp"
        android:layout_centerHorizontal="true"      
        android:layout_gravity="center_horizontal"
        android:layout_marginLeft="20dip"
        android:layout_marginTop="10dip"
        android:background="#E9E9E9"/>        
    </GridLayout>  
   </FrameLayout>
<Syncfusion.SfPdfViewer.Android.SfPdfViewer
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:layout_weight="1"
        android:id="@+id/pdfviewercontrol" />
</LinearLayout>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewerControl;
Button undoButton;
Button redoButton;
protected override void OnCreate(Bundle bundle)
{
	base.OnCreate(bundle);
	SetContentView(Resource.Layout.Main);
	pdfViewerControl = (SfPdfViewer)mainView.FindViewById(Resource.Id.pdfviewercontrol);
	undoButton = mainView.FindViewById<Button>(Resource.Id.undoAnnotationButton);
	undoButton.Click += UndoButton_Click;
	redoButton = mainView.FindViewById<Button>(Resource.Id.redoAnnotationButton);
    redoButton.Click += RedoButton_Click;
}

private void UndoButton_Click(object sender, EventArgs e)
{
	pdfViewerControl.PerformUndo();
}

private void RedoButton_Click(object sender, EventArgs e)
{
	pdfViewerControl.PerformRedo();
}


{% endhighlight %}
{% endtabs %}

## Saving the PDF document

After performing all the changes over the PDF document in the PDF viewer, the resultant document can be saved using the SaveDocument() API.

{% tabs %}
{% highlight axml %}

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:focusable="true"
    android:focusableInTouchMode="true"
    android:id="@+id/parentview">
   <FrameLayout
        android:id="@+id/parent"
        android:layout_width="match_parent"
        android:layout_height="50dp">
        <GridLayout
            android:id="@+id/toolbarGrid"
            android:background="#E9E9E9"
            android:layout_width="match_parent"
            android:columnCount="5"
            android:layout_height="50dp">
            <Button
                android:id="@+id/saveButton"
                android:background="#E9E9E9"
                android:src="@drawable/Save"
                android:layout_width="40dp"
                android:layout_height="30dp"
                android:padding="0dp"
                android:layout_marginLeft="15dip"
                android:layout_marginTop="10dip"/>
        </GridLayout>
   </FrameLayout>
   <Syncfusion.SfPdfViewer.Android.SfPdfViewer
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:layout_weight="1"
        android:id="@+id/pdfviewercontrol" />
</LinearLayout>

{% endhighlight %}
{% endtabs %}

C# code for saving the PDF document

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewerControl;
Button saveButton;
protected override void OnCreate(Bundle bundle)
{
	base.OnCreate(bundle);
	SetContentView(Resource.Layout.Main);
	pdfViewerControl=(SfPdfViewer)mainView.FindViewById(Resource.Id.pdfviewercontrol);
	saveButton = (Button)mainView.FindViewById(Resource.Id.saveButton);
	saveButton.SetTextColor(Android.Graphics.Color.Rgb(103, 103, 103));
	saveButton.TextSize = 18;
	saveButton.Click += SaveButton_Click;              
}

private void SaveButton_Click(object sender, EventArgs e)
{
   	Stream stream = pdfViewerControl.SaveDocument();
}

{% endhighlight %}
{% endtabs %}
N>The CanUndo property is used to identify whether a document loaded in the PDF viewer is edited or not. When this property is set to true, means that the document in the PDF viewer is edited. 
