---
layout: default
title: F1 AUC
parent: Metrics and Curves
nav_order: 9
---

# {{ page.title }}
{: .mb-6}

{{ site.data.metrics[page.title].description }}


### Example


```py
from odin.classes import Metrics

my_metric = Metrics.F1_AUC
# use my_metric as 'metric' parameter in the analyses
```

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
      <td style="background:lightgreen;">yes</td>
      <td style="background:lightgreen;">yes</td>
    </tr>
  </tbody>
</table>
