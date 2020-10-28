---
layout: post
title: Technical Indicators
description: How to enable and customize the technical indicator behavior in Essential Xamarin.Android Chart
platform: Xamarin.Android
control: Chart
documentation: ug
---

# Technical Indicators

The different types of technical indicators available in chart are follows:

* [`AverageTrueIndicator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AverageTrueIndicator.html)
* [`SimpleMovingAverageIndicator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SimpleMovingAverageIndicator.html)
* [`RSIIndicator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.RSIIndicator.html)
* [`AccumulationDistributionIndicator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AccumulationDistributionIndicator.html)
* [`MomentumIndicator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.MomentumIndicator.html) 
* [`StochasticIndicator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StochasticIndicator.html)
* [`ExponentialMovingAverageIndicator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ExponentialMovingAverageIndicator.html)
* [`TriangularMovingAverageIndicator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.TriangularMovingAverageIndicator.html)
* [`BollingerBandIndicator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BollingerBandIndicator.html)
* [`MACDIndicator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.MACDIndicator.html)

## Adding technical indicators to chart

The following section illustrates how to add technical indicators to chart.

**Initializing indicator**

Create an instance for any technical indicator, and add it to the [`TechnicalIndicators`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartBase.html#Com_Syncfusion_Charts_ChartBase_TechnicalIndicators) collection.

Here, for an instance, the [`AccumulationDistributionIndicator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AccumulationDistributionIndicator.html) is added.


{% highlight c# %}

[C#] 

SfChart chart = new SfChart();
...
AccumulationDistributionIndicator indicator= new AccumulationDistributionIndicator();

chart.TechnicalIndicators.Add(indicator);

{% endhighlight %}


**Binding data**

Set the item source and binding paths ([`Open`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FinancialTechnicalIndicator.html#Com_Syncfusion_Charts_FinancialTechnicalIndicator_Open), [`High`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FinancialTechnicalIndicator.html#Com_Syncfusion_Charts_FinancialTechnicalIndicator_High), [`Low`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FinancialTechnicalIndicator.html#Com_Syncfusion_Charts_FinancialTechnicalIndicator_Low), [`Close`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FinancialTechnicalIndicator.html#Com_Syncfusion_Charts_FinancialTechnicalIndicator_Close) and [`XBindingPath`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_XBindingPath) to fetch the values from model.



{% highlight c# %}

[C#]

SfChart chart = new SfChart()
{
      ...                
      TechnicalIndicators =
      {
          new AccumulationDistributionIndicator()
          {
              ItemsSource = viewModel.TechnicalIndicatorData,
              XBindingPath = "XValue",
              Open = "Open",
              High = "High",
              Low = "Low",
              Close = "Close"
          }
    }
};

{% endhighlight %}


**Binding the items source of chart series**

By setting [`Name`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_Name) property of [`ChartSeries`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html) to the [`SeriesName`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FinancialTechnicalIndicator.html#Com_Syncfusion_Charts_FinancialTechnicalIndicator_SeriesName) property of [`FinancialTechnicalIndicator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FinancialTechnicalIndicator.html) you can bind the items source of chart series to technical indicators, including x and y axis.


{% highlight c# %}

[C#]

SfChart chart = new SfChart()
{
    ...        
    Series =
      {
          new HiLoOpenCloseSeries()
          {
              ItemsSource = viewModel.TechnicalIndicatorData,
              XBindingPath = "XValue",
              Open = "Open",
              High = "High",
              Low = "Low",
              Close = "Close",
              Name = "OHLC"
          }
    },

    TechnicalIndicators =
      {
          new AccumulationDistributionIndicator()
          {
              SeriesName = "OHLC"              
          }
    }
};

{% endhighlight %}


Technical indicators have the below properties as common; 

 * [`Period`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BollingerBandIndicator.html#Com_Syncfusion_Charts_BollingerBandIndicator_Period) - used to indicates the moving average period.
 * [`SignalLineColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FinancialTechnicalIndicator.html#Com_Syncfusion_Charts_FinancialTechnicalIndicator_SignalLineColor) - used to defines the color for the respective indicator line.
 * [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_StrokeWidth) - used to change the stroke width of the indicator.

**Adding axis**

The [`XAxis`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FinancialTechnicalIndicator.html#Com_Syncfusion_Charts_FinancialTechnicalIndicator_XAxis) and [`YAxis`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FinancialTechnicalIndicator.html#Com_Syncfusion_Charts_FinancialTechnicalIndicator_YAxis) properties of technical indicators are used to set the x and y-axes.

You can define the axis using the following code example.


{% highlight c# %}

[C#]

SfChart chart = new SfChart()
{
    ...        
    TechnicalIndicators =
      {
          new AccumulationDistributionIndicator()
          {
              SeriesName = "OHLC",
              XAxis = new NumericalAxis()
          }
      }
};

{% endhighlight %}


**Animation**

[`SfChart`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SfChart.html) provides animation support for technical indicators. Technical indicators will be animated whenever the ItemsSource changes. Animation can be enabled by setting the [`EnableAnimation`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_EnableAnimation) property to true. You can also control the duration of the animation using the [`AnimationDuration`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ChartSeries.html#Com_Syncfusion_Charts_ChartSeries_AnimationDuration) property.


{% highlight c# %}

[C#]

SfChart chart = new SfChart()
{
    ...        
    TechnicalIndicators =
      {
          new AccumulationDistributionIndicator()
          {
              SeriesName = "OHLC",
              EnableAnimation = true,
              AnimationDuration = 0.8      
          }
      }
};


{% endhighlight %}

## Average true range indicator 

ATR indicator is a technical analysis volatility indicator. This indicator does not provide an indication of price trend; simply the degree of price volatility. The average true range is an N-day smoothed moving average (SMMA) of the true range values.

You can define the [`AverageTrueIndicator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AverageTrueIndicator.html) using the following code example.


{% highlight c# %}

[C#]

SfChart chart = new SfChart()
{
    ...        
    TechnicalIndicators =
      {
          new AverageTrueIndicator()
          {
              Period = 14,
              SignalLineColor = Color.Blue,
              ItemsSource = viewModel.TechnicalIndicatorData,
              XBindingPath = "XValue",
              Open = "Open",
              High = "High",
              Low = "Low",
              Close = "Close",
          }
      }
};

{% endhighlight %}


The following screenshot illustrates an ATR indicator.

![Average true range indicator type in Xamarin.Android Chart](technicalindicators_images/averagetruerange.png)

## Simple moving average indicator

A SMA indicator is a simple, arithmetic moving average that is calculated by adding the closing price for number of time periods and dividing the total value by the number of time periods.

The following code example demonstrates the usage of [`SimpleMovingAverageIndicator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SimpleMovingAverageIndicator.html).

{% highlight c# %}

[C#]

SfChart chart = new SfChart()
{
    ...        
    TechnicalIndicators =
      {
          new SimpleMovingAverageIndicator()
          {
              Period = 14,
              SignalLineColor = Color.Blue,
              ItemsSource = viewModel.TechnicalIndicatorData,
              XBindingPath = "XValue",
              Open = "Open",
              High = "High",
              Low = "Low",
              Close = "Close",
          }
      }
};

{% endhighlight %}


The following screenshot illustrates an SMA indicator.

![Simple moving average indicator type in Xamarin.Android Chart](technicalindicators_images/simplemovingaverage.png)

## Relative strength index indicator

The RSI indicator has additional two lines other than signal line; they indicate the overbought and oversold region.

The [`UpperLineColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.RSIIndicator.html#Com_Syncfusion_Charts_RSIIndicator_UpperLineColor) property is used to define the color for the line that indicates overbought region, and the [`LowerLineColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.RSIIndicator.html#Com_Syncfusion_Charts_RSIIndicator_LowerLineColor) property is used to define the color for the line that indicates oversold region.

To define the [`RSIIndicator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.RSIIndicator.html), use the following code example.

{% highlight c# %}

[C#]

SfChart chart = new SfChart()
{
    ...        
    TechnicalIndicators =
      {
          new RSIIndicator()
          {
              Period = 14,
              SignalLineColor = Color.Blue,
              UpperLineColor = Color.Teal,
              LowerLineColor = Color.Red,
              ItemsSource = viewModel.TechnicalIndicatorData,
              XBindingPath = "XValue",
              Open = "Open",
              High = "High",
              Low = "Low",
              Close = "Close",
          }
      }
};

{% endhighlight %}


The following screenshot illustrates an RSI technical indicator.

![Relative strength index indicator type in Xamarin.Android Chart](technicalindicators_images/relativestrengthindex.png)

## Accumulation distribution indicator

Accumulation distribution indicator is a volume-based indicator designed to measure the accumulative flow of money into and out of a security. It requires [`Volume`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AccumulationDistributionIndicator.html#Com_Syncfusion_Charts_AccumulationDistributionIndicator_Volume) property additionally with the data source to calculate the signal line. 

The following code example helps you to add [`AccumulationDistributionIndicator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.AccumulationDistributionIndicator.html).


{% highlight c# %}

[C#]

SfChart chart = new SfChart()
{
    ...        
    TechnicalIndicators =
      {
          new AccumulationDistributionIndicator()
          {
              SignalLineColor = Color.Blue,
              ItemsSource = viewModel.TechnicalIndicatorData,
              XBindingPath = "XValue",
              Open = "Open",
              High = "High",
              Low = "Low",
              Close = "Close",
              Volume = "Volume"
          }
      }
};

{% endhighlight %}


The following screenshot illustrates an accumulation distribution indicator.

![Accumulation distribution indicator type in Xamarin.Android Chart](technicalindicators_images/accumulationdistribution.png)


## Momentum indicator

This indicator is having two lines, momentum line and center line. The [`SignalLineColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FinancialTechnicalIndicator.html#Com_Syncfusion_Charts_FinancialTechnicalIndicator_SignalLineColor) property and [`UpperLineColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.MomentumIndicator.html#Com_Syncfusion_Charts_MomentumIndicator_UpperLineColor) property is used to define the color for the momentum and center line respectively.
You can define [`MomentumIndicator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.MomentumIndicator.html) using the following code example.


{% highlight c# %}

[C#]

SfChart chart = new SfChart()
{
    ...        
    TechnicalIndicators =
      {
          new MomentumIndicator()
          {
              Period = 14,
              SignalLineColor = Color.Blue,
              UpperLineColor = Color.Red,
              ItemsSource = viewModel.TechnicalIndicatorData,
              XBindingPath = "XValue",
              Open = "Open",
              High = "High",
              Low = "Low",
              Close = "Close",
          }
      }
};


{% endhighlight %}


![Momentum indicator type in Xamarin.Android Chart](technicalindicators_images/momentum.png)

## Stochastic indicator

This indicator is used to measure the range and momentum of price movements. It contains [`KPeriod`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StochasticIndicator.html#Com_Syncfusion_Charts_StochasticIndicator_DPeriod) and [`DPeriod`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StochasticIndicator.html#Com_Syncfusion_Charts_StochasticIndicator_KPeriod) property defining the ‘K’ percentage and ‘D’ percentage respectively. No signal line in this indicator.
The [`UpperLineColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StochasticIndicator.html#Com_Syncfusion_Charts_StochasticIndicator_UpperLineColor), [`LowerLineColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StochasticIndicator.html#Com_Syncfusion_Charts_StochasticIndicator_LowerLineColor) and [`PeriodLineColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StochasticIndicator.html#Com_Syncfusion_Charts_StochasticIndicator_PeriodLineColor) property are used to define the color for the Stochastic indicator lines.
You can define [`StochasticIndicator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.StochasticIndicator.html) using the following code example.

{% highlight c# %}

[C#]

SfChart chart = new SfChart()
{
    ...        
    TechnicalIndicators =
      {
          new StochasticIndicator()
          {
              Period = 14,
              SignalLineColor = Color.Yellow,
              UpperLineColor = Color.Red,
              LowerLineColor = Color.Teal,
              PeriodLineColor = Color.DarkBlue,
              KPeriod = 8,
              DPeriod = 5,
              ItemsSource = viewModel.TechnicalIndicatorData,
              XBindingPath = "XValue",
              Open = "Open",
              High = "High",
              Low = "Low",
              Close = "Close",
          }
      }
};
{% endhighlight %}


![Stochastic indicator type in Xamarin.Android Chart](technicalindicators_images/stochastic.png)

## Exponential moving average indicator

The [`ExponentialMovingAverageIndicator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.ExponentialMovingAverageIndicator.html) is similar to [[`SimpleMovingAverageIndicator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.SimpleMovingAverageIndicator.html) and this can be defined using the following code examples.


{% highlight c# %}

[C#]

SfChart chart = new SfChart()
{
    ...        
    TechnicalIndicators =
      {
          new ExponentialMovingAverageIndicator()
          {
              Period = 14,
              SignalLineColor = Color.Blue,
              ItemsSource = viewModel.TechnicalIndicatorData,
              XBindingPath = "XValue",
              Open = "Open",
              High = "High",
              Low = "Low",
              Close = "Close",
          }
      }
};

{% endhighlight %}


![Exponential moving average indicator type in Xamarin.Android Chart](technicalindicators_images/exponentialmovingavg.png)

## Triangular moving average indicator

A Triangular moving average is simply a double-smoothed simple moving average of data calculated over a period of time where the middle portion of the data has more weight. 
The [`TriangularMovingAverageIndicator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.TriangularMovingAverageIndicator.html) can be defined as in the following code example.


{% highlight c# %}

[C#]

SfChart chart = new SfChart()
{
    ...        
    TechnicalIndicators =
      {
          new TriangularMovingAverageIndicator()
          {
              Period = 14,
              SignalLineColor = Color.Blue,
              ItemsSource = viewModel.TechnicalIndicatorData,
              XBindingPath = "XValue",
              Open = "Open",
              High = "High",
              Low = "Low",
              Close = "Close",
          }
      }
};


{% endhighlight %}


![Triangular moving average indicator type in Xamarin.Android Chart](technicalindicators_images/triangularmovingavg.png)

## Bollinger band indicator

This indicator also having [`UpperLineColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BollingerBandIndicator.html#Com_Syncfusion_Charts_BollingerBandIndicator_UpperLineColor), [`LowerLineColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BollingerBandIndicator.html#Com_Syncfusion_Charts_BollingerBandIndicator_LowerLineColor)  and [`SignalLineColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.FinancialTechnicalIndicator.html#Com_Syncfusion_Charts_FinancialTechnicalIndicator_SignalLineColor) property for defining the brushes for the indicator lines.

Also, we can specify standard deviation values for BollingerBand indicator using [`StandardDeviation`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BollingerBandIndicator.html#Com_Syncfusion_Charts_BollingerBandIndicator_StandardDeviation) property.
You can define the [`BollingerBandIndicator`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.BollingerBandIndicator.html) using the following code example.

{% highlight c# %}

[C#]

SfChart chart = new SfChart()
{
    ...        
    TechnicalIndicators =
      {
          new BollingerBandIndicator()
          {
              Period = 14,
              SignalLineColor = Color.Blue,
              UpperLineColor = Color.Red,
              LowerLineColor = Color.Teal,
              ItemsSource = viewModel.TechnicalIndicatorData,
              XBindingPath = "XValue",
              Open = "Open",
              High = "High",
              Low = "Low",
              Close = "Close",
          }
      }
};


{% endhighlight %}


![Bollinger band indicator type in Xamarin.Android Chart](technicalindicators_images/bollingerband.png)

## MACD indicator

This is mostly using indicator having [`ShortPeriod`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.MACDIndicator.html#Com_Syncfusion_Charts_MACDIndicator_ShortPeriod) and [`LongPeriod`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.MACDIndicator.html#Com_Syncfusion_Charts_MACDIndicator_LongPeriod) for defining the motion of the indicator.
Also you can draw [`Line`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.MACDType.html), [`Histogram`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.MACDType.html) MACD or [`Both`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.MACDType.html) using the [`MACDType`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.MACDIndicator.html#Com_Syncfusion_Charts_MACDIndicator_MACDType) property, which defines the type of MACD to be drawn.

The [`MACDLineColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.MACDIndicator.html#Com_Syncfusion_Charts_MACDIndicator_MACDLineColor) property is used to define the color for the MACD line  and the  [`HistogramColor`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.MACDIndicator.html#Com_Syncfusion_Charts_MACDIndicator_HistogramColor) property is used to define the color for the MACD histogram. The [`Trigger`](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Charts.MACDIndicator.html#Com_Syncfusion_Charts_MACDIndicator_Trigger) property is used to define the trigger period for the indicator.
You can specify the MACD indicator using the following code example.

{% highlight c# %}

[C#]

SfChart chart = new SfChart()
{
    ...        
    TechnicalIndicators =
      {
          new MACDIndicator()
          {
              MACDType = MACDType.Both,
              ShortPeriod = 2,
              LongPeriod = 10,
              Trigger = 14,
              indicator.SignalLineColor = Color.Blue,
              indicator.HistogramColor = Color.LightSkyBlue,
              indicator.MACDLineColor = Color.Orange,
              ItemsSource = viewModel.TechnicalIndicatorData,
              XBindingPath = "XValue",
              Open = "Open",
              High = "High",
              Low = "Low",
              Close = "Close",
          }
      }
};

{% endhighlight %}


![MACD indicator type in Xamarin.Android Chart](technicalindicators_images/macd.png)
