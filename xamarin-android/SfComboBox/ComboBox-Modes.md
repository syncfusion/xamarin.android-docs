---
layout : post
title : ComboBox modes for Syncfusion ComboBox control in Xamarin.Android
description : Learn how to change the ComboBox modes in SfComboBox
platform : Xamarin.Android
control : SfComboBox
documentation : ug
---

# ComboBox modes

The SfComboBox supports both editable and non-editable text boxes to choose selected items in given data source. Users can select an item from the suggestion list. 

## Editable combo box

In editable mode, the combo box allows users to edit in the text box that shows the suggestion in drop-down list based on the input.

{% tabs %}

{% highlight C# %}	
comboBox.IsEditableMode = true; 	 
{% endhighlight %}

{% endtabs %}

![](images/editable.png)
	
## Non-editable combo box

Non-editable mode is used to prevent users from typing and allows them select from the drop-down list.

{% tabs %}

{% highlight C# %}
comboBox.IsEditableMode = false;  
{% endhighlight %}

{% endtabs %}

![](images/noneditable.png)
 
