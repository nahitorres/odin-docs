---
layout: default
title: RarePlanes
parent: Localization
grand_parent: Examples
nav_order: 1
---

[[Notebook example]](https://github.com/rnt-pmi/odin/tree/master/examples)
{: .text-right .fs-2}

# {{ page.title }}
{: .mb-6}

### Package import and variables definition
```py
from odin.classes import DatasetLocalization, AnalyzerLocalization, Metrics, TaskType, Curves

# define the path of the GT .json file
dataset_gt_param = "../../test-data/localization/gt.json"

# define the path of the folder that contains the predictions .txt files for each model
path_to_detections = [("my_model", "../../test-data/localization/predictions-segmentation/")]

# define the problem task
task_type = TaskType.INSTANCE_SEGMENTATION

# define the file_name for the meta-annotations
properties_file = "properties_plane.json"
```

### Dataset
```py
my_dataset = DatasetClassification(dataset_gt_param,
                                   classification_type,
                                   proposals_paths=path_to_detections,
                                   similar_classes=similar_classes,
                                   properties_file=properties_file,
                                   save_graphs_as_png=False)
```
![Dataset](../../img/examples/rareplanes/dataset.png){:class="img-responsive" style="max-width:300px"}
{: .text-center}

#### Co-occurrence matrix
```py
my_dataset.show_co_occurrence_matrix()
```
![co_occurrence](../../img/examples/rareplanes/co_occurrence.png){:class="img-responsive" style="max-width:400px"}
{: .text-center}

#### Categories distribution
```py
my_dataset.show_distribution_of_categories()
```
![categories_distribution](../../img/examples/rareplanes/categories_distribution.png){:class="img-responsive" style="max-width:500px"}
{: .text-center}

#### Properties distribution
```py
my_dataset.show_distribution_of_properties()
```
![properties_distribution_a](../../img/examples/rareplanes/properties_distribution_a.png){:class="img-responsive" style="max-width:300px"}
![properties_distribution_e](../../img/examples/rareplanes/properties_distribution_e.png){:class="img-responsive" style="max-width:300px"}
![properties_distribution_i](../../img/examples/rareplanes/properties_distribution_i.png){:class="img-responsive" style="max-width:300px"}
{: .text-center}

![properties_distribution_b](../../img/examples/rareplanes/properties_distribution_b.png){:class="img-responsive" style="max-width:300px"}
![properties_distribution_c](../../img/examples/rareplanes/properties_distribution_c.png){:class="img-responsive" style="max-width:300px"}
![properties_distribution_d](../../img/examples/rareplanes/properties_distribution_d.png){:class="img-responsive" style="max-width:300px"}
![properties_distribution_f](../../img/examples/rareplanes/properties_distribution_f.png){:class="img-responsive" style="max-width:300px"}
![properties_distribution_g](../../img/examples/rareplanes/properties_distribution_g.png){:class="img-responsive" style="max-width:300px"}
![properties_distribution_h](../../img/examples/rareplanes/properties_distribution_h.png){:class="img-responsive" style="max-width:300px"}
![properties_distribution_l](../../img/examples/rareplanes/properties_distribution_l.png){:class="img-responsive" style="max-width:300px"}
![properties_distribution_m](../../img/examples/rareplanes/properties_distribution_m.png){:class="img-responsive" style="max-width:300px"}
![properties_distribution_n](../../img/examples/rareplanes/properties_distribution_n.png){:class="img-responsive" style="max-width:300px"}
{: .text-center}

### Analyzer
```py
my_analyzer = AnalyzerLocalization('my_model',
                                   my_dataset,
                                   use_normalization=True,
                                   norm_factor_categories=0.3,
                                   metric=Metrics.AVERAGE_PRECISION_INTERPOLATED,
                                   save_graphs_as_png=False)

my_analyzer.set_normalization(True, with_properties=False)
```

#### Properties analysis
```py
my_analyzer.analyze_properties()
```
![analyze_properties_a](../../img/examples/rareplanes/analyze_properties_a.png){:class="img-responsive" style="max-width:500px"}
![analyze_properties_b](../../img/examples/rareplanes/analyze_properties_b.png){:class="img-responsive" style="max-width:500px"}
![analyze_properties_c](../../img/examples/rareplanes/analyze_properties_c.png){:class="img-responsive" style="max-width:500px"}
{: .text-center}

#### Sensitivity and impact analysis
```py
my_analyzer.analyze_sensitivity_impact_of_properties()
```
![sensitivity_impact](../../img/examples/rareplanes/sensitivity_impact.png){:class="img-responsive" style="max-width:500px"}
{: .text-center}

#### False Positive categorization and impact
```py
my_analyzer.analyze_false_positive_errors()
```
![fp_analysis_a](../../img/examples/rareplanes/fp_analysis_a.png){:class="img-responsive" style="max-width:400px"}
![fp_analysis_b](../../img/examples/rareplanes/fp_analysis_b.png){:class="img-responsive" style="max-width:400px"}
{: .text-center}
![fp_analysis_c](../../img/examples/rareplanes/fp_analysis_c.png){:class="img-responsive" style="max-width:400px"}
![fp_analysis_d](../../img/examples/rareplanes/fp_analysis_d.png){:class="img-responsive" style="max-width:400px"}
{: .text-center}
![fp_analysis_e](../../img/examples/rareplanes/fp_analysis_e.png){:class="img-responsive" style="max-width:400px"}
![fp_analysis_f](../../img/examples/rareplanes/fp_analysis_f.png){:class="img-responsive" style="max-width:400px"}
{: .text-center}

#### False Negative categorization
```py
my_analyzer.analyze_false_negative_errors()
```
![fn_analysis_a](../../img/examples/rareplanes/fn_analysis_a.png){:class="img-responsive" style="max-width:400px"}
![fn_analysis_b](../../img/examples/rareplanes/fn_analysis_b.png){:class="img-responsive" style="max-width:400px"}
![fn_analysis_c](../../img/examples/rareplanes/fn_analysis_c.png){:class="img-responsive" style="max-width:400px"}
{: .text-center}

#### Precision-Recall Curve - Overall
```py
my_analyzer.analyze_curve(average="micro")
```
![pr_curve](../../img/examples/rareplanes/pr_curve.png){:class="img-responsive" style="max-width:800px"}
{: .text-center}

#### Precision-Recall Curve - Per-category
```py
my_analyzer.analyze_curve_for_categories()
```
![pr_curve_categories](../../img/examples/rareplanes/pr_curve_categories.png){:class="img-responsive" style="max-width:800px"}
{: .text-center}

#### IoU analysis
```py
my_analyzer.analyze_intersection_over_union()
```
![iou](../../img/examples/rareplanes/iou.png){:class="img-responsive" style="max-width:800px"}
{: .text-center}

#### Reliability analysis
```py
my_analyzer.analyze_reliability()
```
![reliability](../../img/examples/rareplanes/reliability.png){:class="img-responsive" style="max-width:800px"}
{: .text-center}

#### True Positive distribution
```py
my_analyzer.show_true_positive_distribution()
```
![tp_distribution](../../img/examples/rareplanes/tp_distribution.png){:class="img-responsive" style="max-width:400px"}
{: .text-center}

#### False Negative distribution
```py
my_analyzer.show_false_negative_distribution()
```
![fn_distribution](../../img/examples/rareplanes/fn_distribution.png){:class="img-responsive" style="max-width:400px"}
{: .text-center}

#### False Positive distribution
```py
my_analyzer.show_false_positive_distribution()
```
![fp_distribution](../../img/examples/rareplanes/fp_distribution.png){:class="img-responsive" style="max-width:400px"}
{: .text-center}

#### Performance summary
```py
my_analyzer.base_report()
```
![report](../../img/examples/rareplanes/report.png){:class="img-responsive" style="max-width:800px"}
{: .text-center}
