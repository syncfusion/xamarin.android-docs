---
layout: post
title: Localization of Syncfusion SfImageEditor control
description: This section describes how to Localize the contents of SfImageEditor control for Xamarin.Android platform
platform: xamarin.android
control: ImageEditor
documentation : ug
---

## Localization

The image editor control provides support for localization.You can localize ImageEditor contents by adding equivalent localized string.

## Change default control language

Based on the resource strings in the project the contents are localized. By default,ImageEditor control is available in English.

You can localize the text available in the control by adding equivalent localized string in the resource file.

Create String.xml in resource file in Android

Location- ProjectName.Android/Resources/values/Strings.Xml

![SfImageEditor](ImageEditor_images/androidstrings.png)

In below screenshot we have localized the text to French language.

![SfImageEditor](ImageEditor_images/androidresources.png)

![SfImageEditor](ImageEditor_images/localization.png)

Please find a localization sample [here](https://github.com/SyncfusionExamples/Image-Editor-localization-sample-for-native-platforms/tree/main/Localization_Android).