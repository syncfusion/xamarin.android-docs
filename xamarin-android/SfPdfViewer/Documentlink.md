---
layout: post
title:  Document link in PDF viewer Xamarin.Android | Syncfusion
description: Document Link Annotation or Table of content support in PDF viewer Xamarin.Android allows the user to navigate to specific destination within PDF document.
platform: Xamarin.Android
control: SfPdfViewer
documentation: ug
---

# Working with Document Link Annotation (Table of content)

The PDF viewer navigates to a specific destination within the PDF document.


## How to disable document link navigation in PDF document using PDF viewer control?

Set the “EnableDocumentLinkAnnotation” property to false to disable the document link navigation in PDF viewer. 

{% tabs %}
{% highlight c# %}

pdfViewerControl.EnableDocumentLinkAnnotation =false;

{% endhighlight %}
{% endtabs %}

N>By default, the EnableDocumentLinkAnnotation property is set to true.
