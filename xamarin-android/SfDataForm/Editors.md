---
layout: post
title: Layout | SfDataForm | Xamarin.Android | Syncfusion
description: Different editors and its customization  in SfDataForm.
platform: Xamarin.Android
control: SfDataForm
documentation: UG
---

# Editors

The data form supports several built-in editors as follows:

<table>
<tr>
<th>Editor name</th>
<th>Editor class</th>
<th>Supported Data Type/Attribute</th>
<th>Input control loaded</th>
</tr>
<tr>
<td>
Text
</td>
<td>
{{'[DataFormTextEditor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.DataFormTextEditor.html)'| markdownify }}
</td>
<td>
The String type property and any other type apart from the below specified cases.
</td>
<td>
{{'[EditText](https://developer.android.com/reference/android/widget/EditText)'| markdownify }}
</td>
</tr>
<tr>
<td>
MultilineText
</td>
<td>
{{'[DataFormMultiLineTextEditor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.DataFormMultiLineTextEditor.html)'| markdownify }}
</td>
<td>
The String type property with multi line text.
[DataType(DataType.Multiline)] 
</td>
<td>
{{'[EditText](https://developer.android.com/reference/android/widget/EditText)'| markdownify }}
</td>
</tr>
<tr>
<td>
Numeric
</td>
<td>
{{'[DataFormNumericEditor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.DataFormNumericEditor.html)'| markdownify }}
</td>
<td>
The property of Int, Double, Float, Decimal, Long types and also its nullable property.
</td>
<td>
{{'[SfNumericTextBox](https://help.syncfusion.com/xamarin-android/introduction/overview)'| markdownify }}
</td>
</tr>
<tr>
<td>
Percent
</td>
<td>
{{'[DataFormNumericEditor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.DataFormNumericEditor.html)'| markdownify }}
</td>
<td>
The property of Int, Double, Float, Decimal, Long types and also its nullable property with [DataType(“Percent”)] attribute.
</td>
<td>
{{'[SfNumericTextBox](https://help.syncfusion.com/xamarin-android/introduction/overview)'| markdownify }}
</td>
</tr>
<tr>
<td>
Currency
</td>
<td>
{{'[DataFormNumericEditor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.DataFormNumericEditor.html)'| markdownify }}
</td>
<td>
The property of Int, Double, Float, Decimal, Long types and also its nullable property with [DataType(DataType.Currency)] attribute.
</td>
<td>
{{'[SfNumericTextBox](https://help.syncfusion.com/xamarin-android/introduction/overview)'| markdownify }}
</td>
</tr>
<tr>
<td>
Date
</td>
<td>
{{'[DataFormDateEditor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.DataFormDateEditor.html)'| markdownify }}
</td>
<td>
DateTime type property and the property with [DataType(DataType.Date)] and [DataType(DataType.DateTime)] attributes.
</td>
<td>
{{'[SfDatePicker](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.SfDatePicker.html)'| markdownify }}
</td>
</tr>
<tr>
<td>
Time
</td>
<td>
{{'[DataFormTimeEditor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.DataFormTimeEditor.html)'| markdownify }}
</td>
<td>
The property with [DataType(DataType.Time)] attribute.
</td>
<td>
{{'[SfTimePicker](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.SfTimePicker.html)'| markdownify }}
</td>
</tr>
<tr>
<td>
NumericUpDown
</td>
<td>
{{'[DataFormNumericUpDownEditor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.DataFormNumericUpDownEditor.html)'| markdownify }}
</td>
<td>
Int or Double type property.
</td>
<td>
{{'[SfNumericUpDown](https://help.syncfusion.com/xamarin-android/sfnumericupdown/overview)'| markdownify }}
</td>
</tr>
<tr>
<td>
Segment
</td>
<td>
{{'[DataFormSegmentedEditor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.DataFormSegmentedEditor.html)'| markdownify }}
</td>
<td>
Enum type property.
</td>
<td>
{{'[RadioGroup](https://developer.android.com/reference/android/widget/RadioGroup)'| markdownify }}
</td>
</tr>
<tr>
<td>
Bool
</td>
<td>
{{'[DataFormCheckBoxEditor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.DataFormCheckBoxEditor.html)'| markdownify }}
</td>
<td>
Bool type property.
</td>
<td>
{{'[CheckBox](https://developer.android.com/reference/android/widget/CheckBox)'| markdownify }}
</td>
</tr>
<tr>
<td>
Switch
</td>
<td>
{{'[DataFormSwitchEditor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.DataFormSwitchEditor.html)'| markdownify }}
</td>
<td>
Bool type property.
</td>
<td>
{{'[Switch](https://developer.android.com/reference/android/widget/Switch)'| markdownify }}
</td>
</tr>
<tr>
<td>
Picker
</td>
<td>
{{'[DataFormPickerEditor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.DataFormPickerEditor.html)'| markdownify }}
</td>
<td>
Enum and List type property. 
[EnumDataTypeAttribute]
</td>
<td>
{{'[SfPicker](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.SfPicker.html)'| markdownify }}
</td>
</tr>
<tr>
<td>
DropDown
</td>
<td>
{{'[DataFormDropDownEditor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.DataFormDropDownEditor.html)'| markdownify }}
</td>
<td>
Enum and List type property.
[EnumDataTypeAttribute]
</td>
<td>
{{'[Spinner](https://developer.xamarin.com/guides/android/user_interface/spinner/)'| markdownify }}
</td>
</tr>
<tr>
<td>
Password
</td>
<td>
{{'[DataFormPasswordEditor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.DataFormPasswordEditor.html)'| markdownify }}
</td>
<td>
The String type property and property with 
[DataType(DataType.Password)] attribute.
</td>
<td>
{{'[EditText](https://developer.android.com/reference/android/widget/EditText)'| markdownify }}
</td>
</tr>
</table>

