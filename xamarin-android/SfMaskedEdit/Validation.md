---
layout: post
title: Input validation in SfMaskedEdit control for Xamarin.Android platform
description: Learn how and when to validate the input characters with the given Mask of SfMaskedEdit control.
platform: Xamarin.Android
control: SfMaskedEdit
documentation: ug 
keywords: mask, SfMaskedEdit, maskededit

---



# Validation

## Validation Mode

Input validation happens based on the value of the `ValidationMode` property. The enum values of this property are:

* KeyPress
* LostFocus

The default value for validation mode is `LostFocus`.

{% tabs %}
{% highlight c# %}
SfMaskedEdit maskedEdit = new SfMaskedEdit(this);
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.ValidationMode = InputValidationMode.KeyPress;
{% endhighlight %}
{% endtabs %}

When the ValidationMode is LostFocus, the validation takes place when the control lost its focus. For KeyPress, the validation triggers for each key press.

## HasError

This read only property is used to check whether the validation succeeds or not. It returns true once validation succeeds or else returns false. The following code example shows the usage of `HasError` property.

{% tabs %}
{% highlight c# %}
AlertDialog.Builder dialog;

dialog= new AlertDialog.Builder(this);
SfMaskedEdit maskedEdit = new SfMaskedEdit(this);
maskedEdit.MaskType = MaskType.Text;
maskedEdit.Mask = "00/00/0000";
maskedEdit.ValidationMode = InputValidationMode.LostFocus;
maskedEdit.ValueChanged += MaskedEdit_ValueChanged;


private void MaskedEdit_ValueChanged(object sender, ValueChangedEventArgs e)
{
    SfMaskedEdit maskedEdit = sender as SfMaskedEdit;
    if(maskedEdit.HasError)
    {
        dialog.SetMessage("Please enter valid details");             
        dialog.SetTitle("Status");
        dialog.SetPositiveButton("OK", (object sender1, DialogClickEventArgs e1)=>{});
        dialog.Create().Show();
        dialog.SetCancelable(true);   
    }
}
{% endhighlight %}
{% endtabs %}


Refer this [link](Events#valuechanged-event) to know more about the `ValueChanged` event of SfMaskedEdit control.

![](SfMaskedEditImages/Validation.png)

This demo can be downloaded from this [link](http://files2.syncfusion.com/Xamarin.Android/Samples/MaskedEdit_Validation.zip).
