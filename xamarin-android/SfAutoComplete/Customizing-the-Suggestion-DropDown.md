---
layout : post
title : MinimumPrefixCharacters for Syncfusion AutoComplete Control in Xamarin.Android
description : Learn how to set the MinimumPrefixCharacter in SfAutoComplete 
platform : Xamarin.Android
control : SfAutoComplete
documentation : ug
---


# Customizing the Suggestion DropDown

The suggestion list displaying behavior can be customized based on the entered text and delays in displaying the items.

## Set Minimum Prefix Character

Instead of displaying suggestion list on every text entry, the most possible match can be filtered and displayed after few text entries. This can be done by modifying `MinimumPrefixCharacters`.

N> The default property value is 1.

{% tabs %}

{% highlight C# %}
	
countryAutoComplete.MinimumPrefixCharacters = 4;
	 
{% endhighlight %}

{% endtabs %}
	
![Minimum prefix character](images/minimumprefixcharacter.png)

## Set PopUp Delay

We can delay the time taken to display the dropdown with suggestion list by using the `PopUpDelay` property in SfAutoComplete .

N> The default value is 0. The property value is maintained in milliseconds.

{% tabs %}

{% highlight C# %}
	
countryAutoComplete.PopUpDelay = 100;
	 
{% endhighlight %}

{% endtabs %}

## Set Maximum Height to the DropDown

The height of the drop-down portion of the SfAutocomplete control can be varied using `MaximumDropDownHeight` property. 

N> The `MaximumDropDownHeight` value can be any positive integer value.	

{% tabs %}

{% highlight C# %}
	
countryAutoComplete.MaximumDropDownHeight = 200;
	 
{% endhighlight %}

{% endtabs %}
	
![Maximum drop down height](images/maximumdropdownheight.png)

## Set border color to the DropDown

The DropDownBorderColor property is used to change the border color of DropDown. The following code example demonstrates how to change the border color of DropDown.

{% tabs %}

{% highlight C# %}
	
            LinearLayout linearLayout = new LinearLayout(this);
            linearLayout.LayoutParameters = new ViewGroup.LayoutParams(1000, ViewGroup.LayoutParams.MatchParent);
            linearLayout.SetBackgroundColor(Android.Graphics.Color.Transparent);

            SfAutoComplete countryAutoComplete = new SfAutoComplete(this);
            countryAutoComplete.LayoutParameters = new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MatchParent, 50);

            List<String> countryList = new List<String>();
            countryList.Add("Uganda");
            countryList.Add("Ukraine");
            countryList.Add("United Arab Emirates");
            countryList.Add("United Kingdom");
            countryList.Add("United States");

            ArrayAdapter<String> countryListDataAdapters = new ArrayAdapter<String>(this, Android.Resource.Layout.SimpleListItem1, countryList);
            countryAutoComplete.AutoCompleteSource = countryListDataAdapters;
            countryAutoComplete.DropDownBorderColor = Color.Red;
            countryAutoComplete.MaximumDropDownHeight = 200;

            linearLayout.AddView(countryAutoComplete);
            SetContentView(linearLayout);
	 
{% endhighlight %}

{% endtabs %}
	
![Dropdown border color](images/dropdown-border-color.png)