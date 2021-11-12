---
layout: default
title: ArtDL
parent: Classification
grand_parent: Examples
nav_order: 1
---

[[Notebook example]](https://github.com/rnt-pmi/odin/tree/master/examples){:target="_blank"}
{: .text-right .fs-2}

# {{ page.title }} - a multi label classification task example
{: .mb-6}

### Package import and variables definition
```py
from odin.classes import TaskType, Metrics, Curves, CustomMetric, DatasetClassification, AnalyzerClassification

# define the path of the GT .json file
dataset_gt_param = "../../test-data/classification-ml/gt_art.json"

# define the path of the folder that contains the predictions .txt files for each model
path_to_detections = "../../test-data/classification-ml/predictions"

# define the task type
classification_type = TaskType.CLASSIFICATION_MULTI_LABEL

# define groups of categories which are similar to each other (useful for the error analysis)
similar_classes=[[1, 4, 7], [2, 6, 10], [5, 8], [3, 6, 9]]

# define the file_name for the meta-annotations
properties_file = "properties_art.json"
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
![Dataset](../../img/examples/artdl/dataset.png){:class="img-responsive" style="max-width:300px"}
{: .text-center}

#### Categories distribution
```py
my_dataset.show_distribution_of_categories()
```
![categories_distribution](../../img/examples/artdl/categories_distribution.png){:class="img-responsive" style="max-width:400px"}
{: .text-center}

#### Properties distribution
```py
my_dataset.show_distribution_of_properties()
```
![properties_distribution_a](../../img/examples/artdl/properties_distribution_a.png){:class="img-responsive" style="max-width:300px"}
![properties_distribution_d](../../img/examples/artdl/properties_distribution_d.png){:class="img-responsive" style="max-width:300px"}
{: .text-center}
![properties_distribution_b](../../img/examples/artdl/properties_distribution_b.png){:class="img-responsive" style="max-width:300px"}
![properties_distribution_c](../../img/examples/artdl/properties_distribution_c.png){:class="img-responsive" style="max-width:300px"}
![properties_distribution_e](../../img/examples/artdl/properties_distribution_e.png){:class="img-responsive" style="max-width:300px"}
![properties_distribution_f](../../img/examples/artdl/properties_distribution_f.png){:class="img-responsive" style="max-width:300px"}
![properties_distribution_g](../../img/examples/artdl/properties_distribution_g.png){:class="img-responsive" style="max-width:300px"}
{: .text-center}


### Analyzer
```py
my_analyzer = AnalyzerClassification('my_model',
                                     my_dataset,
                                     metric=Metrics.F1_SCORE,
                                     save_graphs_as_png=False)
```

#### Properties analysis
```py
my_analyzer.analyze_properties()
```
![analyze_properties_a](../../img/examples/artdl/analyze_properties_a.png){:class="img-responsive" style="max-width:800px"}
![analyze_properties_b](../../img/examples/artdl/analyze_properties_b.png){:class="img-responsive" style="max-width:800px"}
{: .text-center}

#### Sensitivity and impact analysis
```py
my_analyzer.analyze_sensitivity_impact_of_properties()
```
![sensitivity_impact](../../img/examples/artdl/sensitivity_impact.png){:class="img-responsive" style="max-width:500px"}
{: .text-center}

#### False Positive categorization and impact
```py
my_analyzer.analyze_false_positive_errors()
```
![fp_analysis_a](../../img/examples/artdl/fp_analysis_a.png){:class="img-responsive" style="max-width:400px"}
![fp_analysis_b](../../img/examples/artdl/fp_analysis_b.png){:class="img-responsive" style="max-width:400px"}
{: .text-center}
![fp_analysis_c](../../img/examples/artdl/fp_analysis_c.png){:class="img-responsive" style="max-width:400px"}
![fp_analysis_d](../../img/examples/artdl/fp_analysis_d.png){:class="img-responsive" style="max-width:400px"}
{: .text-center}
![fp_analysis_e](../../img/examples/artdl/fp_analysis_e.png){:class="img-responsive" style="max-width:400px"}
![fp_analysis_f](../../img/examples/artdl/fp_analysis_f.png){:class="img-responsive" style="max-width:400px"}
{: .text-center}
![fp_analysis_g](../../img/examples/artdl/fp_analysis_g.png){:class="img-responsive" style="max-width:400px"}
![fp_analysis_h](../../img/examples/artdl/fp_analysis_h.png){:class="img-responsive" style="max-width:400px"}
{: .text-center}
![fp_analysis_i](../../img/examples/artdl/fp_analysis_i.png){:class="img-responsive" style="max-width:400px"}
![fp_analysis_l](../../img/examples/artdl/fp_analysis_l.png){:class="img-responsive" style="max-width:400px"}
{: .text-center}
![fp_analysis_m](../../img/examples/artdl/fp_analysis_m.png){:class="img-responsive" style="max-width:400px"}
![fp_analysis_n](../../img/examples/artdl/fp_analysis_n.png){:class="img-responsive" style="max-width:400px"}
{: .text-center}
![fp_analysis_o](../../img/examples/artdl/fp_analysis_o.png){:class="img-responsive" style="max-width:400px"}
![fp_analysis_p](../../img/examples/artdl/fp_analysis_p.png){:class="img-responsive" style="max-width:400px"}
{: .text-center}
![fp_analysis_q](../../img/examples/artdl/fp_analysis_q.png){:class="img-responsive" style="max-width:400px"}
![fp_analysis_r](../../img/examples/artdl/fp_analysis_r.png){:class="img-responsive" style="max-width:400px"}
{: .text-center}
![fp_analysis_s](../../img/examples/artdl/fp_analysis_s.png){:class="img-responsive" style="max-width:400px"}
![fp_analysis_t](../../img/examples/artdl/fp_analysis_t.png){:class="img-responsive" style="max-width:400px"}
{: .text-center}
![fp_analysis_u](../../img/examples/artdl/fp_analysis_u.png){:class="img-responsive" style="max-width:400px"}
![fp_analysis_v](../../img/examples/artdl/fp_analysis_v.png){:class="img-responsive" style="max-width:400px"}
{: .text-center}

#### False Negative categorization
```py
my_analyzer.analyze_false_negative_errors()
```
![fn_analysis_a](../../img/examples/artdl/fn_analysis_a.png){:class="img-responsive" style="max-width:400px"}
![fn_analysis_b](../../img/examples/artdl/fn_analysis_b.png){:class="img-responsive" style="max-width:400px"}
![fn_analysis_c](../../img/examples/artdl/fn_analysis_c.png){:class="img-responsive" style="max-width:400px"}
![fn_analysis_d](../../img/examples/artdl/fn_analysis_d.png){:class="img-responsive" style="max-width:400px"}
![fn_analysis_e](../../img/examples/artdl/fn_analysis_e.png){:class="img-responsive" style="max-width:400px"}
![fn_analysis_f](../../img/examples/artdl/fn_analysis_f.png){:class="img-responsive" style="max-width:400px"}
![fn_analysis_g](../../img/examples/artdl/fn_analysis_g.png){:class="img-responsive" style="max-width:400px"}
![fn_analysis_h](../../img/examples/artdl/fn_analysis_h.png){:class="img-responsive" style="max-width:400px"}
![fn_analysis_i](../../img/examples/artdl/fn_analysis_i.png){:class="img-responsive" style="max-width:400px"}
![fn_analysis_l](../../img/examples/artdl/fn_analysis_l.png){:class="img-responsive" style="max-width:400px"}
{: .text-center}

#### Precision-Recall curve - Overall
```py
my_analyzer.analyze_curve(average="micro")
```
![pr_curve](../../img/examples/artdl/pr_curve.png){:class="img-responsive" style="max-width:800px"}
{: .text-center}

#### Precision-Recall curve - Per-category
```py
my_analyzer.analyze_curve_for_categories()
```
![pr_curve_categories](../../img/examples/artdl/pr_curve_categories.png){:class="img-responsive" style="max-width:800px"}
{: .text-center}

#### Reliability analysis
```py
my_analyzer.analyze_reliability()
```
![reliability](../../img/examples/artdl/reliability.png){:class="img-responsive" style="max-width:800px"}
{: .text-center}

#### Performance summary
```py
my_analyzer.base_report()
```
![report](../../img/examples/artdl/report.png){:class="img-responsive" style="max-width:800px"}
{: .text-center}
