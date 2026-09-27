# AECO problem and evaluation goal

Construction teams may review dated site photographs alongside equipment hire records. This prototype detects visible **backhoe loaders** and **excavators** in individual photos and proposes a class, box, and confidence score for each. A supervisor can review those detections before using them in a separate cost-review workflow. The model does not identify a particular machine across days or measure hire duration.

The provisional target for this small experiment was **test recall of at least 0.70**, while reporting precision, mAP50, and mAP50–95 and inspecting false positives and false negatives. Roboflow version 3 contains 105 training, 13 validation, and 13 held-out test photos: approximately **80% training and 20% evaluation**. The two classes and negative-image rules are defined in [class_definitions.md](class_definitions.md). The [README](../README.md#does-it-work) reports the resulting test scores and limitations.
