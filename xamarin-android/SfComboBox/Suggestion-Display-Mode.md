---
layout : post
title : ComboBoxMode mode for Syncfusion ComboBox control in Xamarin.Android
description : Learn how to change the ComboBoxMode in SfComboBox 
platform : Xamarin.Android
control : SfComboBox
documentation : ug
---

# Suggestion display mode

The `ComboBoxMode` property is used to decide the suggestion pattern for displaying the filtered data according to the text entered. The different types of patterns are, described below

* Suggest

* Append

* Suggest and Append

N> The default option is suggest mode.

## Suggest in drop-down 

* Suggest - Displays suggestions in the drop-down.

{% tabs %}

{% highlight C# %}
	
comboBox.ComboBoxMode = ComboBoxMode.Suggest;	

{% endhighlight %}

{% endtabs %}

## Append

* Append - Appends the first matching string with the entered character.

{% tabs %}

{% highlight C# %}
	
comboBox.ComboBoxMode = ComboBoxMode.Append;

{% endhighlight %}

{% endtabs %}

## Both append and suggest in drop-down
	
* SuggestAppend - Displays the suggestion in the drop-down along with appending the first matching string.

{% tabs %}

{% highlight C# %}
	
comboBox.ComboBoxMode = ComboBoxMode.SuggestAppend;

{% endhighlight %}

{% endtabs %}

![](images/comboboxmode.png)
 
