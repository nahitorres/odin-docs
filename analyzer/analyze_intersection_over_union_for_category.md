---
layout: default
title: analyze_intersection_over_union_for_category()
parent: Analyzer
nav_order: 12
---

# {{ page.title }}
{: .mb-6}

It provides a per-category analysis of the model performances at different Intersection Over Union (IoU) thresholds.

#### Parameters
<dl>
  {% for param in site.data.analyses.analyze_intersection_over_union_for_category %}

  <dt><strong>{{ param.name }}</strong></dt>
  <dd><br><b><i>{{ param.type }}</i></b></dd><dd>{{ param.description }}</dd>

  {% endfor %}
</dl>

<hr>

### Example
#### Localization
```py
from odin.classes import AnalyzerLocalization

my_analyzer = AnalyzerLocalization("my_detector_name", my_localization_dataset)
my_analyzer.analyze_intersection_over_union_for_category('catA')
```

![analyze_iou_cat_output](../img/analyzer/iou_analysis_cat.png){:class="img-responsive"}
{: .text-center}

<hr>

### Tasks supported
<table>
  <thead>
    <tr class="header">
      <th>Binary Classification</th>
      <th>Single-label Classification</th>
      <th>Multi-label Classification</th>
      <th>Object Detection</th>
      <th>Instance Segmentation</th>
    </tr>
  </thead>
  <tbody>
    <tr style="text-align:center;">
      <td style="background:lightcoral;">no</td>
      <td style="background:lightcoral;">no</td>
      <td style="background:lightcoral;">no</td>
      <td style="background:lightgreen;">yes</td>
      <td style="background:lightgreen;">yes</td>
    </tr>
  </tbody>
</table>
