---
layout: default
title: CAMs
parent: Analyses
grand_parent: Analyzer
nav_order: 9
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

# analyze_cams()
{: .mb-6}

It provides the analysis of the model CAMs at different thresholds for the entire data set.


#### Parameters
{: .no_toc}
<dl>
  {% for param in site.data.analyses.analyze_cams %}

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
from odin.classes import AnalyzerCAMs

my_analyzer = AnalyzerCAMs("my_classifier_name", my_CAMs_dataset)
my_analyzer.analyze_cams()
```

![analyze_cams_output](../../img/analyzer/cams_total_analysis.png){:class="img-responsive" style="max-width:800px"}
{: .text-center}

<hr>

## Models comparison
### Example
{: .no_toc}

#### Classification
{: .no_toc}
```py
from odin.classes import ComparatorCAMs

my_comparator = ComparatorCAMs(dataset_gt_param, classification_type, models_proposals)
my_comparator.analyze_cams()
```

![compare_models_on_cams_threshold_output](../../img/comparator/comparison_cams.png){:class="img-responsive" style="max-width:800px"}
{: .text-center}

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
      <td style="background:lightcoral;">no</td>
      <td style="background:lightcoral;">no</td>
    </tr>
  </tbody>
</table>

# analyze_cams_for_categories()
{: .mb-6}

It provides a per-category analysis of the model CAMs at different thresholds.


#### Parameters
{: .no_toc}
<dl>
  {% for param in site.data.analyses.analyze_cams_for_categories %}

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
from odin.classes import AnalyzerCAMs

my_analyzer = AnalyzerCAMs("my_classifier_name", my_CAMs_dataset)
my_analyzer.analyze_cams_for_categories()
```

![analyze_cams_output](../../img/analyzer/cams_cats_analysis.png){:class="img-responsive" style="max-width:800px"}
{: .text-center}

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
      <td style="background:lightcoral;">no</td>
      <td style="background:lightgreen;">yes</td>
      <td style="background:lightgreen;">yes</td>
      <td style="background:lightcoral;">no</td>
      <td style="background:lightcoral;">no</td>
    </tr>
  </tbody>
</table>