## Text editor

In the text editor, the [EditText](https://developer.xamarin.com/guides/android/user_interface/form_elements/edit_text/) is loaded.

### Loading upper case keyboard in EditText

You can load upper case letters keyboard by setting the [InputType](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormTextItem.html) as `TextFlagCapCharacters`.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;
private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{    
    if (e.DataFormItem != null && e.DataFormItem.Name == "Name")
    {
        (e.DataFormItem as DataFormTextItem).InputType = Android.Text.InputTypes.TextFlagCapCharacters;
    }
}
{% endhighlight %}
{% endtabs %}

## Multiline Text editor

In the `MultilineText` editor, the [EditText](https://developer.android.com/reference/android/widget/EditText) is loaded.

And `MultilineText` editor height will auto expand/reduce based on the line wraps in editor , which allowing text to be readable without scrolling the editor.

{% tabs %}
{% highlight c# %}

[DataType(DataType.MultilineText)]
public String Address { get; set; }

{% endhighlight %}
{% endtabs %}

![Loading multi line text editor in Xamarin.Android DataForm](SfDataForm_images/Editors_MultiLine.png)

## Numeric editor

In the numeric editor, the [SfNumericTextBox](https://help.syncfusion.com/xamarin-android/introduction/overview) is loaded.

### Change maximum NumberDecimalDigits in the numeric editor

In the `SfNumericTextBox`, two decimal digits will be displayed by default. You can change the number of decimal digits being displayed by setting the [MaximumNumberDecimalDigits](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormNumericItemBase.html#Syncfusion_Android_DataForm_DataFormNumericItemBase_MaximumNumberDecimalDigits) property in the [DataFormNumericItem](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormNumericItem.html).

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;
private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Amount")
    {
        (e.DataFormItem as DataFormNumericItem).MaximumNumberDecimalDigits = 3;
    }
}
{% endhighlight %}
{% endtabs %}

## Date editor

In the date editor, the [SfDatePicker](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.SfDatePicker.html) will be loaded.

### Setting null value in date editor

In `SfDatePicker`, the default date value (1/01/0001) is displayed by default. You can also set the null value by adding nullable `DateTime` data type for the date picker property in data form, which allows you to set the null value and display the empty value in date editor.

{% tabs %}
{% highlight c# %}
[DataType(DataType.Date)]
[Display(Name ="Birth Date")]
public DateTime? BirthDate { get; set; }

{% endhighlight %}
{% endtabs %}

![Setting nullable date to data form date item in Xamarin.Android DataForm](SfDataForm_images/DateTime_Nullable.png)

### Customizing format in date editor

In the `SfDatePicker`, short date will be shown by default. You can change the applied format by setting the [Format](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormDateItem.html#Syncfusion_Android_DataForm_DataFormDateItem_Format) property in [DataFormDateItem](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormDateItem.html).

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{   

    if (e.DataFormItem != null && e.DataFormItem.Name == "Date")
    {
        (e.DataFormItem as DataFormDateItem).Format = "ddd, MMM d, yyyy";
    }
}
{% endhighlight %}
{% endtabs %}

![Setting DateFormat to data form date item in Xamarin.Android DataForm](SfDataForm_images/DateEditorFormat.png)

### Setting MaximumDate and MinimumDate in date editor

You can customize the maximum and minimum allowable dates in the `SfDatePicker` by setting [MaximumDate](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormDateItem.html#Syncfusion_Android_DataForm_DataFormDateItem_MaximumDate) and [MinimumDate](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormDateItem.html#Syncfusion_Android_DataForm_DataFormDateItem_MinimumDate) in the [DataFormDateItem](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormDateItem.html) respectively.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Date")
    {
        (e.DataFormItem as DataFormDateItem).MinimumDate = new DateTime(2017, 5, 5);
        (e.DataFormItem as DataFormDateItem).MaximumDate = new DateTime(2017, 9, 2);
    }
}

{% endhighlight %}
{% endtabs %}

![Setting maximum date for data form date item in Xamarin.Android DataForm](SfDataForm_images/DateEditorMax.png)

## Time editor

In the time editor, the [SfTimePicker](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.SfTimePicker.html) will be loaded.

**Setting null value in time editor**

In `SfTimePicker`, the default time value (12:00 AM) is displayed by default. You can also set the null value by adding nullable `DateTime` data type for the time picker property in data form, which allows you to set the null value and display the empty value in time editor. 

{% tabs %}
{% highlight c# %}

[DataType(DataType.Time)]
[Display(Name = "Birth Time")]
public DateTime? BirthTime { get; set; }

{% endhighlight %}
{% endtabs %}

![Setting nullable time to data form item in Xamarin.Android DataForm](SfDataForm_images/Time_Nullable.png)

**Customizing format in time editor**

In the `SfTimePicker`, short time will be shown by default. You can change the applied format by setting the [Format](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormTimeItem.html#Syncfusion_Android_DataForm_DataFormTimeItem_Format) property in [DataFormTimeItem](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormTimeItem.html).

{% tabs %}
{% highlight c# %}

dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "BirthTime")
        (e.DataFormItem as DataFormTimeItem).Format = "HH:mm";
} 

{% endhighlight %}
{% endtabs %}

![Setting time format to data form time item in Xamarin.Android DataForm](SfDataForm_images/Editors_TimeFormat.png)

## CheckBox editor

In `CheckBox` editor, the [CheckBox]( https://developer.android.com/reference/android/widget/CheckBox) control is loaded.By default, for `bool` data type property, `CheckBox` editor will be loaded in data form.

{% tabs %}
{% highlight c# %}

[Display(Name = "Is Billable")]
 public bool IsBillable { get; set; } = true;

[Display(Name = "Registered Member")]
public bool RegisteredMember { get; set; }

{% endhighlight %}
{% endtabs %}

![Loading check box editor in Xamarin.Android DataForm](SfDataForm_images/CheckBoxEditor.png)

## Switch Editor

In switch editor, [Switch]( https://developer.android.com/reference/android/widget/Switch) is loaded, and DataForm `Switch` editor supports bool data type property.

To add `Switch` editor in DataForm, register the editor as `Switch` for the required property using the [RegisterEditor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.SfDataForm.html#Syncfusion_Android_DataForm_SfDataForm_RegisterEditor_System_String_System_String_) method.

{% tabs %}
{% highlight c# %}

dataForm.RegisterEditor("CellularData", "Switch");
dataForm.RegisterEditor("AirplaneMode", "Switch");

[Display(Name ="Cellular Data")]
public bool CellularData { get; set; } = true;

[Display(Name = "Airplane Mode")]
public bool AirplaneMode { get; set; }
 
{% endhighlight %}
{% endtabs %}

## Drop down editor

In the drop down editor, the [Spinner](https://developer.xamarin.com/guides/android/user_interface/spinner/) will be loaded.

### Customizing ItemsSource of spinner

By default, the `ItemsSource` for spinner is auto-generated for enum types and collection type properties. For other types, you can set the `ItemsSource` by using the [SourceProvider](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.SfDataForm.html#Syncfusion_Android_DataForm_SfDataForm_SourceProvider).

#### Using SourceProvider

{% tabs %}
{% highlight c# %}
private string _ItemName;
public string ItemName
{
    get
    {
        return _ItemName;
    }
    set
    {
        _ItemName = value;
    }
}
public class SourceProviderExt : SourceProvider
{
    public override IList GetSource(string sourceName)
    {
        var list = new List<string>();
        if (sourceName == "ItemName")
        {
            list.Add("Item1");
            list.Add("Item2");
            list.Add("Item3");
        }
        return list;
    }
}
dataForm.SourceProvider = new SourceProviderExt();
dataForm.RegisterEditor("ItemName", "DropDown");
{% endhighlight %}
{% endtabs %}

#### Using ItemsSource property

You can also set the ItemsSource for drop down editor by using the [ItemsSource](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormDropDownItem.html#Syncfusion_Android_DataForm_DataFormDropDownItem_ItemsSource) property in the `DataFormDropDownItem`.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Name")
    {
        var list = new List<string>();
        list.Add("Home");
        list.Add("Food");
        list.Add("Utilities");
        list.Add("Education");
        (e.DataFormItem as DataFormDropDownItem).ItemsSource = list;
    }
}
{% endhighlight %}
{% endtabs %}

![Setting ItemsSource for drop down editor items in Xamarin.Android DataForm](SfDataForm_images/DropDownItems.png)

You can also change the `ItemsSource` at runtime.

{% tabs %}
{% highlight c# %}
private void Button_Click(object sender, EventArgs e)
{
    var dataFormItem = dataForm.ItemManager.DataFormItems["Name"];
    if (dataFormItem.Name == "Name")
    {
        var list = new List<string>();
        list.Add("Home");
        list.Add("Food");
        list.Add("Utilities");
        list.Add("Education");
        (dataFormItem as DataFormDropDownItem).ItemsSource = list;
    }
}
{% endhighlight %}
{% endtabs %}

## Picker editor

In the picker editor, the [SfPicker](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.SfPicker.html) will be loaded.

### Changing title in the SfPicker

You can show some text in the `SfPicker` popup by using the [Title](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormPickerItem.html#Syncfusion_Android_DataForm_DataFormPickerItem_Title) property in the [DataFormPickerItem](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormPickerItem.html).

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Name")
    {
        (e.DataFormItem as DataFormPickerItem).Title = "Expense Category";
    }
}
{% endhighlight %}
{% endtabs %}

![Changing title for data form picker item in Xamarin.Android DataForm](SfDataForm_images/PickerTitle.png)

### Customizing ItemsSource of SfPicker

By default, the `ItemsSource` for picker is auto-generated for enum type and collection type properties. For other types, you can set the `ItemsSource` by using [SourceProvider](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.SfDataForm.html#Syncfusion_Android_DataForm_SfDataForm_SourceProvider).

### Using SourceProvider

{% tabs %}
{% highlight c# %}
private string _ItemName;
public string ItemName
{
    get
    {
        return _ItemName;
    }
    set
    {
        _ItemName = value;
    }
}
public class SourceProviderExt : SourceProvider
{
    public override IList GetSource(string sourceName)
    {
        var list = new List<string>();
        if (sourceName == "ItemName")
        {
            list.Add("Item1");
            list.Add("Item2");
            list.Add("Item3");
        }
        return list;
    }
}
dataForm.SourceProvider = new SourceProviderExt();
dataForm.RegisterEditor("ItemName", "Picker");
{% endhighlight %}
{% endtabs %}

### Using event

You can also set `ItemsSource` for picker editor by using the [ItemsSource](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormPickerItem.html#Syncfusion_Android_DataForm_DataFormPickerItem_ItemsSource) property in the [DataFormPickerItem](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormPickerItem.html).

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Name")
    {
        var list = new List<string>();
        list.Add("Home");
        list.Add("Food");
        list.Add("Utilities");
        list.Add("Education");
        (e.DataFormItem as DataFormPickerItem).ItemsSource = list;
    }
}
{% endhighlight %}
{% endtabs %}

### Changing ItemsSource of picker at run time

You can also change the `ItemsSource` at runtime.

{% tabs %}
{% highlight c# %}
private void Button_Click(object sender, EventArgs e)
{
    var dataFormItem = dataForm.ItemManager.DataFormItems["Name"];
    if (dataFormItem.Name == "Name")
    {
        var list = new List<string>();
        list.Add("Home");
        list.Add("Food");
        list.Add("Utilities");
        list.Add("Education");
        (dataFormItem as DataFormPickerItem).ItemsSource = list;
    }
}
{% endhighlight %}
{% endtabs %}

### Loading complex type property values in picker

You can display the complex type property values in picker editor by using the [GetSource](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.SourceProvider.html#Syncfusion_Android_DataForm_SourceProvider_GetSource_System_String_) override method of SourceProvider class, which is used to get source list as complex property values for picker editor and set it to `SourceProvider` property of SfDataForm. You need to use `AutoGeneratingDataFormItem` event to set [DisplayMemberPath](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormPickerItem.html) and [ValueMemberPath](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormPickerItem.html#Syncfusion_Android_DataForm_DataFormPickerItem_ValueMemberPath) property value DataFormPickerItem for complex type property. 

N> Class cannot be directly set as data type for picker editor in this complex type scenario.

{% tabs %}
{% highlight c# %}
dataForm.SourceProvider = new SourceProviderExt();
dataForm.RegisterEditor("City", "Picker");
dataForm.DataObject = new ContactInfo();
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;
 
private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "City")
    {
        (e.DataFormItem as DataFormPickerItem).DisplayMemberPath = "City";
        (e.DataFormItem as DataFormPickerItem).ValueMemberPath = "PostalCode";
    }
} 
 
public class SourceProviderExt : SourceProvider
{
    public override IList GetSource(string sourceName)
    {
        if (sourceName == "City")
        {
            List<Address> details = new List<Address>();
            details.Add(new Address() { City = "Chennai", PostalCode = 1 });
            details.Add(new Address() { City = "Paris", PostalCode = 2 });
            details.Add(new Address() { City = "Vatican", PostalCode = 3 });

            return details;
        }
       return new List<string>();
    }
}

public class ContactInfo
{
    public String FirstName { get; set; } 
    public string City { get; set; }
}

public class Address
{
    public int PostalCode { get; set; }
    public string City { get; set; }
}
{% endhighlight %}
{% endtabs %}

You can download the entire source code of this demo for Xamarin.Forms from here [DataFormPickerEditor](http://www.syncfusion.com/downloads/support/directtrac/general/ze/DataForm_AndroidPicker1618036890.zip)

![Loading complex type property values in picker in Xamarin.Android DataForm](SfDataForm_images/ComplexPropertyPicker.png)

## NumericUpDown editor

In the numeric editor, the [SfNumericUpDown](https://help.syncfusion.com/xamarin-android/sfnumericupdown/overview) will be loaded.

### Changing SpinButtonAlignment in NumericUpDown

By default, up down button will be displayed in right side. You can change its alignment by using the [SpinButtonAlignment](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormNumericUpDownItem.html#Syncfusion_Android_DataForm_DataFormNumericUpDownItem_SpinButtonAlignment) property in the [DataFormNumericUpDownItem](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormNumericUpDownItem.html).

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;
private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Quantity")
        (e.DataFormItem as DataFormNumericUpDownItem).SpinButtonAlignment = SpinButtonAlignment.Both;
}
{% endhighlight %}
{% endtabs %}

![Changing spin button alignment for data form item in Xamarin.Android DataForm](SfDataForm_images/SpinButtonCenter.png)

### Changing step value in numeric up down

You can change the next increment and decrement values by using the [StepValue](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormNumericUpDownItem.html#Syncfusion_Android_DataForm_DataFormNumericUpDownItem_StepValue) property in the [DataFormNumericUpDownItem](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormNumericUpDownItem.html). The default value of step value is 1.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Quantity")
        (e.DataFormItem as DataFormNumericUpDownItem).StepValue = 2;
}
{% endhighlight %}
{% endtabs %}

### Setting Maximum and Minimum value in numeric up down

You can set minimum and maximum values for numeric up down by using [Minimum](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormNumericUpDownItem.html#Syncfusion_Android_DataForm_DataFormNumericUpDownItem_Minimum) and [Maximum](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormNumericUpDownItem.html#Syncfusion_Android_DataForm_DataFormNumericUpDownItem_Maximum) properties values respectively.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Quantity")
    {
        (e.DataFormItem as DataFormNumericUpDownItem).Maximum = 100;
        (e.DataFormItem as DataFormNumericUpDownItem).Minimum = 0;
    }
}
{% endhighlight %}
{% endtabs %}

### Enabling auto reverse in numeric up down

In the `SfNumericUpDown`, once maximum and minimum values reached, the value will be unchanged. You can enable the cyclic behavior by setting the [AutoReverse](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormNumericUpDownItem.html#Syncfusion_Android_DataForm_DataFormNumericUpDownItem_AutoReverse) to `true` in the [DataFormNumericUpDownItem](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormNumericUpDownItem.html).

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Quantity")
    {
        (e.DataFormItem as DataFormNumericUpDownItem).AutoReverse = true;
    }
}
{% endhighlight %}
{% endtabs %}

### Changing CultureInfo in numeric up down and numeric text box

You can change the culture in `SfNumericTextBox` and `SfNumericUpDown` by using the [CultureInfo](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormNumericItemBase.html#Syncfusion_Android_DataForm_DataFormNumericItemBase_CultureInfo) property in the [DataFormNumericItemBase](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormNumericItemBase.html).

#### SfNumericTextBox

{% tabs %}
{% highlight c# %}
private double _discount = 10;
        
[DataType(DataType.Currency)]
public double Discount
{
    get
    {
        return _discount;
    }
    set
    {
        _discount = value;
        RaisePropertyChanged("Discount");
    }
}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Discount")
    {
        (e.DataFormItem as DataFormNumericItem).CultureInfo = new Java.Util.Locale("fr", "FR");
    }
}
{% endhighlight %}
{% endtabs %}

![Setting CultureInfo to data form numeric item in Xamarin.Android DataForm](SfDataForm_images/NumericCulture.png)

#### SfNumericUpDown

{% tabs %}
{% highlight c# %}
dataForm.RegisterEditor("Discount", "NumericUpDown");
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;
private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Discount")
    {
        (e.DataFormItem as DataFormNumericUpDownItem).FormatString = "c";
        (e.DataFormItem as DataFormNumericUpDownItem).CultureInfo = new Java.Util.Locale("fr", "FR");
    }
}
{% endhighlight %}
{% endtabs %}

![Setting CultureInfo to data form numeric up down item in Xamarin.Android DataForm](SfDataForm_images/NumericUpDownCulture.png)

## Password editor

In the password editor, the [EditText](https://developer.xamarin.com/guides/android/user_interface/form_elements/edit_text/) is loaded.

{% tabs %}
{% highlight c# %}
private string password;

[Display(ShortName = "Transaction password", Prompt = "Enter password")]
[DataType(DataType.Password)]
public string Password
{
    get { return this.password; }
    set
    {
        this.password = value;
        RaisePropertyChanged("Password");
        this.RaiseErrorChanged("Password");
    }
}
{% endhighlight %}
{% endtabs %}

![Loading password editor in Xamarin.Android DataForm](SfDataForm_images/DataFormPasswordEditor.png)
