---
layout: default
title: Distributions
parent: Analyses
grand_parent: Analyzer
nav_order: 3
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

# show_confusion_matrix()
{: .mb-6}

It shows the confusion matrix of the model. The confusion matrix can be performed for the entire data set or for a subset with a specific property value.

#### Parameters
{: .no_toc}
<dl>
  {% for param in site.data.analyses.show_confusion_matrix %}

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
my_analyzer.show_confusion_matrix()
```

![analyze_cm_output_a](../../img/analyzer/cm_catA.png){:class="img-responsive" style="max-width:500px"}
{: .text-center}

<p style="font-size: 10px; text-align: right;">N.B. As example, it is shown only the output of a single category, but the analysis is performed for all the categories selected.</p>

![analyze_cm_output_b](../../img/analyzer/cm_sl.png){:class="img-responsive" style="max-width:600px"}
{: .text-center}

N.B. The confusion matrix among the categories is supported only for single-label classification task.
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
      <td style="background:lightcoral;">no</td>
      <td style="background:lightcoral;">no</td>
    </tr>
  </tbody>
</table>

<hr>

# show_true_positive_distribution()
{: .mb-6}

It provides the true positive distribution among the categories.

#### Parameters
{: .no_toc}
<dl>
  {% for param in site.data.analyses.show_true_positive_distribution %}

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
my_analyzer.show_true_positive_distribution()
```
#### Localization
{: .no_toc}
```py
from odin.classes import AnalyzerLocalization

my_analyzer = AnalyzerLocalization("my_detector_name", my_localization_dataset)
my_analyzer.show_true_positive_distribution()
```

![show_true_positive_distribution_output](../../img/analyzer/tp_cat_distribution.png){:class="img-responsive" style="max-width:600px"}
{: .text-center}

<hr>

## Models comparison
### Example
{: .no_toc}

#### Classification
{: .no_toc}
```py
from odin.classes import ComparatorClassification

my_comparator = ComparatorClassification(dataset_gt_param, classification_type, models_proposals)
my_comparator.show_true_positive_distribution()
```

#### Localization
{: .no_toc}
```py
from odin.classes import ComparatorLocalization

my_comparator = ComparatorLocalization(dataset_gt_param, task_type, models_proposals)
my_comparator.show_true_positive_distribution()
```

![comparator_tp_distribution](../../img/comparator/comparison_tp.png){:class="img-responsive" style="max-width:800px"}
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
      <td style="background:lightgreen;">yes</td>
      <td style="background:lightgreen;">yes</td>
    </tr>
  </tbody>
</table>

<hr>

# show_false_positive_distribution()
{: .mb-6}

It provides the false positive distribution among the categories.

#### Parameters
{: .no_toc}
<dl>
  {% for param in site.data.analyses.show_false_positive_distribution %}

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
my_analyzer.show_false_positive_distribution()
```
#### Localization
{: .no_toc}
```py
from odin.classes import AnalyzerLocalization

my_analyzer = AnalyzerLocalization("my_detector_name", my_localization_dataset)
my_analyzer.show_false_positive_distribution()
```

![show_false_positive_distribution_output](../../img/analyzer/fp_cat_distribution.png){:class="img-responsive" style="max-width:600px"}
{: .text-center}

<hr>

## Models comparison
### Example
{: .no_toc}

#### Classification
{: .no_toc}
```py
from odin.classes import ComparatorClassification

my_comparator = ComparatorClassification(dataset_gt_param, classification_type, models_proposals)
my_comparator.show_false_positive_distribution()
```

#### Localization
{: .no_toc}
```py
from odin.classes import ComparatorLocalization

my_comparator = ComparatorLocalization(dataset_gt_param, task_type, models_proposals)
my_comparator.show_false_positive_distribution()
```

![comparator_fp_distribution](../../img/comparator/comparison_fp.png){:class="img-responsive" style="max-width:800px"}
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
      <td style="background:lightgreen;">yes</td>
      <td style="background:lightgreen;">yes</td>
    </tr>
  </tbody>
</table>

<hr>

# show_false_negative_distribution()
{: .mb-6}

It provides the false negative distribution among the categories.


#### Parameters
{: .no_toc}
<dl>
  {% for param in site.data.analyses.show_false_negative_distribution %}

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
my_analyzer.show_false_negative_distribution()
```
#### Localization
{: .no_toc}
```py
from odin.classes import AnalyzerLocalization

my_analyzer = AnalyzerLocalization("my_detector_name", my_localization_dataset)
my_analyzer.show_false_negative_distribution()
```

