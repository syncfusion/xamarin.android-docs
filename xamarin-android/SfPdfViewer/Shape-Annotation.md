---
layout: post
title:  Add & modify shapes using PDF viewer Xamarin.Android | Syncfusion
description: PDF viewer Xamarin.Android allows user to add, move and delete shapes such as line, rectangle & ellipse PDF document
platform: Xamarin.Android
control: SfPdfViewer
documentation: ug
---

# Working with shape annotations

PDF viewer allows you to include shape annotations in a PDF document and provides options to modify or remove the existing shape annotations. The supported shape annotations are:

1. Rectangle 
2. Circle
3. Line
4. Arrow

In all of the code snippets that follow `Rectangle` shape annotation is used for illustration purpose. 

## Adding shape annotations

### Enabling shape annotation mode

Set the `AnnotationMode` property of the PDF viewer to `Rectangle`. After the annotation mode is set to any of the shapes, the zooming, panning, and scrolling will be disabled and the shapes can be drawn only on the currently visible pages. Refer to the following code.

In all the code snippets, the term ApplicationContext represents the `ApplicationContext` property of the `MainActivity`.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer(ApplicationContext);
pdfViewer.AnnotationMode = AnnotationMode.Rectangle;

{% endhighlight %}
{% endtabs %}

### Disabling shape annotation mode

Use the following code to reset the annotation mode to None. When the annotation mode is reset, the zooming, panning, and scrolling will be enabled again.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer(ApplicationContext);
pdfViewer.AnnotationMode = AnnotationMode.None;

{% endhighlight %}
{% endtabs %}

### Detecting the inclusion of shape annotations

The event `ShapeAnnotationAdded` will be raised when a shape annotation is added to the PDF.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer(ApplicationContext);
pdfViewer.ShapeAnnotationAdded += PdfViewer_ShapeAnnotationAdded;

{% endhighlight %}
{% endtabs %}

## Detecting tap on shape annotations

Tapping a shape annotation selects it or deselects it if it is already selected. The event ShapeAnnotationTapped is raised when a shape is tapped. 

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer(ApplicationContext);
pdfViewer.ShapeAnnotationTapped += PdfViewer_ShapeAnnotationTapped;

{% endhighlight %}
{% endtabs %}



## Selecting shape annotations

You can select a shape annotation by tapping it. When a shape is selected, the `ShapeAnnotationSelected` event will be raised. The properties of the selected shape can be obtained from the `args` parameter of the event handler. 

