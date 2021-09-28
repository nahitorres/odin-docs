---
layout: default
title: show_distribution_of_property_for_category()
parent: Dataset
nav_order: 2
---

# {{ page.title }}
{: .mb-6}

It provides the distribution of a property for a specific category.


#### Parameters
<dl>
  {% for param in site.data.analyses.show_distribution_of_property_for_category %}

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
my_dataset.show_distribution_of_property_for_category('prop1', 'catA')
```
#### Localization
```py
from odin.classes import DatasetLocalization

my_dataset = DatasetLocalization(dataset_gt_param, localization_type)
my_dataset.show_distribution_of_property_for_category('prop1', 'catA')
```

![show_distribution_of_properties_output](../img/dataset/distribution_prop_for_cat_a.png){:class="img-responsive" width="75%"}
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
