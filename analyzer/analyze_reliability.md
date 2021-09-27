---
layout: default
title: analyze_reliability()
parent: Analyzer
nav_order: 9
---

# {{ page.title }}
{: .mb-6}


It provides the reliability analysis by showing the distribution of the proposals among different confidence values and the corresponding confidence calibration.


#### Parameters
<dl>
  {% for param in site.data.analyses.analyze_reliability %}

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
my_analyzer.analyze_reliability()
```
![analyze_reliability_cl_output](../img/analyzer/reliability_analysis_cl.png){:class="img-responsive" width="100%"}
{: .text-center}

#### Localization
```py
from odin.classes import AnalyzerLocalization

my_analyzer = AnalyzerLocalization("my_detector_name", my_localization_dataset)
my_analyzer.analyze_reliability()
```

![analyze_reliability_loc_output](../img/analyzer/reliability_analysis_loc.png){:class="img-responsive" width="100%"}
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
