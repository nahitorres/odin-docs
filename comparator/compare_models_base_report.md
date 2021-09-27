---
layout: default
title: compare_models_base_report()
parent: Comparator
nav_order: 1
---

# {{ page.title }}
{: .mb-6}

It summarizes the models performances at all levels of granularity.


#### Parameters
<dl>
  {% for param in site.data.analyses.compare_models_base_report %}

  <dt><strong>{{ param.name }}</strong></dt>
  <dd><br><b><i>{{ param.type }}</i></b></dd><dd>{{ param.description }}</dd>

  {% endfor %}
</dl>

<hr>

### Example

#### Classification
```py
from odin.classes import ComparatorClassification

my_comparator = ComparatorClassification(dataset_gt_param, classification_type, models_proposals)
my_comparator.compare_models_base_report()
```

#### Localization
```py
from odin.classes import ComparatorLocalization

my_comparator = ComparatorLocalization(dataset_gt_param, task_type, models_proposals)
my_comparator.compare_models_base_report()
```

![compare_models_base_report_output](../img/comparator/comparison_base_report.png){:class="img-responsive" width="100%"}
{: .text-center}

N.B. For localization models, the Accuracy and Error Rate evaluation metrics are not supported.
{: .text-right .fs-1}

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
      <td style="background:lightgreen;">yes</td>
      <td style="background:lightgreen;">yes</td>
    </tr>
  </tbody>
</table>
