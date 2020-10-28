---
layout : post
title : UI Customization for Syncfusion ComboBox Control in Xamarin.Android
description : Learn how to use customization in SfComboBox 
platform : Xamarin.Android
control : SfComboBox
documentation : ug
---

# UI customization

The combo box control provides user-friendly customizing options for both entry part and drop-down part.  This section explains how to customize the entire combo box control.

## Customizing the entry

The `TextColor`, `TextSize`, `FontAttributes`, `FontFamily` and `BorderColor` properties are used to customize the foreground color, font size, font attribute, font family, and border color of the entry part.

{% tabs %}

{% highlight C# %}
LinearLayout linearLayout = new LinearLayout(this);
linearLayout.LayoutParameters = new ViewGroup.LayoutParams(500, ViewGroup.LayoutParams.MatchParent);
linearLayout.SetBackgroundColor(Android.Graphics.Color.White);

SfComboBox comboBox = new SfComboBox(this);
comboBox.Text = "Sample Text";
comboBox.TextColor = Color.ParseColor("#1976d2");
comboBox.TextSize = 20;
comboBox.FontTypeface = Typeface.DefaultBold;
comboBox.BorderColor = Color.Brown;
comboBox.LayoutParameters = new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MatchParent, 50);

linearLayout.AddView(comboBox);
SetContentView(linearLayout);	 
{% endhighlight %}

{% endtabs %}
	
![Customizing entry](images/customizingentry.png)

## Customizing the suggestion box

### Changing suggestion item height

The `DropDownItemHeight` property is used to modify the height of suggestion items in the drop-down list. The following code example shows this:

{% tabs %}

{% highlight C# %}
List<String> countryList = new List<String>();
countryList.Add("Uganda");
countryList.Add("Ukraine");
countryList.Add("United Arab Emirates");
countryList.Add("United Kingdom");
countryList.Add("United States");
comboBox.DataSource = countryList; 
comboBox.DropDownItemHeight = 70;	
{% endhighlight %}

{% endtabs %}

![Suggestion item height](images/suggestionitemheight.png)

### Changing the border color of suggestion box

The DropDownBorderColor property is used to change the border color of suggestion box. The following code example demonstrates how to change the border color of suggestion box.

{% tabs %}

{% highlight C# %}

            LinearLayout linearLayout = new LinearLayout(this);
            linearLayout.LayoutParameters = new ViewGroup.LayoutParams(1000, ViewGroup.LayoutParams.MatchParent);
            linearLayout.SetBackgroundColor(Android.Graphics.Color.Transparent);

            SfComboBox countryComboBox = new SfComboBox(this);
            countryComboBox.LayoutParameters = new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MatchParent, 50);

            List<String> countryList = new List<String>();
            countryList.Add("Uganda");
            countryList.Add("Ukraine");
            countryList.Add("United Arab Emirates");
            countryList.Add("United Kingdom");
            countryList.Add("United States");

            ArrayAdapter<String> countryListDataAdapters = new ArrayAdapter<String>(this, Android.Resource.Layout.SimpleListItem1, countryList);
            countryComboBox.ComboBoxSource = countryListDataAdapters;
            countryComboBox.DropDownBorderColor = Color.Red;
            countryComboBox.MaximumDropDownHeight = 200;

            linearLayout.AddView(countryComboBox);
            SetContentView(linearLayout);
     
{% endhighlight %}

{% endtabs %}
	
![Dropdown border color](images/dropdown-border-color.png)

### Customizing suggestion items

Suggestion box items can be customized using the `DropDownItemFontAttributes`, `DropDownItemFontFamily`, `DropDownTextSize`, and `DropDownTextColor` properties.

{% tabs %}

{% highlight C# %}
List<String> countryList = new List<String>();
countryList.Add("Uganda");
countryList.Add("Ukraine");
countryList.Add("United Arab Emirates");
countryList.Add("United Kingdom");
countryList.Add("United States");
comboBox.DataSource = countryList;
comboBox.DropDownTextSize = 16;
comboBox.DropDownTextColor = Color.ParseColor("#1976d2");
comboBox.DropDownItemFontTypeface = Typeface.DefaultBold;       
{% endhighlight %}

{% endtabs %}
	
![Customizing suggestion items](images/customizingsuggestionItems.png)

## Drop-down button customization 

The drop-down button can be customized using the `DropDownButtonSettings` property in the following ways:

* Width – Sets the width for the drop-down button. 

* Height - Sets the height for drop-down button. 

* FontIcon - Sets the different FontIcon for drop-down button. 

* FontColor - Sets the different  FontColor for drop-down button. 

* FontSize - Sets the different  FontSize for drop-down button. 

* FontFamily - Sets the different  FontFamily for drop-down button. 

* BackgroundColor - Sets the background color for drop-down button. 

* HighlightedBackgroundColor - Sets the background color for the drop-down button when it is pressed. 

* HighlightedFontColor - Sets the font color for the drop-down button when it is pressed. 

* Image - Sets the image to drop-down button. 

* View – Sets a custom view to the drop-down button.

{% tabs %}

{% highlight C# %}
DropDownButtonSettings buttonSettings = new DropDownButtonSettings();
buttonSettings.Image = "date.png";
comboBox.DropDownButtonSettings = buttonSettings; 	 
{% endhighlight %}

{% endtabs %}
	
![Button customizing](images/buttoncustomizing.png)

## Watermark

This property is used to customize the watermark text that is displayed when the textbox is empty.

{% tabs %}

{% highlight C# %}
comboBox.Watermark = "Enter a Country Name"; 
{% endhighlight %}

{% endtabs %}
	
![watermark](images/watermark.png)

### Changing watermark text color
 
The text color of watermark can be customized using the `WatermarkColor` property.

{% tabs %}

{% highlight C# %}
comboBox.WatermarkColor= Color.ParseColor("#1976d2");	 
{% endhighlight %}

{% endtabs %}
	
![Watermark color](images/watermarkcolor.png)




