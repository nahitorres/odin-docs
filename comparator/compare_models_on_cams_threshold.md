---
layout: default
title: compare_models_on_cams_threshold()
parent: Comparator
nav_order: 11
---

# {{ page.title }}
{: .mb-6}

It compares the CAMs of the models at different threshold values.


#### Parameters
<dl>
  {% for param in site.data.analyses.compare_models_on_cams_threshold %}

  <dt><strong>{{ param.name }}</strong></dt>
  <dd><br><b><i>{{ param.type }}</i></b></dd><dd>{{ param.description }}</dd>

  {% endfor %}
</dl>

<hr>

### Example

#### Classification
```py
from odin.classes import ComparatorCAMs

my_comparator = ComparatorCAMs(dataset_gt_param, classification_type, models_proposals)
my_comparator.compare_models_on_cams_threshold()
```

![compare_models_on_cams_threshold_output](../img/comparator/comparison_cams.png){:class="img-responsive" width="75%"}
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
