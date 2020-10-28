---
layout : post
title : Filtering in Syncfusion SfComboBox control for Xamarin.Android
description : Learn how to filter the text in SfComboBox
platform : Xamarin.Android
control : ComboBox
documentation : ug
---

# Filtering Option 

The combo box control provides an option to filter the dropdown list based on the text typed. You can set filter option by setting the `AllowFiltering` boolean property to true. 

N> The Allow-Filtering property works only when the IsEditableMode property is set to true.

{% tabs %}

{% highlight C# %}

combobox = new SfComboBox(); 
combobox.IsEditableMode = true; 
combobox.AllowFiltering = true; 

{% endhighlight %}

{% endtabs %}

![](images/filtering.png)