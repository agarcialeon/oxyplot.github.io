---
layout: page
title: WPF example (VB.NET)
---

This example shows how to create a WPF application in VB.NET where the content of the plot is defined in code.

Create a new VB.NET Windows/WPF project and add a reference to the OxyPlot.Wpf NuGet package. Then create a view model class:

```
@include ..\Source\Examples\WPF\SimleDemoVB\MainViewModel.vb
```

and edit the main window XAML:

``` xml
@include ..\Source\Examples\WPF\SimleDemoVB\MainWindow.xaml
```

The example is included in `..\Source\Examples\WPF\SimleDemoVB`.