# How to display more data information in the tooltip of UWP Charts

The [UWP Chart](https://www.syncfusion.com/uwp-ui-controls/charts) provides the support to display the needed information from its model of populated items source along with the Tooltip UI customization with the help of [TooltipTemplate](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_TooltipTemplate) in chart series as shown in the following code example.

Here, display both country name and its population details in the tooltip. By default, it displays the corresponding y-axis value of that segment.

```
<Page.DataContext>
      <local:ViewModel/>
</Page.DataContext>
<Page.Resources>
    <DataTemplate x:Key="tooltipTemplate">
        <StackPanel Orientation="Horizontal">
            <!--Template element has DataContext as its Segment named Item. From it, you can access the correponding Model-->
            <TextBlock  FontFamily="Segoe UI"  Foreground="White">
                  <Run Text="{Binding Item.Country}"/>
                  <Run Text=":"/>  
                  <Run Text="{Binding Item.Population}"/>
            </TextBlock>
        </StackPanel>
    </DataTemplate>
</Page.Resources>
<StackPanel Margin="40">
    <syncfusion:SfChart Header="Population growth" Width="353" Height="298">
        <syncfusion:SfChart.PrimaryAxis>
            <syncfusion:CategoryAxis/>
        </syncfusion:SfChart.PrimaryAxis>
        <syncfusion:SfChart.SecondaryAxis>
            <syncfusion:NumericalAxis/>
        </syncfusion:SfChart.SecondaryAxis>
        <syncfusion:ColumnSeries 
                     ItemsSource="{Binding Data}"
                     XBindingPath="Country"
                     YBindingPath="Population"
                     ShowTooltip="True"
                     TooltipTemplate="{StaticResource tooltipTemplate}"/>
    </syncfusion:SfChart>
</StackPanel>
```

## Output:

![Tooltip with more data in UWP chart](https://github.com/SyncfusionExamples/How-to-display-more-data-information-in-the-tooltip-of-UWP-Charts/blob/main/UWP_Chart_Tooltip_Customization.gif)

KB article - [](https://www.syncfusion.com/kb/12482/how-to-display-more-data-in-the-tooltip-of-uwp-charts)

## See also

[How to set the duration for chart tooltip](https://www.syncfusion.com/kb/6161/how-to-set-the-duration-for-chart-tooltip)

[How to view the tooltip when the segment is underneath the axis line](https://www.syncfusion.com/kb/6151/how-to-view-the-tooltip-when-segment-is-underneath-the-axis-line)

[How to change the alignment of chart tooltip](https://help.syncfusion.com/uwp/charts/interactive-features#aligning-the-tooltip)
