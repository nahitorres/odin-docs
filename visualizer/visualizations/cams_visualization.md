---
layout: default
title: CAMs Visualization
grand_parent: Visualizer
parent: Visualizations
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
**CAMs Example**
{: .text-center}
![Example gif](../../gifs/visualizer_CAMs.gif){:class="img-responsive" style="max-width:600px"}
{: .text-center}

<hr>

# visualize_cams()
{: .mb-6}

It shows all the ground truth and the related Class Activation Maps of the model.

#### Parameters
{: .no_toc}
<dl>
  {% for param in site.data.analyses.visualize_cams %}

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
my_visualizer.visualize_cams()
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

<hr>
