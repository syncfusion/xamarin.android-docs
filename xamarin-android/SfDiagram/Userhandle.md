---
title: Adding userhandles in Xamarin.Android Diagram | Syncfusion
description: Learn how to add userhandles ,userhandles customization and its event handle in diagram for Xamarin.Android
platform: Xamarin.Android
control: SfDiagram
documentation: UG
keywords: 
---
# User handles in Xamarin.Android diagram
User handles are customizable handles which can be used to perform custom actions and also default clipboard actions. You can able to customize the user handles using:
* SfGraphicPath
* Image
* View
The following code illustrates how to add custom user handle in diagram:
{% tabs %}
{% highlight c# %}
//Add graphic path into user handle
SfGraphics graph = new SfGraphics();
Pen stroke = new Pen();
stroke.Brush = new SolidBrush(Color.Transparent);
stroke.StrokeWidth = 3;
stroke.StrokeBrush = new SolidBrush(Color.Rgb(24, 161, 237));
graph.DrawEllipse(stroke, new System.Drawing.Rectangle(10, 0, 20, 20));
graph.DrawArc(stroke, 0, 20, 40, 40, 180, 180);
diagram.UserHandles.Add(new Syncfusion.SfDiagram.Android.UserHandle("SfGraphicsPath", UserHandlePosition.Right, graph) { BackgroundColor = Color.Transparent });

//Add image into user handle
var image = new ImageView(this);
image.SetImageResource(Resource.Drawable.delete);
diagram.UserHandles.Add(new Syncfusion.SfDiagram.Android.UserHandle("Delete", UserHandlePosition.Bottom, image));

//Add View into user handle
var view = new View(this);
view.SetBackgroundColor(Color.Purple);
diagram.UserHandles.Add(new Syncfusion.SfDiagram.Android.UserHandle("View", UserHandlePosition.Left, view));


{% endhighlight %}
{% endtabs %}

## User handles clicked event
The following code illustrate how to define user handles clicked event and its action.
{% tabs %}
{% highlight c# %}
//User handles clicked event
diagram.UserHandleClicked += Diagram_UserHandleClicked;

private void Diagram_UserHandleClicked(object sender, UserHandleClickedEventArgs args)
{
    if (args.Item.Name == "Delete")
    {
        diagram.Delete();
    }
}
{% endhighlight %}
{% endtabs %}
![Userhandle in Xamarin.Android diagram](Userhandle_images/Userhandle_img1.jpeg)

## Customizing user handle position
User handle position can be moved or adjusted from its default position. The following code shows how to adjust the position using the “MoveBy” method.
{% tabs %}
{% highlight c# %}
     //Define the user handle 

            UserHandleCollection userHandles = new UserHandleCollection();
            UserHandle left = new UserHandle("Left", UserHandlePosition.Left, plusTemplate) { Visible = true };
     //Customize the user handle position using move by method
            left.MoveBy(-10, -10);
            userHandles.Add(left);
            userHandles.Add(new UserHandle("Right", UserHandlePosition.Right, m_expandTemplate) { Visible = true });
            userHandles.Add(new UserHandle("Delete", UserHandlePosition.Bottom, deleteTemplate) { Visible = true });
            diagram.UserHandles = userHandles;
{% endhighlight %}
{% endtabs %}
![customize user handle position in Xamarin.Android diagram](Userhandle_images/Userhandle_img2.jpeg)

