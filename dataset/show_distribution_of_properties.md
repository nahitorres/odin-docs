---
layout: default
title: show_distribution_of_properties()
parent: Dataset
nav_order: 4
---

# {{ page.title }}
{: .mb-6}

For each property, it provides the distribution of its different values and for each value shows the
distribution of the categories.


#### Parameters
<dl>
  {% for param in site.data.analyses.show_distribution_of_properties %}

  <dt><strong>{{ param.name }}</strong></dt>
  <dd><br><b><i>{{ param.type }}</i></b></dd><dd>{{ param.description }}</dd>

  {% endfor %}
</dl>

<hr>

### Example
#### Classification
```py
from odin.classes import DatasetClassification

my_dataset = DatasetClassification(dataset_gt_param, classification_type)
my_dataset.show_distribution_of_properties()
```
#### Localization
```py
from odin.classes import DatasetLocalization

my_dataset = DatasetLocalization(dataset_gt_param, localization_type)
my_dataset.show_distribution_of_properties()
```

![show_distribution_of_properties_output](../img/dataset/distribution_prop.png){:class="img-responsive" width="75%"}
{: .text-center}

![show_distribution_of_properties_output](../img/dataset/distribution_prop_in_cats_a.png){:class="img-responsive" width="75%"}
{: .text-center}

![show_distribution_of_properties_output](../img/dataset/distribution_prop_in_cats_b.png){:class="img-responsive" width="75%"}
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
      <td style="background:lightgreen;">yes</td>
      <td style="background:lightgreen;">yes</td>
    </tr>
  </tbody>
</table>