![show_false_negative_distribution_output](../../img/analyzer/fn_cat_distribution.png){:class="img-responsive" style="max-width:600px"}
{: .text-center}

<hr>

## Models comparison
### Example
{: .no_toc}

#### Classification
{: .no_toc}
```py
from odin.classes import ComparatorClassification

my_comparator = ComparatorClassification(dataset_gt_param, classification_type, models_proposals)
my_comparator.show_false_negative_distribution()
```

#### Localization
{: .no_toc}
```py
from odin.classes import ComparatorLocalization

my_comparator = ComparatorLocalization(dataset_gt_param, task_type, models_proposals)
my_comparator.show_false_negative_distribution()
```

![comparator_fn_distribution](../../img/comparator/comparison_fn.png){:class="img-responsive" style="max-width:800px"}
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
      <td style="background:lightgreen;">yes</td>
      <td style="background:lightgreen;">yes</td>
    </tr>
  </tbody>
</table>

<hr>

# show_true_negative_distribution()
{: .mb-6}

It provides the true negative distribution among the categories.

#### Parameters
{: .no_toc}
<dl>
  {% for param in site.data.analyses.show_true_negative_distribution %}

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
my_analyzer.show_true_negative_distribution()
```

![show_true_negative_distribution_output](../../img/analyzer/tn_cat_distribution.png){:class="img-responsive" style="max-width:600px"}
{: .text-center}

<hr>

## Models comparison
### Example
{: .no_toc}

#### Classification
{: .no_toc}
```py
from odin.classes import ComparatorClassification

my_comparator = ComparatorClassification(dataset_gt_param, classification_type, models_proposals)
my_comparator.show_true_negative_distribution()
```

![comparator_tn_distribution](../../img/comparator/comparison_tn.png){:class="img-responsive" style="max-width:800px"}
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

<hr>

# show_true_positive_distribution_for_categories_for_property()
{: .mb-6}

It provides the true positive distribution of the property values for each category.


#### Parameters
{: .no_toc}
<dl>
  {% for param in site.data.analyses.show_true_positive_distribution_for_categories_for_property %}

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
my_analyzer.show_true_positive_distribution_for_categories_for_property("property_name")
```
#### Localization
{: .no_toc}
```py
from odin.classes import AnalyzerLocalization

my_analyzer = AnalyzerLocalization("my_detector_name", my_localization_dataset)
my_analyzer.show_true_positive_distribution_for_categories_for_property("property_name")
```

![show_true_positive_distribution_for_categories_for_property_output](../../img/analyzer/tp_distribution_prop_a.png){:class="img-responsive" style="max-width:600px"}
{: .text-center}

![show_true_positive_distribution_for_categories_for_property_output_b](../../img/analyzer/tp_distribution_prop_b.png){:class="img-responsive" style="max-width:600px"}
{: .text-center}

<hr>

## Models comparison
### Example
{: .no_toc}

#### Classification
{: .no_toc}
```py
from odin.classes import ComparatorClassification

my_comparator = ComparatorClassification(dataset_gt_param, classification_type, models_proposals)
my_comparator.show_true_positive_distribution_for_categories_for_property("property_name")
```

#### Localization
{: .no_toc}
```py
from odin.classes import ComparatorLocalization

my_comparator = ComparatorLocalization(dataset_gt_param, task_type, models_proposals)
my_comparator.show_true_positive_distribution_for_categories_for_property("property_name")
```

![comparator_show_true_positive_distribution_for_categories_for_property_output](../../img/comparator/comparison_tp_prop_a.png){:class="img-responsive" style="max-width:800px"}
{: .text-center}

![comparator_show_true_positive_distribution_for_categories_for_property_output_b](../../img/comparator/comparison_tp_prop_b.png){:class="img-responsive" style="max-width:800px"}
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
      <td style="background:lightgreen;">yes</td>
      <td style="background:lightgreen;">yes</td>
    </tr>
  </tbody>
</table>

<hr>


# show_false_positive_distribution_for_categories_for_property()
{: .mb-6}

It provides the false positive distribution of the property values for each category.


#### Parameters
{: .no_toc}
<dl>
  {% for param in site.data.analyses.show_false_positive_distribution_for_categories_for_property %}

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
my_analyzer.show_false_positive_distribution_for_categories_for_property("property_name")
```

![show_false_positive_distribution_for_categories_for_property_output](../../img/analyzer/fp_distribution_prop_a.png){:class="img-responsive" style="max-width:600px"}
{: .text-center}

![show_false_positive_distribution_for_categories_for_property_output_b](../../img/analyzer/fp_distribution_prop_b.png){:class="img-responsive" style="max-width:600px"}
{: .text-center}

<hr>

## Models comparison
### Example
{: .no_toc}

#### Classification
{: .no_toc}
```py
from odin.classes import ComparatorClassification

