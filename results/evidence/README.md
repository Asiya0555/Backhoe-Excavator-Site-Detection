# Evidence index

This folder collects figures from the frozen version 3 dataset and saved notebook outputs. The image grids show multiple labeled examples in one file; their captions state the number of panels. The SAM screenshots document annotation assistance, not trained-model predictions.

## 1. Annotation and prediction examples

| Figure | What it contains |
|---|---|
| [Four annotation examples](annotation_examples_4.png) | Two backhoe loaders and two excavators with training ground-truth boxes. |
| [Ten validation predictions](validation_predictions_10.png) | Ten fixed validation photos, including two without a target label. |
| [Five inference predictions](five_heldout_predictions.png) | Two backhoe loaders, two excavators, and a negative tractor. These five were held out from training but belong to the test split; they are not independently sourced outside photos. |

## 2. Individual success and error panels

- **Successful detections:** [rear-view backhoe loader](success_01_backhoe_rear.png), [backhoe loader at site](success_02_backhoe_site.png), [site excavator](success_03_excavator_site.png).
- **False-positive panels:** [negative tractor with two incorrect boxes](failure_fp_tractor_two_boxes.png) and [extra overlapping excavator box](failure_fp_duplicate_excavator.png). These represent three false boxes across two test photos.
- **False-negative panels:** [sideways backhoe loader](failure_fn_sideways_backhoe.png), [transported excavator](failure_fn_transported_excavator.png), and [partly visible backhoe loader in validation](failure_fn_partial_backhoe_valid.png).

The [error analysis](../../docs/error_analysis.md) explains each case and three prioritized data improvements.

## 3. SAM-assisted annotation screenshots

- [Set the excavator class and run SAM 3 Masks](sam/sam_01_prompt.png).
- [Review a mask and enclosing box on a clear excavator](sam/sam_02_clear_mask.png).
- [Review a mask proposal near other vehicles](sam/sam_03_cluttered_mask.png).

See the screenshots **in context** under [SAM-assisted annotation review](../../docs/annotation_workflow.md#sam-assisted-annotation-review). These are proposed masks during review, not final detector predictions or a measured SAM accuracy result.

## 4. Training and test figures

[Thirty-epoch losses and validation metrics](../results.png) · [test confusion matrix](../confusion_matrix.png) · [full 13-photo test grid](../test_predictions_grid.png)
