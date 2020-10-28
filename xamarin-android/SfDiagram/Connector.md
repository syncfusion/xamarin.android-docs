---
title: Adding connectors in Xamarin.Android diagram control | Syncfusion
description: Describes how to add connector,connection with node and it's appearance in diagram control for Xamarin.Android
platform: Xamarin.Android
control: SfDiagram
documentation: UG
keywords: 
---
# Connector in Xamarin.Android Diagram
The connectors are objects used to create link between two points. Nodes or ports are used to represent the relationship between them.

## Create connector
The connector can be created by defining the start and end points.
{% tabs %}
{% highlight c# %}
//creating connector instance
Connector Connector1 = new Connector(this);
Connector1.SourcePoint = new System.Drawing.PointF(100, 100);
Connector1.TargetPoint = new System.Drawing.PointF(300, 300);
diagram.AddConnector(Connector1);
{% endhighlight %}
{% endtabs %}

## Connections with nodes
The SourceNode and TargetNode properties allows to define the nodes to be connected. The following code example illustrates how to connect two nodes:
{% tabs %}
{% highlight c# %}
// creating node  instance
Node node = new Node(this);
node.OffsetX = 100;
node.OffsetY = 300;
node.Height = 100;
node.Width = 100;
diagram.AddNode(node);
Node node2 = new Node(this);
node2.OffsetX = 300;
node2.OffsetY = 300;
node2.Height = 100;
node2.Width = 100;
diagram.AddNode(node2);
// creating connector instance and connecting nodes with it
Connector connector = new Connector(this);
connector.SourceNode = node;
connector.TargetNode = node2;
diagram.AddConnector(connector);
{% endhighlight %}
{% endtabs %}
![Connections with nodes in Xamarin.Android diagram](Connector_images/Connector_img1.jpeg)

## Connections with ports
The SourcePort and TargetPort properties allows to create connections between some specific points of source or target nodes.

## Using port
The following code example illustrates how to create and connect the ports:
{% tabs %}
{% highlight c# %}
// creating node instance
Node node = new Node(this);
node.OffsetX = 100;
node.OffsetY = 100;
node.Height = 100;
node.Width = 100;
//adding port instance to the node
node.Ports.Add(new Port() { NodeOffsetX = 0.5, NodeOffsetY = 0 });
diagram.AddNode(node);
Node node2 = new Node(this);
node2.OffsetX = 300;
node2.OffsetY = 300;
node2.Height = 100;
node2.Width = 100;
//adding port instance to the node
node2.Ports.Add(new Port() { NodeOffsetX = 0.5, NodeOffsetY = 1});
diagram.AddNode(node2);
//creating and connecting the ports with connector
Connector connector = new Connector(this);
connector.SourceNode = node;
connector.TargetNode = node2;
connector.SourcePort = node.Ports[0];
connector.TargetPort = node2.Ports[0];
connector.SegmentType = SegmentType.OrthoSegment;
diagram.AddConnector(connector);
{% endhighlight %}
{% endtabs %}
![Using port in Xamarin.Android diagram](Connector_images/Connector_img2.jpeg)

## Segments
The path of the connector is defined with a collection of segments.

## Straight
The straight segment allows to create a straight line. To create a straight line, you should specify the segment as StraightSegment. The following code example illustrates how to create a default straight segment:
{% tabs %}
{% highlight c# %}
// creating connector instance with define its segment type
Connector connector = new Connector(this);
connector.SourcePoint = new System.Drawing.PointF(100, 100);
connector.TargetPoint = new System.Drawing.PointF(300, 300);
connector.SegmentType = SegmentType.StraightSegment;
diagram.AddConnector(connector);
{% endhighlight %}
{% endtabs %}
![Straight connector in Xamarin.Android diagram](Connector_images/Connector_img3.jpeg)

## Orthogonal
The orthogonal segments are used to create segments that are perpendicular to each other.
Set the segment as OrthogonalSegment to create the default orthogonal segment. The following code example illustrates how to create a default orthogonal segment:
{% tabs %}
{% highlight c# %}
// creating connector instance with define its segment type
Connector connector = new Connector(this);
connector.SourcePoint = new System.Drawing.PointF(100, 100);
connector.TargetPoint = new System.Drawing.PointF(300, 300);
connector.SegmentType = SegmentType.OrthoSegment;
diagram.AddConnector(connector);
{% endhighlight %}
{% endtabs %}
![Orthogonal connector in Xamarin.Android diagram](Connector_images/Connector_img4.jpeg)

## Curve
Curve segments are used to create links between two points, nodes or ports with curve segments. The following code example illustrates how to create a default curve segment.
{% tabs %}
{% highlight c# %}
// creating connector instance with define its segment type
Connector connector = new Connector(this);
connector.SourcePoint = new System.Drawing.PointF(100, 100);
connector.TargetPoint = new System.Drawing.PointF(300, 300);
connector.SegmentType = SegmentType.CurveSegment;
diagram.AddConnector(connector);
{% endhighlight %}
{% endtabs %}
![Curve connector in Xamarin.Android diagram](Connector_images/Connector_img5.jpeg)

## Bezier 
Bezier curve has cubic curve segments that are configurable with the control points. The “SourceControlPoint” and “TargetControlPoint” of bezier segment allow you to modify the control points. The following code example illustrates how to create and modify a bezier curve segment via control points.
{% tabs %}
{% highlight c# %}
Connector connector = new Connector(this);
connector.SourcePoint = new System.Drawing.PointF(100, 100);
connector.TargetPoint = new System.Drawing.PointF(300, 300);
connector.SourceControlPoint = new System.Drawing.PointF(100, 175);
connector.TargetControlPoint = new System.Drawing.PointF(316, 175);
connector.SegmentType = SegmentType.BezierSegment;
diagram.AddConnector(connector);

{% endhighlight %}
{% endtabs %}
![BEzier connector in Xamarin.Android diagram](Connector_images/Connector_img6.jpeg)

## Decorator
The start and end points of a connector can be decorated with some customizable shapes like arrow, circle, diamond, and square. You can decorate the connection end points with the SourceDecorator and TargetDecorator properties of connector.
The SourceDecoratorStyle and TargetDecoratorStyle properties define the shape of the decorators. The following code example illustrates how to create decorators of various shapes:
{% tabs %}
{% highlight c# %}
//creating connector instance with decorator
Connector connector = new Connector(this);
connector.SourcePoint = new System.Drawing.PointF(100, 100);
connector.TargetPoint = new System.Drawing.PointF(300, 300);
connector.SourceDecoratorType = DecoratorType.Circle;
connector.TargetDecoratorType = DecoratorType.Diamond;
connector.SegmentType = SegmentType.StraightSegment;
diagram.AddConnector(connector);
{% endhighlight %}
{% endtabs %}
![Connector Decorator in Xamarin.Android diagram](Connector_images/Connector_img7.jpeg)

## Remove connector
There are two ways to remove connector from the connection, they are the following:
1.Passing the connector as parameter to remove connector method in the diagram.
The following code example illustrates how to remove a connector from the connection:
{% tabs %}
{% highlight c# %}
//creating connector instance
Connector connector = new Connector(this);
connector.SourcePoint = new System.Drawing.PointF(100, 100);
connector.TargetPoint = new System.Drawing.PointF(300, 300);
//adding connector to the diagram
diagram.AddConnector(connector);
//removing connector from the diagram using object.
diagram.RemoveConnector(connector);
{% endhighlight %}
{% endtabs %}
2.Passing the index value of the connector to remove connector method in the diagram (using RemoveAt method).
The following code example illustrates how to remove a connector from connection:
{% tabs %}
{% highlight c# %}
Connector connector = new Connector(this);
connector.SourcePoint = new System.Drawing.PointF(100, 100);
connector.TargetPoint = new System.Drawing.PointF(300, 300);
//adding connector to the diagram
diagram.AddConnector(connector);
//removing connector from the diagram using index. 
diagram.Connectors.RemoveAt(0);
{% endhighlight %}
{% endtabs %}

## Appearance
The StrokeThickness, Stroke are the set of properties. The style of line connectors  and decorators can be customized with that properties.

## Connector appearance
The following code example illustrates how to customize the connector appearance.
{% tabs %}
{% highlight c# %}
//creating connector instance
Connector connector = new Connector(this);
connector.SourcePoint = new System.Drawing.PointF(100, 100);
connector.TargetPoint = new System.Drawing.PointF(300, 300);
//defining connector styles
connector.Style = new Style()
{
  StrokeBrush = new SolidBrush(Color.Gray),
  StrokeStyle = StrokeStyle.Dashed,
  StrokeWidth = 4
};
diagram.AddConnector(connector);
{% endhighlight %}
{% endtabs %}
![Connector appearance in Xamarin.Android diagram](Connector_images/Connector_img8.jpeg)

## Decorator appearance
The following code example illustrates how to customize the appearance of the decorator:
{% tabs %}
{% highlight c# %}
// creating connector instance with decorator
Connector connector = new Connector(this);
connector.SourcePoint = new System.Drawing.PointF(100, 100);
connector.TargetPoint = new System.Drawing.PointF(300, 300);
connector.SegmentType = SegmentType.StraightSegment;
connector.SourceDecoratorType = DecoratorType.Circle;
connector.TargetDecoratorType = DecoratorType.Diamond;
// defining decorator style for a connector
connector.TargetDecoratorStyle = new DecoratorStyle()
{
  Fill = Color.Yellow,
  StrokeColor = Color.Brown,
  StrokeWidth = 4,
  Size = 12
};
// defining decorator style for a connector
connector.SourceDecoratorStyle = new DecoratorStyle()
{
  Fill = Color.Green,
  StrokeColor = Color.Gray,
  StrokeWidth = 5,
  Size = 12
};
diagram.AddConnector(connector);
{% endhighlight %}
{% endtabs %}
![Decorator appearance in Xamarin.Android diagram](Connector_images/Connector_img9.jpeg)

