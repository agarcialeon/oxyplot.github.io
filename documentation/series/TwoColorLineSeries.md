---
layout: page
title: TwoColorLineSeries
---

A `TwoColorLineSeries` shows a line where the the color is different above and below a specified limit.

![TwoColorLineSeries](/public/images/documentation/series/TwoColorLineSeries.png)


### Tracker

The `TrackerFormatString` property is used to format the string shown in the [tracker](../tracker). The format string may use the following arguments:

- `{0}` the title of the series
- `{1}` the title of the x-axis
- `{2}` the x-value
- `{3}` the title of the y-axis
- `{4}` the y-value

To show the x and y values with one digit, use the format string `"{2:0.0},{4:0.0}"`.

If an item was hit, it is also possible to use the extended format string syntax, e.g. `{PropertyX:0.##}`, where the value of `PropertyX` will be found by reflection of the item.

The default format string for `TwoColorLineSeries` is `"{0}\n{1}: {2:0.###}\n{3}: {4:0.###}"`

See [MSDN](http://msdn.microsoft.com/en-us/library/system.string.format(v=vs.110).aspx) for more information about format strings.

The `TrackerKey` property may be used to specify a [custom tracker](../tracker). This makes it possible to use different trackers for each series.


### Example

``` csharp
var model = new PlotModel { Title = "TwoColorLineSeries" };
```