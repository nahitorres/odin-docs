---
layout: default
title: Custom Metric
parent: Metrics and Curves
nav_order: 17
---

# {{ page.title }}
{: .mb-6}

Odin provides the possibility to execute all the analyses with user custom evaluation metrics. To take advantage of this functionality, it is mandatory to extend the _CustomMetric_ interface and to implement the <i>evaluation_metric()</i> method with the computation of the metric.

## evaluation_metric()
#### Parameters
<dl>
  {% for param in site.data.analyses.evaluation_metric %}

  <dt><strong>{{ param.name }}</strong></dt>
  <dd><br><b><i>{{ param.type }}</i></b></dd><dd>{{ param.description }}</dd>

  {% endfor %}
</dl>


### Example
```py
from odin.classes import CustomMetric

class MyEvaluationMetric(CustomMetric):
    def evaluate_metric(self, gt, predictions, matching, is_micro_required=False):
        if not is_micro_required: #is_micro_required == false
            # implement your evaluation
            return my_score, my_standard_error
        #when called from base report for micro avg
        else: #is_micro_required == true
            # implement your micro evaluation
            return my_score, my_standard_error

my_evaluation_metric = MyEvaluationMetric("my_metric_name")
my_analyzer.add_custom_metric(my_evaluation_metric)

# use my_metric_name as 'metric' parameter in the analyses
```

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
