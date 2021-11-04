---
permalink: /correction/fp_background_error.html
nav_exclude: true
---

# False Positive background error correction (Localization tasks)

### Previous version
In the previous version of _Odin_, each prediction was matched with an annotation of the same category, if any, otherwise it was matched with the annotation with the highest IoU score.

In this way, if in an image there was at least one annotation of the predicted category and the score of Iou with the prediction was lower than a minimum threshold (0.2), the error was classified as 'background'.

With this categorization, the 'background' errors also included cases where the model had correctly located an object, but the predicted class was wrong.

The following images provide some examples of this case:

![fp_background_a](../img/fp_explanation/id_1.png){:class="img-responsive" style="max-width:450px"}
![fp_background_b](../img/fp_explanation/id_54.png){:class="img-responsive" style="max-width:450px"}
{: .text-center}


### Actual version
In the actual version we have modified the matching between the predictions and the ground truth as follow.

Each prediction is matched with an annotation of the same category only if the IoU score is greater than a minimum threshold (0.2), so to be considered at least a localization error (if the IoU score is less than the threshold provided), otherwise, the prediction is matched with the annotation with the highest IoU score.

With this change, if the model has correctly located an object, but the predicted class is wrong, the error is classified as 'other' or 'similar' (if the model has confused two similar classes).


<b>N.B. This change affects only the FP categorization and impact analysis</b>
{: .text-center}
