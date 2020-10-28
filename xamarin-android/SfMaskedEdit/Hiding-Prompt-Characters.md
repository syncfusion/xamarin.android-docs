---
layout: post
title: Hiding propmpt characters of SfMaskedEdit control for Xamarin.Android paltform
description: Learn how to hide the prompt characters of SfMasedEdit while control loses focus
platform: Xamarin.Android
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit

---


# Hiding Prompt Characters

When the `HidePromptOnLeave` property is set to true, prompt characters are ignored when control loses focus. Again, the prompt characters are restored when the control is focused.

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit(this);
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.HidePromptOnLeave = true;
{% endhighlight %}
{% endtabs %}

![](SfMaskedEditImages/HPL.png)

This demo can be downloaded from this [link](http://files2.syncfusion.com/Xamarin.Android/Samples/MaskedEdit_HidingPrompt.zip).
