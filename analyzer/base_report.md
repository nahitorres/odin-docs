---
layout: default
title: base_report()
parent: Analyzer
nav_order: 1
---

# {{ page.title }}
{: .mb-6}

It summarizes all the performance scores of the model at all levels of granularity: it provides the overall scores, the per-category scores and the per-property scores.

#### Parameters
<dl>
  {% for param in site.data.analyses.base_report %}

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
my_analyzer.base_report()
```

#### Localization
```py
from odin.classes import AnalyzerLocalization

my_analyzer = AnalyzerLocalization("my_detector_name", my_localization_dataset)
my_analyzer.base_report()
```

![base_report_output](../img/analyzer/base_report.png){:class="img-responsive" width="75%"}
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
