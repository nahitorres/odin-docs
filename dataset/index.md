---
layout: default
title: Dataset
nav_order: 3
has_children: true
has_toc: false
---


# {{ page.title }}
{: .mb-6}

The Dataset component stores the ground truth and the predictions of the model.
<br>
It provides different distribution analyses in order to identify possible bias in the data set.

<hr>

## DatasetClassification

The DatasetClassification class can be used to store the ground truth and predictions for classification models.

#### Parameters
<dl>
  {% for param in site.data.classes.datasetclassification %}

  <dt><strong>{{ param.name }}</strong></dt>
  <dd><br><b><i>{{ param.type }}</i></b></dd><dd>{{ param.description }}</dd>

  {% endfor %}
</dl>

### Input format

#### Ground Truth
Odin accepts as ground truth a .json file in the following format:

    "categories" :[       # list of categories in the data set
      {
        "id": ...,        # id of the category
        "name": ...       # name of the category
      },
      ...],

    "observations":[      # list of observations
      {
        "id": ...,        # id of the observation
        "file_name": ..., # filename of the observation (it is mandatory only if match_on_filename=True)
        "category": ...,  # id of the category present in the observation (it is mandatory only for TaskType.CLASSIFICATION_BINARY and TaskType.CLASSIFICATION_SINGLE_LABEL classification tasks)
        "categories": ...,# list of ids of the categories present in the observation (it is mandatory only for TaskType.CLASSIFICATION_MULTI_LABEL classification task)
        "...": ...        # any property name with the corresponding property value
      },
      ...]

#### Predictions
The predictions must be in a .txt file, one for each category, and all must be stored in the same directory. Each line of the file represents a prediction, and it must be in the following format:

    # category_name_a.txt

    observation_id confidence        # if match_on_filename=False
    ...
    observation_file_name confidence # if match_on_filename=True
    ...

### Example
```py
from odin.classes import DatasetClassification

# define the path of the GT .json file
dataset_gt_param = "/path/to/gt/file.json"

# define the path of the folder which contains the predictions .txt files
path_to_detections = "/path/to/predictions"

classification_type = TaskType.CLASSIFICATION_MULTI_LABEL

my_dataset = DatasetClassification(dataset_gt_param, classification_type, proposal_path=path_to_detections)
```


<hr>

## DatasetLocalization

The DatasetLocalization class can be used to store the ground truth and predictions for localization models, such as object detection and instance segmentation.

#### Parameters
<dl>
  {% for param in site.data.classes.datasetlocalization %}
  <dt><strong>{{ param.name }}</strong></dt>
  <dd><br><b><i>{{ param.type }}</i></b></dd><dd>{{ param.description }}</dd>

  {% endfor %}
</dl>

### Input format

#### Ground Truth
Odin accepts as ground truth a .json file in the following format:

    "categories" :[           # list of categories in the data set
      {
        "id": ...,            # id of the category
        "name": ...           # name of the category
      },
      ...],

    "images":[                # list of images
      {
        "id": ...,            # id of the image
        "file_name": ...,     # filename of the image (it is mandatory only if match_on_filename=True)
      },
      ...],

    "annotations": [          # list of annotations
      {
        "id": ...,            # id of the annotation
        "image_id": ...,      # id of the image the annotation refers to
        "category_id": ...,   # id of the category present in the annotation
        "segmentation": ...,  # segmentation mask of the annotation (it is mandatory only for TaskType.INSTANCE_SEGMENTATION localization task)
        "bbox": ...,          # bounding box of the annotation (it is mandatory only for TaskType.OBJECT_DETECTION)
        "...": ...            # any property name with the corresponding property value
      }
    ]

#### Predictions
The predictions must be in a .txt file, one for each category, and all must be stored in the same directory. Each line of the file represents a prediction, and it must be in the following format:

    # category_name_a.txt

    # For TaskType.OBJECT_DETECTION
    image_id confidence min_x min_y width height        # if match_on_filename=False
    ...
    image_file_name confidence min_x min_y width height # if match_on_filename=True
    ...

    # For TaskType.INSTANCE_SEGMENTATION
    image_id confidence x1 y1 x2 y2 ... xn yn           # if match_on_filename=False
    ...
    image_file_name confidence x1 y1 x2 y2 ... xn yn    # if match_on_filename=True
    ...

### Example
```py
from odin.classes import DatasetLocalization

# define the path of the GT .json file
dataset_gt_param = "/path/to/gt/file.json"

# define the path of the folder which contains the predictions .txt files
path_to_detections = "/path/to/predictions"

localization_type = TaskType.OBJECT_DETECTION

my_dataset = DatasetLocalization(dataset_gt_param, localization_type, proposal_path=path_to_detections)
```

<hr>

## DatasetCAMs

The DatasetCAMs class can be used to store the ground truth and the Class Activation Maps generated by classification models.

#### Parameters
<dl>
  {% for param in site.data.classes.datasetcams %}

  <dt><strong>{{ param.name }}</strong></dt>
  <dd><br><b><i>{{ param.type }}</i></b></dd><dd>{{ param.description }}</dd>

  {% endfor %}
</dl>

### Input format

#### Ground Truth
Odin accepts as ground truth a .json file in the following format:

    "categories" :[       # list of categories in the data set
      {
        "id": ...,        # id of the category
        "name": ...       # name of the category
      },
      ...],

    "observations":[      # list of observations
      {
        "id": ...,        # id of the observation
        "file_name": ..., # filename of the observation (it is mandatory only if match_on_filename=True)
        "category": ...,  # id of the category present in the observation (it is mandatory only for TaskType.CLASSIFICATION_BINARY and TaskType.CLASSIFICATION_SINGLE_LABEL classification tasks)
        "categories": ...,# list of ids of the categories present in the observation (it is mandatory only for TaskType.CLASSIFICATION_MULTI_LABEL)
        "...": ...        # any property name with the corresponding property value
      },
      ...],

    "annotations": [          # list of annotations
      {
        "id": ...,            # id of the annotation
        "image_id": ...,      # id of the image the annotation refers to
        "category_id": ...,   # id of the category present in the annotation
        "segmentation": ...,  # segmentation mask of the annotation (it is mandatory only for AnnotationType.SEGMENTATION localization task)
        "bbox": ...,          # bounding box of the annotation (it is mandatory only for AnnotationType.BBOX)
      }
    ]

#### CAMs
The CAMs must be in a .npy file, one for each image, and all must be stored in the same directory. Each file size is _h_ x _w_ x _c_ where _h_ and _w_ are the height and width of the image and _c_ is the number of categories.


### Example
```py
from odin.classes import DatasetCAMs

# define the path of the GT .json file
dataset_gt_param = "/path/to/gt/file.json"

# define the path of the CAMs
path_to_cams_detections = "/path/to/cams/predictions"

classification_type = TaskType.CLASSIFICATION_MULTI_LABEL

my_dataset = DatasetCAMs(dataset_gt_param, classification_type, cams_path=path_to_cams_detections)
```
