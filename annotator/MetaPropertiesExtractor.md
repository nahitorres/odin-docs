---
layout: default
title: MetaPropertiesExtractor
parent: Annotator
nav_order: 3
---

# {{ page.title }}
{: .mb-6}

The MetaPropertiesExtractor class allows the automatic extraction of meta-annotations from the observations.<br>
_Odin_ provides the support to the extraction of three different meta-annotations:
 - **MetaProperties.COLOR**: extraction of the image color space. It can be 'rgb' (colored) or 'bw' (greyscaled).
 - **MetaProperties.FACES**: extraction of the number of faces present in the image. It can be '0-1', '2-4', '5+'.
 - **MetaProperties.CHARACTERS**: extraction of the number of CHARACTERS present in the image. It can be '0-1', '2-4', '5+'.

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
properties = [MetaProperties.COLOR, MetaProperties.FACES, MetaProperties.CHARACTERS]
my_output_path = "path/to/save/the/new/annotated/dataset/"

my_annotator = MetaPropertiesExtractor(my_classification_dataset, properties,
                                       output_path=my_output_path)
my_annotator.start_annotation()
```

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
