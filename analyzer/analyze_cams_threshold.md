---
layout: default
title: analyze_cams_threshold()
parent: Analyzer
nav_order: 18
---

# {{ page.title }}
{: .mb-6}

It provides a per-category analysis of the model CAMs at different thresholds.


#### Parameters
<dl>
  {% for param in site.data.analyses.analyze_cams_threshold %}

  <dt><strong>{{ param.name }}</strong></dt>
  <dd><br><b><i>{{ param.type }}</i></b></dd><dd>{{ param.description }}</dd>

  {% endfor %}
</dl>

<hr>

### Example
#### Classification
```py
from odin.classes import AnalyzerCAMs

my_analyzer = AnalyzerCAMs("my_classifier_name", my_CAMs_dataset)
my_analyzer.analyze_cams_threshold()
```

![analyze_cams_output](../img/analyzer/cam_analysis.png){:class="img-responsive;" width="75%"}
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
      <td style="background:lightgreen;">yes</td>
      <td style="background:lightgreen;">yes</td>
      <td style="background:lightgreen;">yes</td>
      <td style="background:lightcoral;">no</td>
      <td style="background:lightcoral;">no</td>
    </tr>
  </tbody>
</table>
