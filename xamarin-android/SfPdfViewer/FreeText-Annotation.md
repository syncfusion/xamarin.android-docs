---
layout: post
title:  Freetext annotations in Xamarin.Android PDF Viewer | Syncfusion
description: Learn about free text annotations support in Syncfusion Xamarin.Android Pdf Viewer (SfPdfViewer) control and more details.
platform: Xamarin.Android
control: SfPdfViewer
documentation: ug
---

# Working with free text annotations

PDF viewer allows you to include free text annotations in a PDF document and provides options to modify or remove the existing ones.

## Adding free text annotations

### Enabling free text mode

Set the `AnnotationMode` property of the PDF viewer to FreeText. After setting the annotation mode, the zooming, panning, and scrolling will be disabled, tap anywhere on the PDF page displayed and a popup will appear. Type the text in the popup and click &#34;Ok&#34; to add text to the page. Zooming, panning, and scrolling will be enabled again if the free text annotation is added.

In all code snippets, the term ApplicationContext represents  the `ApplicationContext` property of the MainActivity.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer(ApplicationContext);
pdfViewer.AnnotationMode = AnnotationMode.FreeText;

{% endhighlight %}
{% endtabs %}

### Disabling free text mode

Setting the AnnotationMode to `None` disables the free text annotation mode. 

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer(ApplicationContext);
pdfViewer.AnnotationMode = AnnotationMode.None;

{% endhighlight %}
{% endtabs %}

### Detecting the inclusion of free text annotations

The event `FreeTextAnnotationAdded` will be raised when a free text annotation is added to the PDF.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer(ApplicationContext);
pdfViewer.FreeTextAnnotationAdded += PdfViewer_FreeTextAnnotationAdded;

{% endhighlight %}
{% endtabs %}

## Detecting tap on free text annotations

Tapping a free text annotation selects it or deselects if it is already selected. The event `FreeTextAnnotationTapped` is raised when a free text is tapped.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer(ApplicationContext);
pdfViewer.FreeTextAnnotationTapped += PdfViewer_FreeTextAnnotationTapped;

{% endhighlight %}
{% endtabs %}

## Selecting free text annotations

You can select a free text annotation by tapping on it. When a free text is selected, the `FreeTextAnnotationSelected` event is raised.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer(ApplicationContext);
pdfViewer.FreeTextAnnotationSelected += PdfViewer_FreeTextAnnotationSelected;

{% endhighlight %}
{% endtabs %}

When the event is raised, the properties of the selected free text can be obtained from the `args` parameter of the event handler.

