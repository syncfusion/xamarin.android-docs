---
layout: post
title: ImageFilter in Syncfusion SfImageEditor control in Xamarin.Android
description: This section describes how to apply image filter support in SfImageEditor control for Xamarin.Android platform
platform: Xamarin.Android
control: SfImageEditor
documentation: ug
---

# Image filter in SfImageEditor

Using the SfImageEditor control, you can add effects such as hue, saturation, brightness, contrast, blur, and sharpen to the image. These effects can be applied from toolbar or using the ApplyImageEffect method. The [`ApplyImageEffect`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfImageEditor.Android.SfImageEditor.html#Syncfusion_SfImageEditor_Android_SfImageEditor_ApplyImageEffect_Syncfusion_SfImageEditor_Android_ImageEffect_System_Single_) method contains two arguments: [`ImageEffect`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfImageEditor.Android.SfImageEditor.html#Syncfusion_SfImageEditor_Android_SfImageEditor_ImageEffect) and [`EffectValue`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfImageEditor.Android.SfImageEditor.html#Syncfusion_SfImageEditor_Android_SfImageEditor_EffectValue). The ImageEffect is an enum, which contains the following effects:

* Hue
* Saturation
* Brightness
* Contrast
* Blur
* Sharpen 
* None

The [`EffectValue`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfImageEditor.Android.SfImageEditor.html#Syncfusion_SfImageEditor_Android_SfImageEditor_EffectValue) is the corresponding [`ImageEffect`](https://help.syncfusion.com/cr/xamarin-android/Syncfusion.SfImageEditor.Android.SfImageEditor.html#Syncfusion_SfImageEditor_Android_SfImageEditor_ImageEffect) values, which varies for each effect, and they are explained as follows.

## Hue

The hue represents the dominant wavelength of the color. The value of the hue effect ranges from -180 to 180.

{% highlight C# %}

public MainPage()
{               
    . . .
    editor.ApplyImageEffect(ImageEffect.Hue, 120);
    . . .
}

{% endhighlight %}

![SfImageEditor](ImageEditor_images/Hue.jpg)

## Saturation

The saturation represents the intensity of the color. The value of the saturation effect ranges from -100 to 100.

{% highlight C# %}

public MainPage()
{               
    . . .
    editor.ApplyImageEffect(ImageEffect. Saturation, -80);
    . . .
}

{% endhighlight %}

![SfImageEditor](ImageEditor_images/Saturation.jpg)

## Brightness

The brightness represents how bright the color is. The value of the brightness effect ranges from -100 to 100.

{% highlight C# %}

public MainPage()
{               
    . . .
    editor.ApplyImageEffect(ImageEffect.Brightness, -60);
    . . .
}

{% endhighlight %}

![SfImageEditor](ImageEditor_images/Brightness.jpg)

## Contrast

The contrast represents the color contrast of an image. The value of the contrast effect ranges from -100 to 100.

{% highlight C# %}

public MainPage()
{               
    . . .
    editor.ApplyImageEffect(ImageEffect. Contrast, -30);
    . . .
}

{% endhighlight %}

![SfImageEditor](ImageEditor_images/Contrast.jpg)

## Blur

The blur represents the clearness of the image. The value of the blur effect ranges from 0 to 6.

{% highlight C# %}

public MainPage()
{               
    . . .
    editor.ApplyImageEffect(ImageEffect.Blur, 4);
    . . .
}

{% endhighlight %}

![SfImageEditor](ImageEditor_images/Blur.jpg)

## Sharpen

The sharpen is used to highlight edges and fine details in an image. The value of the sharpen effect ranges from 0 to 6.

{% highlight C# %}

public MainPage()
{               
    . . .
    editor.ApplyImageEffect(ImageEffect.Sharpen, 2);
    . . .
}

{% endhighlight %}

![SfImageEditor](ImageEditor_images/Sharpen.jpg)

N> The ImageEffect enum also contains “None” option, which removes all the previously applied effects, which are not saved and displays the original image. When applying effects using the ApplyImageEffect method, the effects will be saved automatically. But, if you apply effects from toolbar, each effect will be saved only when clicking the OK button, else all the applied effects will not be saved.
