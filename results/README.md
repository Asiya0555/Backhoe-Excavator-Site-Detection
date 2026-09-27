# Results and visual evidence

The figures below come from the executed training notebook and frozen Roboflow version 3 export. Two classes were trained: `Backhoe Loader` and `excavator`; the confusion matrix adds *background* to show unmatched objects or predictions. Background is not a dataset class.

## Training and evaluation

- [Training losses and validation metrics across 30 epochs](results.png): training box loss fell overall while validation mAP rose. Individual loss curves fluctuate.
- [Held-out test confusion matrix](confusion_matrix.png): inspect both missed labels and unmatched predictions alongside the aggregate metrics.

The 13-image test split has 12 labeled target objects. Overall test precision was **0.812**, recall **0.904**, mAP50 **0.938**, and mAP50–95 **0.677**. These are small-sample results.

## Example annotations and predictions

- [Four training annotations](annotation_examples.png): two backhoe-loader and two excavator examples with the saved ground-truth boxes.
- [Ten validation predictions](validation_predictions_grid.png): fixed, filename-sorted selection of eight labeled and two negative photos.
- [All 13 held-out test predictions](test_predictions_grid.png): labels and predictions shown together, including the negative image.
- [Five-photo inference demonstration](five_test_predictions.png): rear-view backhoe loader, negative tractor, sideways backhoe loader, site excavator, and excavator with duplicate boxes.

### Three clear detections

1. Rear-view backhoe loader in the [five-photo demonstration](five_test_predictions.png), confidence 0.85.
2. Backhoe loader at the site in the [test prediction grid](test_predictions_grid.png), confidence 0.88.
3. Excavator at the site in the [five-photo demonstration](five_test_predictions.png), confidence 0.86.

### Three instructive errors

1. The negative front-loader tractor receives **two false detections** (`Backhoe Loader` 0.37 and `excavator` 0.35) in the [five-photo demonstration](five_test_predictions.png). It resembles target machinery.
2. The sideways backhoe loader receives **no detection** at the 0.25 confidence threshold in the [test prediction grid](test_predictions_grid.png). In the [orientation comparison](orientation_comparison.png), rotating that same photo upright leads to a Backhoe Loader prediction at 0.81. This is a diagnostic on one image; the original test result remains unchanged.
3. An excavator on a transport vehicle receives **no detection** in the [test prediction grid](test_predictions_grid.png). Its unfamiliar context likely contributes to the miss.

The [test grid](test_predictions_grid.png) also shows an excavator with two overlapping predicted boxes. The notebook provides filenames and confidence scores for every example. The photographs are attributed in the [repository README](../README.md).
