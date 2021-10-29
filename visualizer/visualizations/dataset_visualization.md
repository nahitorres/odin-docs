---
layout: default
title: Data Set Visualization
grand_parent: Visualizer
parent: Visualizations
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

<div class="row">
  <div class="column">
    <b>Classification Example</b>
    <img class="img-responsive" src="../../gifs/visualizer_CL.gif" alt="Example CL gif" />
  </div>
  <div class="column">
    <b>Localization Example</b>
    <img class="img-responsive" src="../../gifs/visualizer_LOC.gif" alt="Example LOC gif" />
  </div>
</div>

<style>
  .row {
  display: flex;
  }

  .column {
    text-align: center;
    flex: 50%;
    margin: 0 auto;
    max-width: 600px;
  }

  @media (max-width: 1400px) {
    .row {
      display: block;
    }
    .column {
      flex: 100%;
    }
}
</style>


<hr>

# visualize_annotations()
{: .mb-6}

It shows all the ground truth and, at user request, the related predictions.

#### Parameters
{: .no_toc}
<dl>
  {% for param in site.data.analyses.visualize_annotations %}

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
from odin.classes import VisualizerClassification

my_visualizer = VisualizerClassification(models)
my_visualizer.visualize_annotations(show_predictions=True)
```

#### Localization
{: .no_toc}
```py
from odin.classes import VisualizerLocalization

my_visualizer = VisualizerLocalization(models)
my_visualizer.visualize_annotations(show_predictions=True)
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
      <td style="background:lightgreen;">yes</td>
      <td style="background:lightgreen;">yes</td>
    </tr>
  </tbody>
</table>

<hr>


# visualize_annotations_for_property()
{: .mb-6}

It shows all the ground truth with a specific property value and, at user request, the related predictions.

#### Parameters
{: .no_toc}
<dl>
  {% for param in site.data.analyses.visualize_annotations_for_property %}

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
from odin.classes import VisualizerClassification

my_visualizer = VisualizerClassification(models)
my_visualizer.visualize_annotations_for_property('property_name',
                                                 'property_value',
                                                 show_predictions=True)
```


#### Localization
{: .no_toc}
```py
from odin.classes import VisualizerLocalization

my_visualizer = VisualizerLocalization(models)
my_visualizer.visualize_annotations_for_property('property_name',
                                                 'property_value',
                                                 show_predictions=True)
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
      <td style="background:lightgreen;">yes</td>
      <td style="background:lightgreen;">yes</td>
    </tr>
  </tbody>
</table>

<hr>

# visualize_annotations_for_class_for_property()
{: .mb-6}

It shows all the ground truth of a category with a specific property value and, at user request, the related predictions.

#### Parameters
{: .no_toc}
<dl>
  {% for param in site.data.analyses.visualize_annotations_for_class_for_property %}

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
from odin.classes import VisualizerClassification

my_visualizer = VisualizerClassification(models)
my_visualizer.visualize_annotations_for_class_for_property('category_name',
                                                           'property_name',
                                                           'property_value',
                                                           show_predictions=True)
```


#### Localization
{: .no_toc}
```py
from odin.classes import VisualizerLocalization

my_visualizer = VisualizerLocalization(models)
my_visualizer.visualize_annotations_for_class_for_property('category_name',
                                                           'property_name',
                                                           'property_value',
                                                           show_predictions=True)
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
      <td style="background:lightgreen;">yes</td>
      <td style="background:lightgreen;">yes</td>
    </tr>
  </tbody>
</table>

<hr>
