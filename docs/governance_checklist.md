# AECO Governance Checklist

## 1. Data provenance

- **Sources and ownership:** The frozen Roboflow [version 3](https://universe.roboflow.com/asiya-begum-aurak-ac-ae/excavator-backhoe-detection-in-construction-site_ab/dataset/3) contains 131 images selected from [DataCluster Labs](https://universe.roboflow.com/datacluster-labs-agryi/excavator-construction-vehicle) and [Mohamed Sabek](https://universe.roboflow.com/mohamed-sabek-6zmr6/excavators-cwlh0). Both source projects list CC BY 4.0. Original image rights remain with their respective licensors; this repository does not claim ownership.
- **Dates:** DataCluster Labs describes captures during 2020–2022; some filenames contain 2022 dates. Individual capture dates in this export were not independently verified.
- **Preparation:** Selected backhoe loaders were relabeled, excavators added, five unsuitable photos excluded, related views grouped by split where identified, and version 3 auto-oriented and resized to 640 × 640. The frozen ZIP and SHA256 are linked in the [README](../README.md#method-and-data).

## 2. Privacy and consent

- **PII review:** A review of all 131 images as a contact sheet and selected full-size photos found people in several scenes and a readable passenger-car registration in one training photo (`20221128_07_06_57...rf.6bfe2245...jpg`). The released images were **not blurred or anonymized**. Separate documentation of photographed people's consent or private-site disclosure permission was unavailable.
- **Data minimization and protection:** The detector uses photos and two equipment labels, not names, personnel details, precise locations, or hire records. Before further redistribution or operational use, review full-size images for identifiable people, plates, and site details and remove or obscure affected details where permission is absent. Changing the frozen training ZIP requires a new checksum and release asset; retrain or clearly distinguish new public data from the data used for the published weights.
- **Secrets:** The notebooks use public fixed Release URLs. No API key or account is needed.

## 3. Risk and limitations

- **False negative:** A missed target leaves an incomplete snapshot of visible equipment. **False positive:** A lookalike machine can cause an unnecessary follow-up or wrong interpretation.
- **Limits:** The small test set and known orientation and lookalike failures prevent claims of reliable site-wide counting. A box does not identify a unique machine across dates or measure operating time or hire hours. Do not use this prototype alone for contractual, financial, or safety decisions.

## 4. Human review

An architect, site engineer, or equipment coordinator checks source photos, classes, and boxes before using detections in a project record. They can correct errors and flag examples for dataset improvement.

## 5. License

Original repository code and prose use [MIT](../LICENSE). The two linked source projects list [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) for their images. The README and Release credit both sources and describe the relabeling and other changes. A public license listing does not independently establish every contributor's image rights or separate privacy permission.