{% tabs %}
{% highlight c# %} 

private void PdfViewer_FreeTextAnnotationSelected(object sender, FreeTextAnnotationSelectedEventArgs args)
{
	//Obtain the bounds of the annotation
	Rect bounds = args.Bounds;

	//Obtain the text in the annotation
	string text = args.Text;

	//Obtain the size of the text in the annotation
	float textSize = args.FontSize;

	//Obtain the color of the text
	Color textColor = args.TextColor;

	//Obtain the page number in which the selected annotation is
	int pageNumber = args.PageNumber;
}

{% endhighlight %}
{% endtabs %}

## Deselecting free text annotations

You can deselect a selected free text annotation by tapping on it or somewhere else on the PDF page. Deselection can be detected using the `FreeTextAnnotationDeselected` event.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer(ApplicationContext);
pdfViewer.FreeTextAnnotationDeselected += PdfViewer_FreeTextAnnotationDeselected;

{% endhighlight %}
{% endtabs %}

## Customizing the appearance of free text annotations

You can customize the default text color and size of all free text annotations to be added. This will not affect the already added free text annotations. The appearance of a selected free text can also be modified. 

### Setting the default text color

You can set the default text color of the free text annotations by using the `SfPdfViewer.AnnotationSettings.FreeText.TextColor` property. Refer to the following code.
 
{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer(ApplicationContext);
pdfViewer.AnnotationSettings.FreeText.TextColor = Color.Red;

{% endhighlight %}
{% endtabs %}

### Setting the default text size

You can set the default text size of the free text annotations by using the `SfPdfViewer.AnnotationSettings.FreeText.TextSize` property. Refer to the following code example.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer(ApplicationContext);
pdfViewer.AnnotationSettings.FreeText.TextSize = 4; 

{% endhighlight %}
{% endtabs %}

### Changing the properties of a selected free text

You can change the properties of the selected annotation by casting the `sender` parameter of the `FreeTextAnnotationSelected` event handler to `FreeTextAnnotation` and modifying its properties. The following code shows how to change the properties.

{% tabs %}
{% highlight c# %} 

SfPdfViewer pdfViewer = new SfPdfViewer(ApplicationContext);
pdfViewer.FreeTextAnnotationSelected += PdfViewer_FreeTextAnnotationSelected;
changeFreeTextPropertiesButton.Clicked += ChangeFreeTextPropertiesButton_Clicked;
FreeTextAnnotation selectedFreeTextAnnotation;

private void PdfViewer_FreeTextAnnotationSelected(object sender, FreeTextAnnotationSelectedEventArgs args)
{
	//Cast the sender object to free text annotation
	selectedFreeTextAnnotation = sender as FreeTextAnnotation;
}

private void ChangeFreeTextPropertiesButton_Clicked(object sender, EventArgs e)
{
	//Change the color of the text
    selectedFreeTextAnnotation.Settings.TextColor = Color.Purple;

    //Change the size of the text
    selectedFreeTextAnnotation.Settings.TextSize = 6;
}

{% endhighlight %}
{% endtabs %}

## Moving or resizing free text annotations

To move or resize the annotation, it should be selected. After the selector appears, tapping and dragging anywhere inside the selector will move the annotation. Tapping on the bubbles around the selector and dragging will resize the annotation. 

### Detecting the move or resize of a free text

The event `FreeTextAnnotationMovedOrResized` is raised when you move or resize the selected annotation.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer(ApplicationContext);
pdfViewer.FreeTextAnnotationMovedOrResized += PdfViewer_FreeTextAnnotationMovedOrResized;

{% endhighlight %}
{% endtabs %}

The properties of the moved or resized free text can be obtained from the `args` parameter of the event handler.

{% tabs %}
{% highlight c# %}

private void PdfViewer_FreeTextAnnotationMovedOrResized(object sender, FreeTextAnnotationMovedOrResizedEventArgs args)
{
	//Retrieve the old bounds of the annotation
	Rect oldBounds = args.OldBounds;

	//Retrieve the new bounds of the annotation
	Rect newBounds = args.NewBounds;

	//Retrieve the current page number
	int pageNumber = args.PageNumber;
}
{% endhighlight %}
{% endtabs %}

## Deleting free text annotations

The PDF viewer can remove a selected annotation or all the annotations in the PDF document.

### Removing all annotations

The `ClearAllAnnotations` method can be used to delete all annotations irrespective of their types from the PDF. 

{% tabs %}
{% highlight c# %}

pdfViewer.ClearAllAnnotations();

{% endhighlight %}
{% endtabs %}

### Removing a selected free text annotation

The following code snippet illustrates removing a selected free text from the PDF document.
{% tabs %}
{% highlight c# %}

FreeTextAnnotation selectedFreeTextAnnotation;

private void PdfViewer_FreeTextAnnotationSelected(object sender, FreeTextAnnotationSelectedEventArgs args)
{
	//Cast the sender object to free text annotation.
	selectedFreeTextAnnotation = sender as FreeTextAnnotation;
}

private void deleteFreeTextAnnotationButton_Clicked(object sender, EventArgs e)
{
	//Delete the selected free text annotation
	pdfViewer.RemoveAnnotation(selectedFreeTextAnnotation);
}

{% endhighlight %}
{% endtabs %}

### Detecting the removal of a free text

The event `FreeTextAnnotationRemoved` is raised when a free text annotation is removed from the PDF.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer(ApplicationContext);
pdfViewer.FreeTextAnnotationRemoved += PdfViewer_FreeTextAnnotationRemoved;

{% endhighlight %}
{% endtabs %}

The properties of the removed free text can be obtained from the `args` parameter of the event handler. 

{% tabs %}
{% highlight c# %}
private void PdfViewer_FreeTextAnnotationRemoved(object sender, FreeTextAnnotationRemovedEventArgs args)
{
	//Get the bounds 
	Rect bounds = args.Bounds;
	//Get the page number on which the deselected free text is 
	int pageNumber = args.PageNumber;
	//Get the text of the free text annotation 
	string text = args.Text;
	//Get the text color 
	Color textColor = args.TextColor;
	//Get the text size 
	float textSize = args.FontSize;
}

{% endhighlight %}
{% endtabs %}