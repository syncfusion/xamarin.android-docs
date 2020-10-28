---
layout: post
title: Editing | SfDataForm | Xamarin.Android | Syncfusion
description: Editing in SfDataForm for Xamarin.Android
platform: xamarin.Android
control: SfDataForm
documentation: ug
---

# Editing 
The data form supports several built-in editors. 

## Supported editors and associated DataFormItem

<table>
<tr>
<th>Editor name</th>
<th>Editor class</th>
<th>Data Type/Attribute</th>
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
The String type property and any other type apart from the following specified cases.
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
The DateTime type property and the property with [DataType(DataType.Date)] and [DataType(DataType.DateTime)] attributes.
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

## Changing editor for type

By default, the editors will be loaded based on the previous table. To change the editor for any type, use the [RegisterEditor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.SfDataForm.html#Syncfusion_Android_DataForm_SfDataForm_RegisterEditor_System_Type_System_String_) method and specify the type and editor.

{% tabs %}
{% highlight c# %}

dataForm.RegisterEditor(typeof(int), "NumericUpDown");

{% endhighlight %}
{% endtabs %}

Here, the `NumericUpDown` editor will be loaded for the integer type instead of numeric editor.

## Changing editor for property

To change the editor for any property, use the [RegisterEditor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.SfDataForm.html#Syncfusion_Android_DataForm_SfDataForm_RegisterEditor_System_String_System_String_) method and specify the property name and editor.

{% tabs %}
{% highlight c# %}

dataForm.RegisterEditor("IsAvailable", "Switch");

{% endhighlight %}
{% endtabs %}

Here, the Switch editor will be loaded for the `IsAvailable` property (bool type) instead of `CheckBox` editor.

## Customizing existing editor

The existing editors defined in the previous table can be customized by overriding the default editors. 

Here, the [DataFormTextEditor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.DataFormTextEditor.html) is customized to set different foreground for the FirstName property text editor.

{% tabs %}
{% highlight c# %}
public class CustomTextEditor : DataFormTextEditor
{
    public CustomTextEditor(SfDataForm dataForm) : base(dataForm)
    {
    }
    
    protected override void OnInitializeView(DataFormItem dataFormItem, EditText view)
    {
        if (dataFormItem.Name == "FirstName")
            view.SetTextColor(Color.Green);
        base.OnInitializeView(dataFormItem, view);
    }
}

dataForm.RegisterEditor("Text", new CustomTextEditor(dataForm));            
{% endhighlight %}
{% endtabs %}

![Customizing existing editor of data form item in Xamarin.Android DataForm](SfDataForm_images/EditorCustomization.png)

## Creating new custom editor

Create the custom editor by overriding the [DataFormEditor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.DataFormEditor-1.html) class.

Property settings, commit, data validation can be handled by overriding the required methods. Here, the `EditText` is loaded for `Age` editor.

{% tabs %}
{% highlight c# %}

public class CustomTextEditor : DataFormEditor<EditText>
{
	public CustomTextEditor(SfDataForm dataForm) : base(dataForm)
	{
	}

	protected override EditText OnCreateEditorView()
	{
		return new EditText(this.dataForm.Context);
	}
	protected override void OnInitializeView(DataFormItem dataFormItem, EditText view)
	{
		base.OnInitializeView(dataFormItem, view);
	}

	protected override void OnWireEvents(EditText view)
	{
		view.TextChanged += OnViewTextChanged;
		view.FocusChange += OnViewFocusChange;
	}

	private void OnViewFocusChange(object sender, View.FocusChangeEventArgs e)
	{
		var view = sender as EditText;
		view.SetTextColor(Color.Red);

		if (this.DataForm.CommitMode == CommitMode.LostFocus || this.DataForm.ValidationMode == ValidationMode.LostFocus)
			this.OnValidateValue(view);
		if (this.DataForm.CommitMode != CommitMode.LostFocus) return;
		this.OnCommitValue(view);
		OnValidateValue(sender as EditText);
	}

	private void OnViewTextChanged(object sender, Android.Text.TextChangedEventArgs e)
	{
		var view = sender as EditText;
		if (DataForm.CommitMode == CommitMode.PropertyChanged || DataForm.ValidationMode == ValidationMode.PropertyChanged)
			this.OnValidateValue(view);
		if (this.DataForm.CommitMode != CommitMode.PropertyChanged) return;
		this.OnCommitValue(view);
	}

	private void OnViewPropertyChanged(object sender, PropertyChangedEventArgs e)
	{
		OnValidateValue(sender as EditText);
	}

	protected override bool OnValidateValue(EditText view)
	{
		return this.DataForm.Validate("Age");
	}

	protected override void OnCommitValue(EditText view)
	{
		var dataFormItemView = view.Parent as DataFormItemView;
		this.DataForm.ItemManager.SetValue(dataFormItemView.DataFormItem, view.Text);
	}

	protected override void OnUnWireEvents(EditText view)
	{
		view.TextChanged -= OnViewTextChanged;
		view.FocusChange -= OnViewFocusChange;
	}
}

dataForm.RegisterEditor("numeric", new CustomTextEditor(dataForm));
dataForm.RegisterEditor("Age", "numeric");
dataForm.ValidationMode = ValidationMode.LostFocus;

{% endhighlight %}
{% endtabs %}

You should manually commit the custom DataFormItem editor value by using [OnCommitValue](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.DataFormEditor-1.html#Syncfusion_Android_DataForm_Editors_DataFormEditor_1_OnCommitValue__0_) override method of [DataFormEditor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.DataFormEditor-1.html) class on custom editor `Value` or `Focus changed` event which is used to update the custom editor value in respective property in [DataObject](https://help.syncfusion.com/xamarin-android/sfdataform/getting-started#setting-data-object) based on dataform [commit mode](https://help.syncfusion.com/xamarin-android/sfdataform/editing#commit-mode) set. 

Also , you should manually validate the custom editor value in by using [OnValidateValue](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.Editors.DataFormEditor-1.html#Syncfusion_Android_DataForm_Editors_DataFormEditor_1_OnValidateValue__0_) override method of `DataFormEditor` class on custom editor `Value` or `Focus changed` event which is used to validate the custom editor value based on data form [validation mode](https://help.syncfusion.com/xamarin-android/sfdataform/validation?cs-save-lang=1&cs-lang=xaml#validation-mode) set. In the override method for OnValidateValue, you need to return [DataForm.Validate(string)](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.SfDataForm.html#Syncfusion_Android_DataForm_SfDataForm_Validate) method in order to validate the particular data item.

![Creating custom editor for the data form item in Xamarin.Android DataForm](SfDataForm_images/DataFormCustomEditor.png)

## Support for Email editor

You can load the Email editor by changing input type in the [AutoGeneratingDataFormItem](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.SfDataForm.html) event.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;
private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem.Name == "Email")
        (e.DataFormItem as DataFormTextItem).InputType = Android.Text.InputTypes.TextVariationEmailAddress;
}
{% endhighlight %}
{% endtabs %}

![Loading Email editor to the data form item in Xamarin.Android DataForm](SfDataForm_images/EmailEditor.png)

## Commit mode

The [CommitMode](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.CommitMode.html) determines when the value should be committed to the data object.

The supported commit modes are as follows:

* LostFocus
* PropertyChanged
* Explicit

{% tabs %}
{% highlight c# %}
dataForm.CommitMode = CommitMode.LostFocus;
{% endhighlight %}
{% endtabs %}

### LostFocus

If the commit mode is LostFocus, the value is committed when the editor lost its focus.

### PropertyChanged

The value will be committed immediately when it is changed.

### Explicit

The value should be committed manually by calling the [SfDataForm.Commit](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.SfDataForm.html#Syncfusion_Android_DataForm_SfDataForm_Commit().html) or [SfDataForm.Commit(propertyName)](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.SfDataForm.html#Syncfusion_Android_DataForm_SfDataForm_Commit(String).html) method.

The following code commits the value of all the properties in the data object:

{% tabs %}
{% highlight c# %}
dataForm.Commit();
{% endhighlight %}
{% endtabs %}

To commit the specific property value, pass the property name as argument.

{% tabs %}
{% highlight c# %}
dataForm.Commit("Name");
{% endhighlight %}
{% endtabs %}

## Update editor value based on another editor

You can the update the editor value by using the [SfDataForm.UpdateEditor](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.SfDataForm.html#Syncfusion_Android_DataForm_SfDataForm_UpdateEditor_System_String_) method at runtime.

{% tabs %}
{% highlight c# %}
var expenseInfo = new ExpenseInfo();
expenseInfo.PropertyChanged += ExpenseInfo_PropertyChanged;
dataForm.DataObject = expenseInfo;
SetContentView(dataForm);

private void ExpenseInfo_PropertyChanged(object sender, PropertyChangedEventArgs e)
{
    if (e.PropertyName == "Budget" || e.PropertyName == "Expense")
    {
        var item = sender as ExpenseInfo;
        item.Balance = item.Budget - item.Expense;
        dataForm.UpdateEditor("Balance");               
    }
}
{% endhighlight %}
{% endtabs %}

Here, the Balance property value is updated based on Budget and Expense properties. For updating value in editor, the `UpdateEditor` method is called.

You can download the sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/UpdateEditors1637679644).

## Converter

To show the original value in different format or as different value, use the [Converter](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.ConverterAttribute.html) attribute.

### Changing original value of the DataForm property value using converter

Here, the original value is multiplied by 10 and shown in editor. While committing, it is divided by 10 and stored in the data object.

{% tabs %}
{% highlight c# %}
public class ValueConverterExt : IPropertyValueConverter
{
    public object Convert(object value)
    {            
        var amount = double.Parse(value.ToString());
        return amount * 10;
    }

    public object ConvertBack(object value)
    {
        var amount = double.Parse(value.ToString());
        return amount / 10;
    }
}

private double? amount = 1000;

[Converter(typeof(ValueConverterExt))]
public double? Amount
{
    get
    {
        return amount;
    }
    set
    {
        amount = value;
        RaisePropertyChanged("Amount");
    }
}
{% endhighlight %}
{% endtabs %}

### Using date editor for DateTimeOffset DataForm property data type

In SfDataForm, you cannot use date editor for `DateTimeOffset` property data type. To overcome this, you need to use `Converter` attribute to convert `DateTimeOffset` to `DateTime` value and vice-versa.

{% tabs %}
{% highlight c# %}

private DateTimeOffset displayDate;

[Converter(typeof(ValueConverterExt))]
public DateTimeOffset DisplayDate
{
    get
    {
        return displayDate;
    }
    set
    {
        displayDate = value;
    }
}
public class ValueConverterExt : IPropertyValueConverter
{
    public object Convert(object value)
    {
        DateTime baseTime = new DateTime(2008, 6, 19, 7, 0, 0);
        DateTime targetTime;

        var dateTimeOffset = (DateTimeOffset)value;
        dateTimeOffset = new DateTimeOffset(baseTime,
                                            TimeZoneInfo.Local.GetUtcOffset(baseTime));
        targetTime = dateTimeOffset.DateTime;
        return targetTime;
    }
    public object ConvertBack(object value)
    {
        var dateTime = (DateTime)value;
        dateTime = new DateTime(2008, 6, 19, 7, 0, 0);
        dateTime = DateTime.SpecifyKind(dateTime, DateTimeKind.Local);
        DateTimeOffset dateTimeOffset = dateTime;
        return dateTimeOffset;
    }
}
{% endhighlight %}
{% endtabs %}

You can download the source code of this demo from here [DateTimeOffsetConverter](https://github.com/SyncfusionExamples/Convert-DateTimeOffset-into-DateTime-and-back-in-Xamarin-DataForm)

## Disable editing
You can disable editing by setting the [IsReadOnly](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.SfDataForm.html#Syncfusion_Android_DataForm_SfDataForm_IsReadOnly) property of the data form.

{% tabs %}
{% highlight c# %}
dataForm.IsReadOnly = true;
{% endhighlight %}
{% endtabs %}

You can also change the editing behavior by setting the [IsReadOnly](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormItem.html#Syncfusion_Android_DataForm_DataFormItem_IsReadOnly) property of the [DataFormItem](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormItem.html).

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null)
    {
        if (e.DataFormItem.Name == "Salary")
            e.DataFormItem.IsReadOnly = true;
    }
}
{% endhighlight %}
{% endtabs %}

You can also change the editing behavior at runtime.

{% tabs %}
{% highlight c# %}
private void Button_Click(object sender, System.EventArgs e)
{
    var dataFormItem = dataForm.ItemManager.DataFormItems["FirstName"];
    dataFormItem.IsReadOnly = true;
}
{% endhighlight %}
{% endtabs %}

N> [DataFormItem.IsReadOnly](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormItem.html#Syncfusion_Android_DataForm_DataFormItem_IsReadOnly) takes higher priority than [SfDataForm.IsReadOnly](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.SfDataForm.html#Syncfusion_Android_DataForm_SfDataForm_IsReadOnly).

You can also have option to define the editing behavior from `SfDataForm.DataObject` definition using the [ReadOnly](https://msdn.microsoft.com/en-us/library/system.componentmodel.readonlyattribute.aspx) attribute and [EditableAttribute](https://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations.editableattribute.aspx).

{% tabs %}
{% highlight c# %}
private double? balance;
[ReadOnly(true)]
public double? Balance
{
    get
    {
        return balance;
    }
    set
    {
        balance = value;
        RaisePropertyChanged("Balance");
    }
}
private double? balance;
[Editable(false)]
public double? Balance
{
    get
    {
        return balance;
    }
    set
    {
        balance = value;
        RaisePropertyChanged("Balance");
    }
}

{% endhighlight %}
{% endtabs %}

You can also define the editing behavior by defining the [SfDataForm.DataObject](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.SfDataForm.html#Syncfusion_Android_DataForm_SfDataForm_DataObject) fields definition without `setter` or with `private set`.

{% tabs %}
{% highlight c# %}
private double? balance;
public double? Balance
{
    get
    {
        return balance;
    }    
}
private double? balance;
public double? Balance
{
    get
    {
        return balance;
    }
    private set
    {
        balance = value;
    }
}
{% endhighlight %}
{% endtabs %}
