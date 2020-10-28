---
layout: post
title: Formatting value of Value property of SfMaskedEdit control for Xamarin.Android platform
description: Learn how to format the characters in the Value property of SfMaskedEdit control
platform: Xamarin.Android
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit

---


# Formatting Value

SfMaskedEdit allows you to format the characters in the `Value` property in a mask scenario (when the Mask property is set). By default, the Value property holds your input characters, prompt characters and the literals defined in the mask. You can modify this and allow the Value property to hold the characters without prompt and literals by setting the ValueMaskFormat property of the control. The Value in the SfMaskedEdit is formatted by any one of the following formatting enum values:

* ExcludePromptAndLiterals
* IncludePrompt
* IncludeLiterals
* IncludePromptAndLiterals

## ExcludePromptAndLiterals

Value contains only the typed characters, the prompt characters and literals are excluded.

## IncludePrompt

Value contains the typed characters and prompt characters, literals are excluded.

## IncludeLiterals

Value contains the typed characters and literals, prompt characters are excluded.

## IncludePromptAndLiterals

Value contains typed characters, prompt characters, and literals.

{% tabs %}
{% highlight c# %}
TextView label1;
TextView label2;
TextView label3;
TextView label4;
SfMaskedEdit maskedEdit1;
SfMaskedEdit maskedEdit2;
SfMaskedEdit maskedEdit3;
SfMaskedEdit maskedEdit4;

maskedEdit1 = new SfMaskedEdit(this);
maskedEdit1.MaskType = MaskType.Text;
maskedEdit1.Mask = "00/00/0000";
maskedEdit1.ValueMaskFormat = MaskFormat.ExcludePromptAndLiterals;
maskedEdit1.ValueChanged += MaskedEdit1_ValueChanged;
label1 = new TextView(this);
linearLayout.AddView(label1);
linearLayout.AddView(maskedEdit1);

maskedEdit2 = new SfMaskedEdit(this);
maskedEdit2.MaskType = MaskType.Text;
maskedEdit2.Mask = "00/00/0000";
maskedEdit2.ValueMaskFormat = MaskFormat.IncludeLiterals;
maskedEdit2.ValueChanged += MaskedEdit2_ValueChanged;
label2 = new TextView(this);
linearLayout.AddView(label2);
linearLayout.AddView(maskedEdit2);

maskedEdit3 = new SfMaskedEdit(this);
maskedEdit3.MaskType = MaskType.Text;
maskedEdit3.Mask = "00/00/0000";
maskedEdit3.ValueMaskFormat = MaskFormat.IncludePrompt;
maskedEdit3.ValueChanged += MaskedEdit3_ValueChanged;
label3 = new TextView(this);
linearLayout.AddView(label3);
linearLayout.AddView(maskedEdit3);

maskedEdit4 = new SfMaskedEdit(this);
maskedEdit4.MaskType = MaskType.Text;
maskedEdit4.Mask = "00/00/0000";
maskedEdit4.ValueMaskFormat = MaskFormat.IncludePromptAndLiterals;
maskedEdit4.ValueChanged += MaskedEdit4_ValueChanged;
label4 = new TextView(this);
linearLayout.AddView(maskedEdit4);
linearLayout.AddView(label4); 

private void MaskedEdit1_ValueChanged(object sender, Syncfusion.XForms.MaskedEdit.ValueChangedEventArgs e)
{
    label1.Text = e.Value as string;
}

private void MaskedEdit2_ValueChanged(object sender, Syncfusion.XForms.MaskedEdit.ValueChangedEventArgs e)
{
    label2.Text = e.Value as string;
}

private void MaskedEdit3_ValueChanged(object sender, Syncfusion.XForms.MaskedEdit.ValueChangedEventArgs e)
{
    label3.Text = e.Value as string;
}

private void MaskedEdit4_ValueChanged(object sender, Syncfusion.XForms.MaskedEdit.ValueChangedEventArgs e)
{
    label4.Text = e.Value as string;
}
{% endhighlight %}
{% endtabs %}

Refer this [link](Events#valuechanged-event) to know more about the ‘ValueChanged’ event of SfMaskedEdit control.

![](SfMaskedEditImages/FormattingValue.png)

This demo can be downloaded from this [link](http://files2.syncfusion.com/Xamarin.Android/Samples/MaskedEdit_FormattingValue.zip).
