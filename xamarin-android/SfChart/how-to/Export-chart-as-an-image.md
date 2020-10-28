---
layout: post
title: Export Syncfusion SfChart as an image in Xamarin.Android
description: This session describes how the Syncfusion Xamarin.Android SfChart can be exported as an image at device storage.
platform: Android
control: Chart
documentation: ug
---

# Export SfChart as an image in Xamarin.Android

The [`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html) can be converted as an image and saved in the desired directory by creating Bitmap from drawing cache and save it using the FileStream.

The code sample demonstrated as follows.

{% highlight c# %}

public void SaveAsImage(string filename) 
{       
    //Enabled drawing cache
    chart.DrawingCacheEnabled = true; 
    
    chart.SaveEnabled = true; 
    Bitmap bitmap = null; 
    //Create bitmap from chart drawing cache.
    using (bitmap = chart.DrawingCache) 
    { 
        var extension = filename.Split('.'); 
        //Create an image path with existing environment with the provided file name.
        var imagePath = 
            new Java.IO.File(Android.OS.Environment.ExternalStorageDirectory + "/Pictures/" + filename); 
        imagePath.CreateNewFile(); 
        using (Stream fileStream = new FileStream(imagePath.AbsolutePath, System.IO.FileMode.OpenOrCreate)) 
        { 
            try 
            { 
                string imageExtension = extension.Length > 1 ? extension[1].Trim().ToLower() : "jpg"; 

                //Compressed bitmap to get needed format.
                switch (imageExtension) 
                { 
                    case "png": 
                        bitmap.Compress(Bitmap.CompressFormat.Png, 100, fileStream); 
                        break; 
                    case "jpg":  case "jpeg": default: 
                        bitmap.Compress(Bitmap.CompressFormat.Jpeg, 100, fileStream); 
                        break; 
                } 
            } 
            finally 
            { 
                //Closing stream and disabled drawing cache. 
                fileStream.Flush(); 
                fileStream.Close(); 
                chart.DrawingCacheEnabled = false; 
            } 
        } 
    } 
}

{% endhighlight  %}

To save the image in Android, must grant device storage permission.

{% highlight xaml %}

<manifest . . . 
          package="ExportChartAsImage.ExportChartAsImage">

. . . 

	<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
</manifest>

{% endhighlight  %}

## See also

[How to export chart as an image in Xamarin.Android](https://www.syncfusion.com/kb/11930/how-to-export-the-charts-in-xamarin-android)

[How to export chart to PDF in Xamarin.Android](https://www.syncfusion.com/kb/9370/how-to-export-chart-to-pdf-in-xamarin-android)