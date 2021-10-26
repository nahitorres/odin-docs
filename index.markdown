---
layout: default
title: Home
nav_order: 1
permalink: /
---

# **Odin**
{: .mb-6}

**_Odin_**  is an open source diagnosis framework for generic machine learning **classification** tasks and for computer vision **object detection** and **instance segmentation** tasks that lets developers add meta-annotations to their data sets, compute performance metrics split by meta-annotation values, and visualize diagnosis reports.
<br>
**_Odin_**  is agnostic to the training platform and input formats and can be extended with application- and domain-specific meta-annotations and metrics with almost no coding.


<span class="fs-4">
[Odin on GitHub](//github.com/rnt-pmi/odin){:target="_blank"}{:rel="noopener noreferrer"}{: .btn .btn-outline }
</span>
{: .text-center .mb-6 .mt-6}

<hr>

<div class="container-iframe">
<iframe src="https://www.youtube.com/embed/lM4EMaZSbVk" frameborder="0" allowfullscreen class="responsive-iframe"></iframe>
</div>

<hr>

## Supported Tasks
_Odin_ provides different diagnosis methods for machine learning models which address one of the following tasks:

<dl>
  <dt><b>Classification</b></dt>
  <dd>requires an algorithm to categorize the input data into categories</dd>
  <dt><b>Object Detection</b></dt>
  <dd>requires an algorithm to determine which objects are present in an image and to localize their position using bounding boxes</dd>
  <dt><b>Instance Segmentation</b></dt>
  <dd>requires an algorithm to determine which objects are present in an image and to localize their position using a pixel-level segmentation mask</dd>
</dl>


## Supported Diagnosis Methods
The following tables summarize the evaluation metrics and diagnosis methods supported in _Odin_.

### Evaluation Metrics

<table>
  <thead>
    <tr class="header">
      <th colspan=2>Metrics</th>
      <th>Binary Classification</th>
      <th>Single-label Classification</th>
      <th>Multi-label Classification</th>
      <th>Object Detection</th>
      <th>Instance Segmentation</th>
    </tr>
  </thead>
  <tbody  style="text-align:center;">
    {% for param in site.data.tables.metrics %}
    <tr>
      {% if param.rowspan > 0 %}
        <td rowspan={{param.rowspan}}><b>{{param.category}}</b></td>
      {% endif %}
      <td style="border-left: 0px;">{{param.name}}</td>
      <td >{{param.bin_supp}}</td>
      <td >{{param.sl_supp}}</td>
      <td >{{param.ml_supp}}</td>
      <td >{{param.od_supp}}</td>
      <td >{{param.is_supp}}</td>
    </tr>
    {% endfor %}
  </tbody>
</table>

### Dataset Exploration

<table>
  <thead>
    <tr class="header">
      <th colspan=2>Analysis</th>
      <th>Binary Classification</th>
      <th>Single-label Classification</th>
      <th>Multi-label Classification</th>
      <th>Object Detection</th>
      <th>Instance Segmentation</th>
    </tr>
  </thead>
  <tbody  style="text-align:center;">
    {% for param in site.data.tables.dataset %}
    <tr>
    {% if param.rowspan > 0 %}
      <td rowspan={{param.rowspan}}><b>{{param.name}}</b></td>
    {% endif %}
      <td style="border-left: 0px;">{{param.specs}}</td>
      <td >{{param.bin_supp}}</td>
      <td >{{param.sl_supp}}</td>
      <td >{{param.ml_supp}}</td>
      <td >{{param.od_supp}}</td>
      <td >{{param.is_supp}}</td>
    </tr>
    {% endfor %}
  </tbody>
</table>

### Model Analyses

<table>
  <thead>
    <tr class="header">
      <th colspan=2>Analysis</th>
      <th>Models Comparison</th>
      <th>Binary Classification</th>
      <th>Single-label Classification</th>
      <th>Multi-label Classification</th>
      <th>Object Detection</th>
      <th>Instance Segmentation</th>
    </tr>
  </thead>
  <tbody  style="text-align:center;">
    {% for param in site.data.tables.analyses %}
    <tr>
    {% if param.rowspan > 0 %}
      <td rowspan={{param.rowspan}}><b>{{param.name}}</b></td>
    {% endif %}

      <td style="border-left: 0px;">{{param.specs}}</td>
      <td >{{param.comp_supp}}</td>
      <td >{{param.bin_supp}}</td>
      <td >{{param.sl_supp}}</td>
      <td >{{param.ml_supp}}</td>
      <td >{{param.od_supp}}</td>
      <td >{{param.is_supp}}</td>
    </tr>
    {% endfor %}
  </tbody>
</table>

<style>
    .table-wrapper {
      max-width: 100%;
      margin: auto;
    }

    .container-iframe {
      position: relative;
      overflow: hidden;
      width: 100%;
      padding-top: 56.25%; /* 16:9 Aspect Ratio (divide 9 by 16 = 0.5625) */
    }
    .responsive-iframe {
      position: absolute;
      top: 0;
      left: 0;
      bottom: 0;
      right: 0;
      width: 100%;
      height: 100%;
    }
</style>
