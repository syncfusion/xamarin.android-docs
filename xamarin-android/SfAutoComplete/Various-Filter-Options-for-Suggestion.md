---
layout : post
title : Suggestion mode for Syncfusion AutoComplete Control in Xamarin.Android
description : Learn how to display suggestion mode in SfAutoComplete
platform : Xamarin.Android
control : SfAutoComplete
documentation : ug
---

# Various Filter Options for Suggestion

By default, the items that matches with the starting letter will be displayed as suggestion. This phenomenon can be changed using  `SuggestionMode` property, which provides various option to filter the data according to the text entered. There are eight types of suggestion modes and are described as follows.

## Words that Starts with Input Text

Displays the list of suggestions based on starting letter.

{% tabs %}

{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.StartsWith;
	 
{% endhighlight %}

{% endtabs %}
	
![](images/startswith.png)

### Filter with Character Casing

Displays the list of suggestions based on starting letter with case sensitive.

{% tabs %}

{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.StartsWithCaseSensitive;
	 
{% endhighlight %}

{% endtabs %}
	
![](images/startswithcasesensitive.png)

## Words that Contains the Input Text

Displays the list of suggestions, if autocomplete list contains that words.

{% tabs %}

{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.Contains;
	 
{% endhighlight %}

{% endtabs %}
	
![](images/contains.png)

### Filter with Character Casing

Displays the list of suggestions, if autocomplete list contains that words with case sensitive.

{% tabs %}

{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.ContainsWithCaseSensitive;
	 
{% endhighlight %}

{% endtabs %}
	
![](images/containswithcasesensitive.png)

## Words that Equals to the Input Text

Displays the word that matches.

{% tabs %}

{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.Equals;
	 
{% endhighlight %}

{% endtabs %}
	
![](images/equals.png)

### Filter with Character Casing

Displays the word that matches with case sensitive.

{% tabs %}

{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.EqualsWithCaseSensitive;
	 
{% endhighlight %}

{% endtabs %}
	
![](images/equalswithcasesensitive.png)

## Words that Ends with Input Text

Displays the list of suggestions based on ending word.

{% tabs %}

{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.EndsWith;
	 
{% endhighlight %}

{% endtabs %}
	
![](images/endswith.png)

### Filter with Character Casing

Displays the list of suggestions based on the ending word with case sensitive.

{% tabs %}

{% highlight C# %}
	
countryAutoComplete.SuggestionMode = SuggestionMode.EndsWithCaseSensitive;
	 
{% endhighlight %}

{% endtabs %}
	
![](images/endswithcasesensitive.png)


### Custom filter

Displays the list of suggestions based on the custom words in the SfAutoComplete.
{% tabs %}

{% highlight C# %}
	
countryAutoComplete.SuggestionMode = SuggestionMode.Custom;
	 
{% endhighlight %}

{% endtabs %}
	
![](images/customfilter.png)



