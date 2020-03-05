```eval_rst
:github_url: https://github.com/littlevgl/docs/blob/master/en/object-types/gauge.md
```
# Gauge (lv_gauge)

## Overview
The gauge is a meter with scale labels and one or more needles.

## Parts and Styles
The Gauge's main part is called `LV_GAUGE_PART_MAIN`.vIt draws a background using the typical background style properties and "minor" scale lines using the *line* and *scale* style properties.
It also uses the *text* properties to set the style of teh scale labels. *pad_inner* is used to set space between the scale lines and the scale labels. 

`LV_GAUGE_PART_MAJOR` is a virtual part which describes the  major scale lines (where labels are added) useing the *line* and *scale* style properties.

`LV_GAUGE_PART_NEEDLE` is also virtual part and it describes the needle(s) via the *line* style proeprties. *size* and the typical background proeprties are used to describe a rectangle (or circle) i nthe picot point of the needle(s).
*pad_inner* is used to to make the needle(s) smaller thn the outter radius of the scale lines.

## Usage

### Set value and needles
The gauge can show more than one needle.
Use the `lv_gauge_set_needle_count(gauge, needle_num, color_array)` function to set the number of needles and an array with colors for each needle. 
The array must be static or global variable because only its pointer is stored.

You can use `lv_gauge_set_value(gauge, needle_id, value)` to set the value of a needle.


### Scale
You can use the `lv_gauge_set_scale(gauge, angle, line_num, label_cnt)` function to adjust the scale angle and the number of the scale lines and labels.
The default settings are 220 degrees, 6 scale labels, and 21 lines.

The scale of the Gauge can have offset. It can be adjusted with `lv_gauge_set_angle_offset(gauge, angle)`.

### Range
The range of the gauge can be specified by `lv_gauge_set_range(gauge, min, max)`. The default range is 0..100.

### Critical value
To set a critical value, use `lv_gauge_set_critical_value(gauge, value)`. The scale color will be changed to *scale_end_color* after this value. The default critical value is 80.

## Events
Only the [Generic events](/overview/event.html#generic-events) are sent by the object type.

Learn more about [Events](/overview/event).

## Keys
No *Keys* are processed by the object type.

Learn more about [Keys](/overview/indev).

## Example

```eval_rst

.. include:: /lv_examples/src/lv_ex_widgets/lv_ex_gauge/index.rst

```
## API

```eval_rst

.. doxygenfile:: lv_gauge.h
  :project: lvgl

```
