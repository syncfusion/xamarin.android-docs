---
layout: post
title: Using Mask Characters as Literals in SfMaskedEdit control for Xamarin.Android platform
description: Learn how to use mask characters as literals in SfMaskedEdit control for Xamarin.Forms platform
platform: Xamarin.Android
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit

---


# Using Mask Characters as Literals

To use mask character as a literal, precede the mask character with a backslash (\\). For example, to display the dollar sign ($), then set the mask as follows:

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit(this);
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = @"\$ 0000";
{% endhighlight %}
{% endtabs %}

This will produce a mask that displays a dollar sign ($) followed by the prompt characters for entering numbers.

![](SfMaskedEditImages/MaskAsLiterals.png)

This demo can be downloaded from this [link](http://files2.syncfusion.com/Xamarin.Android/Samples/MaskedEdit_UsingMaskCharactersAsLiterals.zip).
