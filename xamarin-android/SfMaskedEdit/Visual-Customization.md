---
layout: post
title: Visual appearence customization of SfMaskedEdit control for Xamarin.Android Platform
description: Learn how to customize the visual appearence of SfMaskedEdit control
platform: Xamarin.Android
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit

---


# Visual Customization:

The appearance of SfMaskedEdit can be customized using the following properties:

## BorderColor

Sets the custom border color to SfMaskedEdit.

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit(this);
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.BorderColor = Color.Green;
{% endhighlight %}
{% endtabs %}

![](SfMaskedEditImages/Visual_BorderColor.png)

## ErrorBorderColor

Sets the custom error border color to SfMaskedEdit. Error border color indicates the color to be used when the validation fails for your input with respect to the mask used. 

> Validation triggers based on `ValidationMode` property.

Refer this [link](Validation#validation-mode) to know more about the `ValidationMode` property of SfMaskedEdit control.

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit(this);
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.ErrorBorderColor = Color.Yellow;
{% endhighlight %}
{% endtabs %}

![](SfMaskedEditImages/Visual_ErrorBorderColor.png)

 
## Setting Appearance of Text

You can customize the display text appearance of SfMaskedEdit control using the following properties:

* `SetTextColor`: Changes the color of the text.
* `TextAlignment`: Changes the horizontal alignment of the text.
* `Typeface`: Changes the font family of the text and sets font attributes(bold/italic/none) of the text.
* `TextSize`: Sets font size of the text.

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit(this);
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.SetTextColor(Color.Brown);
maskedEdit.TextAlignment = TextAlignment.Center;
maskedEdit.Typeface = Typeface.Create("Arial", TypefaceStyle.Bold);
maskedEdit.TextSize = 20;
{% endhighlight %}
{% endtabs %}

![](SfMaskedEditImages/Visual_TextColor.png)

This demo can be downloaded from this [link](http://files2.syncfusion.com/Xamarin.Android/Samples/MaskedEdit_VisualCustomize.zip).
