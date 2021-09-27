---
layout: default
title: analyze_false_positive_errors()
parent: Analyzer
nav_order: 6
---

# {{ page.title }}
{: .mb-6}

For each class, it analyzes the false positives by identifying the type of the errors and shows the gain that the model could achieve by removing all the false positives of each type.

#### Parameters
<dl>
  {% for param in site.data.analyses.analyze_false_positive_errors %}

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
my_analyzer.analyze_false_positive_errors()
```
![analyze_false_positive_errors_cl_output_a](../img/analyzer/false_positive_category_distribution_cl.png){:class="img-responsive" width="75%"}
{: .text-center}
![analyze_false_positive_errors_cl_output_b](../img/analyzer/false_positive_category_gain_cl.png){:class="img-responsive" width="75%"}
{: .text-center}

<p style="font-size: 10px; text-align: right;">N.B. As example, it is shown only the output of a single category, but the analysis is performed for all the categories selected.</p>

#### Localization
```py
from odin.classes import AnalyzerLocalization

my_analyzer = AnalyzerLocalization("my_detector_name", my_localization_dataset)
my_analyzer.analyze_false_positive_errors()

```

![analyze_false_positive_errors_loc_output_a](../img/analyzer/false_positive_category_distribution_loc.png){:class="img-responsive" width="75%"}
{: .text-center}
![analyze_false_positive_errors_loc_output_b](../img/analyzer/false_positive_category_gain_loc.png){:class="img-responsive" width="75%"}
{: .text-center}

N.B. As example, it is shown only the output of a single category, but the analysis is performed for all the categories selected.
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
      <td style="background:lightcoral;">no</td>
      <td style="background:lightgreen;">yes</td>
      <td style="background:lightgreen;">yes</td>
      <td style="background:lightgreen;">yes</td>
      <td style="background:lightgreen;">yes</td>
    </tr>
  </tbody>
</table>
