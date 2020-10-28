---
layout: post
title: Getting Started | SfBarcode | Xamarin.Android | Syncfusion
description: getting started
platform: Xamarin.Android
control: SfBarcode
documentation: ug
---

# Getting Started

## Create your first Barcode in Xamarin.Android Studio

This section explains how to configure a Barcode for Xamarin.Android application by using the Xamarin.Android. To get started with the Essential Barcode, refer to the following steps and in result, you get the output on Android devices as follows.

![](Getting-Started_images/Getting-Started_img1.png)                                                                                             
QR Barcode                                                                                   
{:.caption}

## Configure the Barcode control

The following steps explain how to create and configure a Barcode.

1.Add reference to the SfBarcode as follows.
 
2.Create a SfBarcode instance in the Main Activity and set the SfBarcode as a ContentView in onCreate() overridden method.

{% highlight c# %} 
   
   public class MainActivity extends Activity {

	@Override

	protected void onCreate(Bundle savedInstanceState) {

		super.onCreate(savedInstanceState);

		// creates new instance for Barcode

		SfBarcode sfBarcode = new SfBarcode(this);

		setContentView(sfBarcode);

	}
	
{% endhighlight %}  
  
3.Then you can set the text that you want to encode.
 
  
  {% highlight c# %} 
  
    sfBarcode.Text = "http://www.wikipedia.org";
  
  {% endhighlight %}  
   
4.Set the required symbology to encode the given text. By default, the given text is encoded by using Code 39 symbology.

  {% highlight c# %} 
  
    sfBarcode.Symbology = BarcodeSymbolType.QRBarcode;
  
  {% endhighlight %}  
   
5.To customize the Barcode, initialize the settings of the corresponding Barcode symbology. 

{% highlight c# %}

    QRBarcodeSettings setting = new QRBarcodeSettings();
    setting.XDimension = 15;
    sfBarcode.SymbologySettings = setting;

  {% endhighlight %}  
   
6.Finally, the Barcode is generated as displayed in the screenshot by using the following code example.

{% highlight c# %}
  
    public class MainActivity : Activity
    {
        protected override void OnCreate(Bundle bundle)
        {
            base.OnCreate(bundle);
            SfBarcode sfBarcode = new SfBarcode(this);
            sfBarcode.Text = "http://www.wikipedia.org";
            sfBarcode.Symbology = BarcodeSymbolType.QRBarcode;
            QRBarcodeSettings setting = new QRBarcodeSettings();
            setting.XDimension = 15;
            sfBarcode.SymbologySettings = setting;
            sfBarcode.SetBackgroundColor(Color.White);
            SetContentView(sfBarcode);
        }
    }

  {% endhighlight %}  
   
  ![](Getting-Started_images/Getting-Started_img3.png)   