my_comparator = ComparatorClassification(dataset_gt_param, classification_type, models_proposals)
my_comparator.show_false_positive_distribution_for_categories_for_property("property_name")
```

![comparator_show_false_positive_distribution_for_categories_for_property_output](../../img/comparator/comparison_fp_prop_a.png){:class="img-responsive" style="max-width:800px"}
{: .text-center}

![comparator_show_false_positive_distribution_for_categories_for_property_output_b](../../img/comparator/comparison_fp_prop_b.png){:class="img-responsive" style="max-width:800px"}
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

<hr>

# show_false_negative_distribution_for_categories_for_property()
{: .mb-6}

It provides the false negative distribution of the property values for each category.


#### Parameters
{: .no_toc}
<dl>
  {% for param in site.data.analyses.show_false_negative_distribution_for_categories_for_property %}

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
my_analyzer.show_false_negative_distribution_for_categories_for_property("property_name")
```
#### Localization
{: .no_toc}
```py
from odin.classes import AnalyzerLocalization

my_analyzer = AnalyzerLocalization("my_detector_name", my_localization_dataset)
my_analyzer.show_false_negative_distribution_for_categories_for_property("property_name")
```

![show_false_negative_distribution_for_categories_for_property_output](../../img/analyzer/fn_distribution_prop_a.png){:class="img-responsive" style="max-width:600px"}
{: .text-center}

![show_false_negative_distribution_for_categories_for_property_output_b](../../img/analyzer/fn_distribution_prop_b.png){:class="img-responsive" style="max-width:600px"}
{: .text-center}

<hr>

## Models comparison
### Example
{: .no_toc}

#### Classification
{: .no_toc}
```py
from odin.classes import ComparatorClassification

my_comparator = ComparatorClassification(dataset_gt_param, classification_type, models_proposals)
my_comparator.show_false_negative_distribution_for_categories_for_property("property_name")
```

#### Localization
{: .no_toc}
```py
from odin.classes import ComparatorLocalization

my_comparator = ComparatorLocalization(dataset_gt_param, task_type, models_proposals)
my_comparator.show_false_negative_distribution_for_categories_for_property("property_name")
```

![comparator_show_false_negative_distribution_for_categories_for_property_output](../../img/comparator/comparison_fn_prop_a.png){:class="img-responsive" style="max-width:800px"}
{: .text-center}

![comparator_show_false_negative_distribution_for_categories_for_property_output_b](../../img/comparator/comparison_fn_prop_b.png){:class="img-responsive" style="max-width:800px"}
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
      <td style="background:lightgreen;">yes</td>
      <td style="background:lightgreen;">yes</td>
    </tr>
  </tbody>
</table>

<hr>


# show_true_negative_distribution_for_categories_for_property()
{: .mb-6}

It provides the true negative distribution of the property values for each category.


#### Parameters
{: .no_toc}
<dl>
  {% for param in site.data.analyses.show_true_negative_distribution_for_categories_for_property %}

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
my_analyzer.show_true_negative_distribution_for_categories_for_property("property_name")
```
#### Localization
{: .no_toc}
```py
from odin.classes import AnalyzerLocalization

my_analyzer = AnalyzerLocalization("my_detector_name", my_localization_dataset)
my_analyzer.show_true_negative_distribution_for_categories_for_property("property_name")
```

![show_true_negative_distribution_for_categories_for_property_output](../../img/analyzer/tn_distribution_prop_a.png){:class="img-responsive" style="max-width:600px"}
{: .text-center}

![show_true_negative_distribution_for_categories_for_property_output_b](../../img/analyzer/tn_distribution_prop_b.png){:class="img-responsive" style="max-width:600px"}
{: .text-center}

<hr>

## Models comparison
### Example
{: .no_toc}

#### Classification
{: .no_toc}
```py
from odin.classes import ComparatorClassification

my_comparator = ComparatorClassification(dataset_gt_param, classification_type, models_proposals)
my_comparator.show_true_negative_distribution_for_categories_for_property("property_name")
```

![comparator_show_true_negative_distribution_for_categories_for_property_output](../../img/comparator/comparison_tn_prop_a.png){:class="img-responsive" style="max-width:800px"}
{: .text-center}

![comparator_show_true_negative_distribution_for_categories_for_property_output_b](../../img/comparator/comparison_tn_prop_b.png){:class="img-responsive" style="max-width:800px"}
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

<hr>
