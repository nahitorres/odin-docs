---
layout: default
title: analyze_properties()
parent: Analyzer
nav_order: 3
---

# {{ page.title }}
{: .mb-6}

For each property, the model performances are analyzed for each category considering subsets of the data set which have a specific property value.


#### Parameters
<dl>
  {% for param in site.data.analyses.analyze_properties %}

  <dt><strong>{{ param.name }}</strong></dt>
  <dd><br><b><i>{{ param.type }}</i></b></dd><dd>{{ param.description }}</dd>

  {% endfor %}
</dl>

<hr>

### Example

#### Classification
```py
from odin.classes import AnalyzerClassification

my_analyzer = AnalyzerClassification("my_classifier_name", my_classification_dataset)
my_analyzer.analyze_properties()
```

#### Localization
```py
from odin.classes import AnalyzerLocalization

my_analyzer = AnalyzerLocalization("my_detector_name", my_localization_dataset)
my_analyzer.analyze_properties()
```

![analyze_properties_output_a](../img/analyzer/Analysis_of_prop1_property.png){:class="img-responsive" width="75%"}
{: .text-center}
![analyze_properties_output_b](../img/analyzer/Analysis_of_prop2_property.png){:class="img-responsive" width="75%"}
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
