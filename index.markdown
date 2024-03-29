---
layout: default
title: Home
nav_order: 0
permalink: /
---

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

    /* The Modal (background) */
    .modal {
      display: none; /* Hidden by default */
      position: fixed; /* Stay in place */
      z-index: 2; /* Sit on top */
      width: 100%; /* Full width */
      height: 100%;
      left: 0;
      top: 0;
      overflow: auto; /* Enable scroll if needed */
      background-color: rgb(0,0,0); /* Fallback color */
      background-color: rgba(0,0,0,0.4); /* Black w/ opacity */
    }

    /* Modal Content/Box */
    .modal-content {
      background-color: #fefefe;
      margin: 15% auto; /* 15% from the top and centered */
      padding: 20px;
      border: 1px solid #888;
      width: 100%; /* Could be more or less, depending on screen size */
      max-width: 500px;
      text-align: center;
    }

    /* The Close Button */
    .close {
      color: #aaa;
      float: right;
      font-size: 28px;
      font-weight: bold;
    }

    .close:hover,
    .close:focus {
      color: black;
      text-decoration: none;
      cursor: pointer;
    }
</style>


<script>
  $(document).ready(function () {
    if (sessionStorage.getItem('showModal') == null){
      $("#myModal").css({"display": "block"});
      $(".close").on("click", function () {
        $("#myModal").css({"display": "none"})
      });
      sessionStorage.setItem('showModal', false);
    }
  });

</script>


<!-- The Modal -->
<div id="myModal" class="modal">

  <!-- Modal content -->
  <div class="modal-content">
    <span class="close">&times;</span>
    <h2>NEW!</h2>
    <p>Now Odin supports <b>Time Series analysis</b>!</p>
    <p>In particular, it implements diagnosis for models that address <i>Anomaly Detection</i> and <i>Predictive Maintenance</i> tasks.<br>
    The new documentation will be soon available.</p>
  </div>

</div>

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

![architecture](./img/architecture.png){:class="img-responsive" style="max-width:800px"}
{: .text-center}
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
    {% for param in site.data.tables.diagnosis_metrics %}
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
    {% for param in site.data.tables.diagnosis_analyses %}
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

*From the previous version, we have modified the counting of the background errors ​for localization problems. For more information, click [here](./correction/fp_background_error.html)
{: .fs-1}

## Supported CAMs Methods

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
    {% for param in site.data.tables.cams_metrics %}
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

### CAMs Analyses
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
    {% for param in site.data.tables.cams_analyses %}
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

<hr>

## Contributors
{: .text-center}
{% for contributor in site.data.contributors.contributors %}
  {{contributor.name}} - {{contributor.email}}
  {: .text-center}
{% endfor %}
