---
layout: page
title: Xamarin.Forms example
---

This example shows how to create a [Xamarin.Forms][forms] app where both the user interface and the plot is defined in portable code.

### Create the project

Start Visual Studio and select the blank Xamarin.Forms app template.

### Update and add references

Update the `Xamarin.Forms` NuGet packages to the latest version (at least version 1.3.1).

Add the `OxyPlot.Xamarin.Forms` NuGet package in both the portable and platform specific projects.

### Initialize renderers

You need to initialize the OxyPlot renderers by adding the following call just before `Xamarin.Forms.Forms.Init()`:

- iOS (Unified API): `OxyPlot.Xamarin.Forms.Platform.iOS.Forms.Init();`
- Android: `OxyPlot.Xamarin.Forms.Platform.Android.Forms.Init();`
- WinPhone: `OxyPlot.Xamarin.Forms.Platform.WinPhone.Forms.Init();`

### Add the `PlotView` to a page (in code)

In the portable/shared app project, add the plot view to a page:

``` csharp
public App()
{
    this.MainPage = new ContentPage
    {
        Content = new PlotView
        {
            Model = new PlotModel { Title = "Hello, Forms!" },
            VerticalOptions = LayoutOptions.Fill,
            HorizontalOptions = LayoutOptions.Fill,
        },
    };
}
```

### Add the `PlotView` to a page (XAML)

Add a "Forms Xaml Page" to your project. In the page element, add a namespace declaration:

``` xml
xmlns:oxy="clr-namespace:OxyPlot.Xamarin.Forms;assembly=OxyPlot.Xamarin.Forms"
```

Then add the plot view:

``` xml
<oxy:PlotView Model="{Binding Model}" VerticalOptions="Center" HorizontalOptions="Center" />
```

This view will now be bound to a `PlotModel` in the binding context of the page.

### References

The source code can be found in the [HelloWorld\XamarinFormsApp1](https://github.com/oxyplot/documentation-examples/tree/master/HelloWorld/XamarinFormsApp1) folder in the [documentation-examples](https://github.com/oxyplot/documentation-examples) repository.

[forms]: http://xamarin.com/forms