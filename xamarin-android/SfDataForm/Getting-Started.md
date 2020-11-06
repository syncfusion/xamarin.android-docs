---
layout: post
title: Getting started | SfDataForm | Xamarin.Android | Syncfusion
description: This section explains key features and getting started with SfDataForm for Xamarin.Android platform.
platform: Xamarin.Android
control: SfDataForm
documentation: ug
---

**SfDataForm**

The SfDataForm control helps editing the data fields of any data object. It can be used to develop various forms such as login, reservation, data entry, etc. Key features includes the following:

* Layout and grouping: Supports to linear and grid layout with grouping support. Supports customizing the layout with different heights for each item.
* Caption customization: Supports loading the image as caption for the editor.
* Editors: Built-in support for text, numeric, numeric up-down, picker, date picker, time picker, switch, and checkbox editors. 
* Custom editor: Supports loading the custom editors.
* Validation: Built-in support to validate the data based on the [IDataErrorInfo](https://msdn.microsoft.com/en-us/library/system.componentmodel.idataerrorinfo.aspx), [INotifyDataErrorInfo](https://msdn.microsoft.com/en-us/library/system.componentmodel.inotifydataerrorinfo.aspx), and data annotations. It also programmatically supports validation handling.

# Getting started with Xamarin.Android DataForm(SfDataForm)

This section explains the quick overview to use the [SfDataForm](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.SfDataForm.html) for Xamarin.Android in your application.

## Assembly deployment

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, {Syncfusion Essential Studio Installed location} \Essential Studio\15.x.x.x\Xamarin\lib

Eg: C:\Program Files (x86) \Syncfusion\Essential Studio\15.3.0.26\Xamarin\lib

N> Assemblies can be found in unzipped package location in Mac.

### Adding SfDataForm Reference

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfDataForm to your project, open the NuGet package manager in Visual Studio, and search for [Syncfusion.Xamarin.SfDataForm](https://www.nuget.org/packages/Syncfusion.Xamarin.SfDataForm.Android/#), and then install it.

![Adding  data form nuget reference in Xamarin.Android DataForm]](SfDataForm_images/SfDataForm_NuGet_Android.png)

To know more about obtaining our components, refer to this [link](https://help.syncfusion.com/xamarin-android/introduction/download-and-installation). Also, if you prefer to manually refer the assemblies instead of NuGet, refer the list of assemblies mentioned in the table below.

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>
Xamarin.Android
</td>
<td>
Syncfusion.SfNumericUpDown.Android.dll<br/>Syncfusion.SfNumericTextBox.Android.dll<br/>Syncfusion.SfDataForm.Android.dll<br/></td>
</tr>
</table>

>**Important** 
Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Creating the data form

In this section, you will create Xamarin.Android application with `SfDataForm`. The control should be configured entirely in C# code.

* Creating the project.
* Adding data form in Xamarin.Android.
* Creating data object.
* Setting data object.

### Creating the project

Create a new Android application in Xamarin Studio or Visual Studio for Xamarin.Android.

### Adding data form in Xamarin.Android

To add the data form to your application, follow the steps:

1. Add required assemblies as discussed in assembly deployment section.
2. Import the `SfDataForm` namespace [Syncfusion.Android.DataForm](https://help.syncfusion.com/cr/xamarin-android).
3. Create an instance of data form control and add as a view to the linear layout.

{% tabs %}
{% highlight c# %}

using Syncfusion.Android.DataForm;

[Activity(Label = "GettingStarted", MainLauncher = true, Icon = "@drawable/icon")]
public class MainActivity : Activity
{        
    protected override void OnCreate(Bundle bundle)
    {
        base.OnCreate(bundle);
            
        var dataForm = new SfDataForm(this);
        SetContentView(dataForm);
    }
}

{% endhighlight %}
{% endtabs %}

### Creating data object

The `SfDataForm` is a data edit control so, create a data object to edit the data object.

Here, the data object named **ContactsInfo** created with some properties.

{% tabs %}
{% highlight c# %}

public class ContactsInfo
{
    private string firstName;
    private string middleName;
    private string lastName;
    private string contactNo;
    private string email;
    private string address;
    private DateTime? birthDate;
    private string groupName;

    public ContactsInfo()
    {

    }

    public string FirstName
    {
        get { return this.firstName; }
        set
        {
            this.firstName = value;
        }
    }

    public string MiddleName
    {
        get { return this.middleName; }
        set
        {
            this.middleName = value;
        }
    }
    public string LastName
    {
        get { return this.lastName; }
        set
        {
            this.lastName = value;
        }
    }

    public string ContactNumber
    {
        get { return contactNo; }
        set
        {
            this.contactNo = value;
        }
    }

    public string Email
    {
        get { return email; }
        set
        {
            email = value;
        }
    }

    public string Address
    {
        get { return address; }
        set
        {
            address = value;
        }
    }

    public DateTime? BirthDate
    {
        get { return birthDate; }
        set
        {
            birthDate = value;
        }
    }

    public string GroupName
    {
        get { return groupName; }
        set
        {
            groupName = value;
        }
    }
}

{% endhighlight %}
{% endtabs %}

## Setting data object

To populate the labels and editors in the data form, set the [DataObject](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.SfDataForm.html#Syncfusion_Android_DataForm_SfDataForm_DataObject) property.

{% tabs %}
{% highlight c# %}

dataForm.DataObject = new ContactsInfo();

{% endhighlight %}
{% endtabs %}

Now, run the application to render the `data form` to edit the data object as in the following screenshot:

![Setting data object to data form in Xamarin.Android DataForm](SfDataForm_images/Overview.png)

You can download the entire source code of this demo for Xamarin.Android from here [DataFormGettingStarted](http://www.syncfusion.com/downloads/support/directtrac/general/ze/DataFormSample-696015926.zip).

## Defining editors

The data form control automatically generates [DataFormItems](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormItems.html) (which has UI settings of data field) when the data object set to the `SfDataForm.DataObject` property. The [DataFormItem](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormItem.html) encapsulates the layout and editor setting for the data field appearing in the data form. When the `DataFormItems` are generated, you can handle the SfDataForm.AutoGeneratingDataFormItem event to customize or cancel the `DataFormItem`. 

The type of input editor generated for the data field depends on the type and attribute settings of the property. The following table lists the `DataFormItem` and its constraints for generation:

<table>
<tr>
<th>Generated DataFormItem Type</th>
<th>Data Type / Attribute</th>
</tr>
<tr>
<td>
{{'[DataFormTextItem](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormTextItem.html)'| markdownify }}
</td>
<td>
Default DataFormItem generated for the String type and the properties with [DataType(DataType.Text)], [DataType(DataType.MultilineText)] and [DataType(DataType.Password)] attributes.
</td>
</tr>
<tr>
<td>
{{'[DataFormNumericItem](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormNumericItem.html)'| markdownify }}
</td>
<td>
Generated for the Int or Double type property.
[DataType(DataType.Currency)].
[DataType("Percent")]
</td>
</tr>
<tr>
<td>
{{'[DataFormDateItem](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormDateItem.html)'| markdownify }}
</td>
<td>
Generated for the DateTime type property.
[DataType(DataType.Date)].
[DataType(DataType.DateTime)].
</td>
</tr>
<tr>
<td>
{{'[DataFormTimeItem](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormTimeItem.html)'| markdownify }}
</td>
<td>
Generated for the DataTime type property.
[DataType(DataType.Time)].
</td>
</tr>
<tr>
<td>
{{'[DataFormPickerItem](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormPickerItem.html)'| markdownify }}
</td>
<td>
Generated for the Enum type property.
[EnumDataTypeAttribute]
</td>
</tr>
</table>
The following list of editors are supported:
<table>
<tr>
<th>Editor</th>
<th>Data Type/Attribute</th>
<th>Input control loaded</th>
</tr>
<tr>
<td>
Text
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
Int or Double type property.
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
The Int or Double type Property with percent value.
[DataType("Percent")]].
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
The Int or Double type property with currency value.
[DataType(DataType.Currency)].
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
The DateTime type property with date value.
[DataType(DataType.Date)]
[DataType(DataType.DateTime)]
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
Property with [DataType(DataType.Time)] attribute.
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
The String type property with [DataType(DataType.Password)] attribute.
</td>
<td>
{{'[EditText](https://developer.android.com/reference/android/widget/EditText)'| markdownify }}
</td>
</tr>
</table>

## Layout options

### Label position

By default, the data form arranges the label at left side and input control at the right side. You can change the label position by setting the [SfDataForm.LabelPosition](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.SfDataForm.html#Syncfusion_Android_DataForm_SfDataForm_LabelPosition) property. You can position the label from left to top of the input control by setting the `LabelPosition` as Top.

{% tabs %}
{% highlight c# %}

dataForm.LabelPosition = LabelPosition.Top;

{% endhighlight %}
{% endtabs %}

![Setting label position to data form item in Xamarin.Android DataForm](SfDataForm_images/LabelTop.png)

### Grid layout

By default, the data form arranges one data field per row. It is possible to have more than one date field per row by setting the [ColumnCount](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.SfDataForm.html#Syncfusion_Android_DataForm_SfDataForm_ColumnCount) property which provides grid like layout for the data form.

{% tabs %}
{% highlight c# %}

dataForm.ColumnCount = 2;

{% endhighlight %}
{% endtabs %}
![Setting column count to data form in Xamarin.Android DataForm](SfDataForm_images/DataFormGrid.png)

## Loading DataForm with customized height and width

The DataForm can be loaded with specific height and width inside different layouts by specifying the height and width of the DataForm when adding it as a child to its parent.

{% tabs %}
{% highlight c# %}

dataForm = new SfDataForm(this);
linearLayout = new LinearLayout(this);
dataForm.DataObject = new ContactInfo();
//To place SfDataForm at center position, padding has been set.
linearLayout.SetPadding(100, 550, 0, 0);
linearLayout.AddView(dataForm,800,800);
SetContentView(linearLayout);

{% endhighlight %}
{% endtabs %}

![Loading data form with customized height and width Xamarin.Android DataForm](SfDataForm_images/CustomHeightWidth.png)

## Editing

By default, the data form enables editing of the data field. You can disable editing by setting the [IsReadOnly](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.SfDataForm.html#Syncfusion_Android_DataForm_SfDataForm_IsReadOnly) property of the data form. You can enable or disable editing for a particular data field by setting the [IsReadOnly](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormItem.html#Syncfusion_Android_DataForm_DataFormItem_IsReadOnly) property of [DataFormItem](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.Android.DataForm.DataFormItem.html) in the `AutoGeneratingDataFormItem` event. The data field editing behavior can also be defined by using [EditableAttribute](https://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations.editableattribute.aspx).

## Additional Help Resources

The [`Xamarin.Android SfDataForm`](https://www.syncfusion.com/kb/xamarin.android/dataform) Knowledge Base section contains responses to some of the most common questions that other customers have asked us before. So this will be a good place to search for topics that are not covered in the user guide.

Similar to the [`Knowledge Base`](https://www.syncfusion.com/kb/xamarin.android/dataform), the [`forum`](https://www.syncfusion.com/forums/xamarin.Android) section also contains responses to questions that other customers have asked us in the past.