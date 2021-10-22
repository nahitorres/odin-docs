---
layout: default
title: Performance Summary
parent: Analyses
grand_parent: Analyzer
nav_order: 1
---

# {{page.title}}
{: .no_toc}

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
- TOC
{:toc}
</details>

<hr>

# base_report()
{: .mb-6}

It summarizes all the performance scores of the model at all levels of granularity: it provides the overall scores, the per-category scores and the per-property scores.

#### Parameters
{: .no_toc}
<dl>
  {% for param in site.data.analyses.base_report %}

  <dt><strong>{{ param.name }}</strong></dt>
  <dd><br><b><i>{{ param.type }}</i></b></dd><dd>{{ param.description }}</dd>

  {% endfor %}
</dl>

<hr>

### Example
{: .no_toc}
#### Classification
{: .no_toc}
```py
from odin.classes import AnalyzerClassification

my_analyzer = AnalyzerClassification("my_classifier_name", my_classification_dataset)
my_analyzer.base_report()
```

#### Localization
{: .no_toc}
```py
from odin.classes import AnalyzerLocalization

my_analyzer = AnalyzerLocalization("my_detector_name", my_localization_dataset)
my_analyzer.base_report()
```

![base_report_output](../../img/analyzer/base_report.png){:class="img-responsive" width="50%"}
{: .text-center}

N.B. For localization models, the Accuracy and Error Rate evaluation metrics are not supported.
{: .text-right .fs-1}

<hr>

## Models comparison
### Example
{: .no_toc}
#### Classification
{: .no_toc}
```py
from odin.classes import ComparatorClassification

my_comparator = ComparatorClassification(dataset_gt_param, classification_type, models_proposals)
my_comparator.base_report()
```

#### Localization
{: .no_toc}
```py
from odin.classes import ComparatorLocalization

my_comparator = ComparatorLocalization(dataset_gt_param, task_type, models_proposals)
my_comparator.base_report()
```

![compare_models_base_report_output](../../img/comparator/comparison_base_report.png){:class="img-responsive" width="75%"}
{: .text-center}

N.B. For localization models, the Accuracy and Error Rate evaluation metrics are not supported.
{: .text-right .fs-1}

<hr>

### Tasks supported
{: .no_toc}
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
