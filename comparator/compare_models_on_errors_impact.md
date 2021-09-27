---
layout: default
title: compare_models_on_errors_impact()
parent: Comparator
nav_order: 4
---

# {{ page.title }}
{: .mb-6}

It compares the false positives by identifying the type of the errors of the models and shows the gain that each model could achieve by removing all the false positives of each type.

#### Parameters
<dl>
  {% for param in site.data.analyses.compare_models_on_errors_impact %}

  <dt><strong>{{ param.name }}</strong></dt>
  <dd><br><b><i>{{ param.type }}</i></b></dd><dd>{{ param.description }}</dd>

  {% endfor %}
</dl>

<hr>

### Example

#### Classification
```py
from odin.classes import ComparatorClassification

similar_categories = [[1, 3], [2, 3]]

my_comparator = ComparatorClassification(dataset_gt_param, classification_type, models_proposals, similar_classes=similar_categories)
my_comparator.compare_models_on_errors_impact()
```

#### Localization
```py
from odin.classes import ComparatorLocalization

my_comparator = ComparatorLocalization(dataset_gt_param, task_type, models_proposals, similar_classes=similar_categories)
my_comparator.compare_models_on_errors_impact()
```

![compare_models_on_curve_output](../img/comparator/comparison_errors_a.png){:class="img-responsive" width="75%"}
{: .text-center}

![compare_models_on_curve_output](../img/comparator/comparison_errors_b.png){:class="img-responsive" width="75%"}
{: .text-center}

![compare_models_on_curve_output](../img/comparator/comparison_errors_c.png){:class="img-responsive" width="75%"}
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
      <td style="background:lightgreen;">yes</td>
      <td style="background:lightgreen;">yes</td>
      <td style="background:lightgreen;">yes</td>
      <td style="background:lightgreen;">yes</td>
    </tr>
  </tbody>
</table>
