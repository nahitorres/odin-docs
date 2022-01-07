---
layout: default
title: MetaPropertiesExtractor
parent: Annotator
nav_order: 3
---

# {{ page.title }}
{: .mb-6}

The MetaPropertiesExtractor class allows the automatic extraction of meta-annotations from the observations.<br>
_Odin_ provides the support to the extraction of two different meta-annotations:
 - **MetaProperties.COLOR**: extraction of the image color space. It can be 'rgb' (colored) or 'bw' (greyscaled).
 - **MetaProperties.FACES**: extraction of the number of faces present in the image. It can be '0-1', '2-4', '5+'.

<hr>

#### Parameters
<dl>
  {% for param in site.data.classes.metapropertiesextractor %}

  <dt><strong>{{ param.name }}</strong></dt>
  <dd><br><b><i>{{ param.type }}</i></b></dd><dd>{{ param.description }}</dd>

  {% endfor %}
</dl>

<hr>

### Example
```py
from odin.annotator.meta_annotator_extractor import MetaPropertiesExtractor, MetaProperties

# define the properties to be extracted
my_properties = [MetaProperties.COLOR, MetaProperties.FACES]
my_output_path = "path/to/save/the/new/annotated/dataset/"

my_annotator = MetaPropertiesExtractor(my_classification_dataset,
                                       properties=my_properties,
                                       output_path=my_output_path)
my_annotator.start_annotation()
```

<hr>

## Custom extractor

It is possible to implement a custom meta-annotation extractor by simply implement the _process_object_ function of the _PropertyAnnotatorInterface_ interface. The following example shows how to implement a custom extractor and how it can be integrated into the _MetaPropertiesExtractor_.

### Example
```py
from odin.annotator.meta_annotator_extractor import MetaPropertiesExtractor, MetaProperties, PropertyAnnotatorInterface

# define your custom meta-annotation extractor
class MyCustomMetaAnnotationExtractor(PropertyAnnotatorInterface):
    DEFAULT_VALUE = 0
    NAME = "n_categories"

    def __init__(self):
        property_values = []
        super().__init__(self.NAME, property_values, self.DEFAULT_VALUE)

    def process_object(self, data_object, dataset_abs_path=None):
        """
        Return the number of categories in the observation
        """
        n_categories = len(data_object["categories"])
        if n_categories not in self.property_values:
            self.property_values.append(n_categories)
        return n_categories

# instantiate the MetaPropertiesExtractor
my_output_path = "path/to/save/the/new/annotated/dataset/"
my_annotator = MetaPropertiesExtractor(my_classification_dataset,
                                       output_path=my_output_path)

# instantiate the custom extractor and add it to the annotator
custom_extractor = MyCustomMetaAnnotationExtractor()
my_annotator.add_custom_property(custom_extractor)

my_annotator.start_annotation()
```

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