{% tabs %}
{% highlight c# %}

private void PdfViewer_ShapeAnnotationSelected(object sender, ShapeAnnotationSelectedEventArgs args)
{
    //Get the type of the annotation. Here it is rectangle because the AnnotationMode was set to Rectangle
    AnnotationMode annotationMode = args.AnnotationType;
            
    //Get the bounds of the rectangle
    Rect bounds = args.Bounds;

    //Get the page number in which the annotations are present
    int pageNumber = args.PageNumber;

}


{% endhighlight %}
{% endtabs %}

## Deselecting shape annotations

You can deselect a selected shape annotation by tapping on it or somewhere else on the PDF page. Deselection can be detected using the `ShapeAnnotationDeselected` event.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer(ApplicationContext);
pdfViewer.ShapeAnnotationDeselected += PdfViewer_ShapeAnnotationDeselected;

{% endhighlight %}
{% endtabs %}

The following code shows how to retrieve the properties of the deselected shape annotation.

{% tabs %}
{% highlight c# %}

private void PdfViewer_ShapeAnnotationDeselected(object sender, ShapeAnnotationDeselectedEventArgs args)
{ 
   //Which type of annotation is deselected e.g Rectangle, Circle, FreeText, Ink etc.,
   AnnotationMode annotationType = args.AnnotationType;
   
   //Retrieves the bounds of the deselected annotation.
   Rect bounds = args.Bounds;

   //Retrieves the page number where the deselected annotation resides.
   int page = args.PageNumber;
}

{% endhighlight %}
{% endtabs %}

## Customizing the appearance of shape annotations

You can customize the values of stroke color, opacity, and thickness of all shape annotations to be added. This will not affect the already added shape annotations. The appearance of a selected free text can also be modified.

### Setting the default stroke color

You can set the default stroke color of the shape annotations by using the `SfPdfViewer.AnnotationSettings.Rectangle.Settings.StrokeColor` property. Refer to the following code.
 
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer(ApplicationContext);
pdfViewer.AnnotationSettings.Rectangle.Settings.StrokeColor = Color.Red;

{% endhighlight %}

### Setting the default opacity value

You can set the default opacity of the shape annotations by using the `SfPdfViewer.AnnotationSettings.Rectangle.Settings.Opacity` property. Opacity value ranges from 0 to 1. Refer to the following code example.

{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer(ApplicationContext);
pdfViewer.AnnotationSettings.Rectangle.Settings.Opacity = 0.5f; 

{% endhighlight %}

### Setting the default thickness

You can set the thickness of the shape annotations by using the `SfPdfViewer.AnnotationSettings.Rectangle.Settings.Thickness` property. Refer to the following code example.

{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer(ApplicationContext);
pdfViewer.AnnotationSettings.Rectangle.Settings.Thickness = 5;

{% endhighlight %}

### Changing the properties of a selected shape

You can change the properties of the selected annotation by casting the `sender` parameter of the `ShapeAnnotationSelected` event handler to `ShapeAnnotation` and modifying its properties. The following code shows how to change the properties.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer(ApplicationContext);
pdfViewer.ShapeAnnotationSelected += PdfViewer_ShapeAnnotationSelected;

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

private void PdfViewer_ShapeAnnotationSelected(object sender, ShapeAnnotationSelectedEventArgs args)
{
	//Get the type of the annotation e.g Rectangle, Circle, FreeText, Ink etc.,
    AnnotationMode annotationMode = args.AnnotationType;

	//Cast the sender object as shape annotation.
	ShapeAnnotation selectedShapeAnnotation = sender as ShapeAnnotation;

	//Set the stroke color of the selected annotation using shape annotation settings.
	selectedShapeAnnotation.Settings.StrokeColor = Color.Blue;

	//Set the opacity of the selected annotation using shape annotation settings.
	selectedShapeAnnotation.Settings.Opacity = 0.3f;

	//Set the thickness of the selected annotation using shape annotation settings.
	selectedShapeAnnotation.Settings.Thickness = 3;
}

{% endhighlight %}
{% endtabs %}

## Moving or resizing shape annotations

Tap and drag the annotation to move it. It can be resized by selecting it and dragging the bubbles at the corners.  

### Detecting the move or resizing of a shape

The event `AnnotationMovedOrResized` will be raised when you move or resize the selected annotation.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer(ApplicationContext);
pdfViewer.AnnotationMovedOrResized += PdfViewer_AnnotationMovedOrResized;

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

private void PdfViewer_AnnotationMovedOrResized(object sender, AnnotationMovedOrResizedEventArgs args) 
{
	 //Determine whether the moved or resized annotation is a shape or some other annotation. 
	 
	 if(sender as ShapeAnnotation == null)
	 {
		//The annotation is not a shape
	 }
	 else
	 {
		//The annotation is a shape
	 }
	 
     //Retrieve the old bounds of the annotation
     Rect oldBounds = args.OldBounds;

     //Retrieve the new bounds of the annotation
     Rect newBounds = args.NewBounds;
}

{% endhighlight %}
{% endtabs %}

## Deleting shape annotations

The PDF viewer can remove a selected annotation or all the annotations in the PDF document.

### Removing all annotations

All annotations from the PDF, irrespective of their types can be removed using the `ClearAllAnnotations` method. 

{% tabs %}
{% highlight c# %}

pdfViewer.ClearAllAnnotations();

{% endhighlight %}
{% endtabs %}

### Removing a selected shape annotation.

The following code snippet illustrates removing a selected annotation from the PDF document.

{% tabs %}
{% highlight c# %}

ShapeAnnotation selectedShapeAnnotation;

private void PdfViewer_ShapeAnnotationSelected(object sender, ShapeAnnotationSelectedEventArgs args)
{
	//Cast the sender object as Shape annotation.
	selectedShapeAnnotation = sender as ShapeAnnotation;
}

private void deleteShapeAnnotationButton_Clicked(object sender, EventArgs e)
{
	//Delete the selected shape annotation
	pdfViewer.RemoveAnnotation(selectedShapeAnnotation);
}

{% endhighlight %}
{% endtabs %}

### Detecting the removal of a shape

The event `ShapeAnnotationRemoved` will be raised when a shape annotation is removed from the PDF.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer(ApplicationContext);
pdfViewer.ShapeAnnotationRemoved += PdfViewer_ShapeAnnotationRemoved;

{% endhighlight %}
{% endtabs %}

The properties of the removed shape can be retrieved from the `args` parameter of the event handler.  

{% tabs %}
{% highlight c# %}

private void PdfViewer_ShapeAnnotationRemoved(object sender, ShapeAnnotationRemovedEventArgs args)
{
	//Get the type of the annotation. Here it is rectangle because the AnnotationMode was set to rectangle
	AnnotationMode annotationMode = args.AnnotationType;

	//Get the bounds of the rectangle
	Rect bounds = args.Bounds;

	//Get the data points of the shape
	List<Point> dataPoints = args.DataPoints;

	//Get the opacity value
	float opacity = args.Opacity;

	//Get the page number in which the annotations are present
	int pageNumber = args.PageNumber;

	//Get the position of the shape within the page
	Point position = args.Position;

	//Get the stroke color of the shape 
	Color strokeColor = args.StrokeColor;

	//Get the thickness of the shape
	float thickness = args.Thickness;

}

{% endhighlight %}
{% endtabs %}