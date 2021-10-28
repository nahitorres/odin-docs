---
layout: default
title: Visualizer
nav_order: 6
has_children: true
has_toc: false
---

# {{ page.title }}
{: .mb-6}

The Visualizer component provides a qualitative analysis of the model.
<br>
It is possible to visualize the ground truth and the predictions at different levels of granularity.

<hr>

## VisualizerClassification

The VisualizerClassification class can be used to visualize the ground truth, the predictions  and the CAMs of classification tasks.

#### Parameters
<dl>
  {% for param in site.data.classes.visualizerclassification %}

  <dt><strong>{{ param.name }}</strong></dt>
  <dd><br><b><i>{{ param.type }}</i></b></dd><dd>{{ param.description }}</dd>

  {% endfor %}
</dl>

### Example

#### For ground truth visualization
```py
from odin.classes import DatasetClassification, VisualizerClassification

dataset_gt_param = "/path/to/gt/file.json" # Your file gt file goes here
images_path = "/path/to/gt/images" # Your images folder goes here
classification_type = TaskType.CLASSIFICATION_MULTI_LABEL

my_dataset = DatasetClassification(dataset_gt_param, classification_type,
                                   observations_abs_path=images_path)

my_visualizer = VisualizerClassification(my_dataset)
```

#### For ground truth and predictions visualization
```py
from odin.classes import DatasetClassification, VisualizerClassification

dataset_gt_param = "/path/to/gt/file.json"
images_path = "/path/to/gt/images"
path_to_detections = [("model_a", "/path/to/predictions_a"),
                      ("model_b", "/path/to/predictions_b")]
classification_type = TaskType.CLASSIFICATION_MULTI_LABEL

my_dataset = DatasetClassification(dataset_gt_param, classification_type,
                                   proposals_paths=path_to_detections,
                                   observations_abs_path=images_path)

my_visualizer = VisualizerClassification(my_dataset)
```

#### For ground truth, predictions and analyses visualization
```py
from odin.classes import AnalyzerClassification, VisualizerClassification

my_analyzer_a = AnalyzerClassification("model_a", my_dataset)
my_analyzer_b = AnalyzerClassification("model_b", my_dataset)

my_visualizer = VisualizerClassification(my_dataset,
                                         analyzers=[my_analyzer_a, my_analyzer_b])
```

#### For CAMs visualization
```py
from odin.classes import DatasetCAMs, VisualizerClassification

dataset_gt_param = "/path/to/gt/file.json" # Your file gt file goes here
images_path = "/path/to/gt/images" # Your images folder goes here
path_to_cams_detections = [("model_a", "/path/to/cams/predictions_a"),
                           ("model_b", "/path/to/cams/predictions_b")]
classification_type = TaskType.CLASSIFICATION_MULTI_LABEL


my_dataset = DatasetCAMs(dataset_gt_param, classification_type,
                         cams_paths=path_to_cams_detections,
                         observations_abs_path=images_path,
                         for_analysis=True)

my_visualizer = VisualizerClassification(my_dataset)
```

<hr>

## VisualizerLocalization

The VisualizerLocalization class can be used to visualize the ground truth and the predictions of localization tasks, such as object detection and instance segmentation.

#### Parameters
<dl>
  {% for param in site.data.classes.visualizerlocalization %}
  <dt><strong>{{ param.name }}</strong></dt>
  <dd><br><b><i>{{ param.type }}</i></b></dd><dd>{{ param.description }}</dd>

  {% endfor %}
</dl>

### Example
#### For ground truth visualization
```py
from odin.classes import DatasetLocalization, VisualizerLocalization

dataset_gt_param = "/path/to/gt/file.json" # Your file gt file goes here
images_path = "/path/to/gt/images" # Your images folder goes here
localization_type = TaskType.OBJECT_DETECTION

my_dataset = DatasetLocalization(dataset_gt_param, localization_type,
                                 images_abs_path=images_path)

my_visualizer = VisualizerLocalization(my_dataset)
```

#### For ground truth and predictions visualization
```py
from odin.classes import DatasetLocalization, VisualizerLocalization

dataset_gt_param = "/path/to/gt/file.json"
images_path = "/path/to/gt/images"
path_to_detections = [("model_a", "/path/to/predictions_a"),
                      ("model_b", "/path/to/predictions_b")]
localization_type = TaskType.OBJECT_DETECTION

my_dataset = DatasetLocalization(dataset_gt_param, localization_type,
                                 proposals_paths=path_to_detections,
                                 images_abs_path=images_path)

my_visualizer = VisualizerLocalization(my_dataset)
```

#### For ground truth, predictions and analyses visualization
```py
from odin.classes import AnalyzerLocalization, VisualizerLocalization

my_analyzer_a = AnalyzerLocalization("model_a", my_dataset)
my_analyzer_b = AnalyzerLocalization("model_b", my_dataset)

my_visualizer = VisualizerLocalization(my_dataset,
                                       analyzers=[my_analyzer_a, my_analyzer_b])
```
