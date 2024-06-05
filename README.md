# AndroidLabelLineBreakExtraSpace MAUI Bug

## Problem

<b>Current Behavior</b>:

When using the `LineBreakMode="WordWrap"` property on a `Label` in a `Grid` in a MAUI app, the `Label` will have extra space at the end of the text on Android where the line breaks.

<b>Expected Behavior</b>:

The `Label` should not have extra space at the end of the text on Android where the line breaks and should be resized to fit the width of the text.

<i>This does not happen on iOS</i>.

## Repro

Add the following XAML to a ContentPage app:

```xml
<Grid
    Margin="24"
    ColumnDefinitions="*,auto,auto"
    HorizontalOptions="Center"
    VerticalOptions="Start"
    ColumnSpacing="2">

    <Label
      BackgroundColor="DarkSlateGray"
      Grid.Column="0"
      HorizontalOptions="Start"
      LineBreakMode="WordWrap"
      LineHeight="1"
      FontSize="Caption"
      Text="Svorna, Mikeondoko Nananom Dadadadodo Septop"
      VerticalOptions="Start"
      VerticalTextAlignment="Start" />

    <Label
      BackgroundColor="DarkGreen"
      Grid.Column="1"
      Text=" • "
      LineHeight="1"
      FontSize="Caption"
      VerticalOptions="Start"
      HorizontalOptions="Center"
      HorizontalTextAlignment="Center"
      VerticalTextAlignment="Start" />

    <Label
      BackgroundColor="DarkRed"
      Grid.Column="2"
      LineHeight="1"
      FontSize="Caption"
      Text="May 32-Jun 33, 2069"
      VerticalOptions="Start"
      VerticalTextAlignment="Start" />

</Grid>
```

## Screenshots

<b>Android - note the large extra space highlighted in red:<b>

<img src="https://github.com/ewerspej/AndroidLabelLineBreakExtraSpace/blob/main/screenshots/android_highlight.png?raw=true" width="300" />

<b>iOS - here it's correct:</b>

<img src="https://github.com/ewerspej/AndroidLabelLineBreakExtraSpace/blob/main/screenshots/ios_correct.png?raw=true" width="300" />