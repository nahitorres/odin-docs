---
layout: default
title: analyze_top1_top5_error()
parent: Analyzer
nav_order: 10
---

# {{ page.title }}
{: .mb-6}


It analyzes the model performances by considering the top-1 and the top-5 classification predictions. The analysis can be performed for the entire data set or for a subset with a specific property value.


#### Parameters
<dl>
  {% for param in site.data.analyses.analyze_top1_top5_error %}

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
my_analyzer.analyze_top1_top5_error()
```

![analyze_top_output_a](../img/analyzer/top_analysis.png){:class="img-responsive" width="75%"}
{: .text-center}

```py
from odin.classes import AnalyzerClassification

my_analyzer = AnalyzerClassification("my_classifier_name", my_classification_dataset)
my_analyzer.analyze_top1_top5_error(properties=['prop1'])
```

![analyze_top_output_b](../img/analyzer/top_analysis_prop.png){:class="img-responsive" width="75%"}
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
      <td style="background:lightcoral;">no</td>
      <td style="background:lightcoral;">no</td>
      <td style="background:lightcoral;">no</td>
    </tr>
  </tbody>
</table>
