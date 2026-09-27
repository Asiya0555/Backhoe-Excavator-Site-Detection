# AECO Governance Checklist

## 1. Data provenance

- **Frozen data:** Roboflow project `asiya-begum-aurak-ac-ae/excavator-backhoe-detection-in-construction-site_ab`, version 3, 131 exported images. The SHA256 checksum is recorded in the README.
- **Primary source:** [Excavator Construction Vehicle by DataCluster Labs](https://universe.roboflow.com/datacluster-labs-agryi/excavator-construction-vehicle), shown as CC BY 4.0 on Roboflow Universe. Although its original class is named `excavator`, this project's visible source machines were reviewed and labeled as `Backhoe Loader` where appropriate. The public source project contains 100 images; its description offers a larger commercial collection separately.
- **Additional source:** [Excavators by Mohamed Sabek](https://universe.roboflow.com/mohamed-sabek-6zmr6/excavators-cwlh0), shown as CC BY 4.0 on Roboflow Universe. Imported examples were reviewed and labeled as `excavator` in this project.
- **Image ownership:** The original image rights remain with the respective source licensors; this project does not claim ownership of the photographs.
- **Collection dates:** The DataCluster Labs source describes its images as captured during 2020–2022, and some source filenames contain 2022 date strings. Exact capture dates for the individual photos in this 131-image export were not independently verified.
- **Changes:** Two target classes were curated; ambiguous and unsuitable examples were excluded, related machine views grouped into splits, labels reviewed, and version 3 auto-oriented and resized images to 640 × 640 with black padding.

## 2. Privacy and PII handling

- **Faces and license plates:** A contact-sheet review of all 131 exported images and full-size checks of selected photos on 27 September 2026 found people in several street/site scenes and a readable passenger-car registration in a training photograph (`20221128_07_06_57...rf.6bfe2245...jpg`). A visual scan cannot establish whether every person is identifiable. **Frozen version 3 was not blurred and may contain personal details.**
- **Consent and permission:** The two source projects display CC BY 4.0 and are credited. Separate documentation of consent from photographed people or permission to disclose private site details was not available for this review.
- **Data minimization:** The experiment uses site photographs and target/negative labels for two equipment classes. The detector does not require names, hire records, personnel identifiers, or precise site locations.
- **Protection and follow-up:** The public Release preserves the data actually used for the reported experiment; it has not been privacy-sanitized and is not an operational image store. Before any further redistribution or production use, full-resolution photos should be reviewed for identifiable people, plates, and site details; affected details should be removed or obscured where permission is absent. A changed training ZIP would require a new checksum and release asset, with retraining or a clear distinction from the data used for the published weights. The current Release is not described as anonymized.
- **Secrets:** The notebooks use fixed public Release URLs for the main data path and require no API key or account.

## 3. Risk statement

- **False negative:** A visible backhoe loader or excavator may be missed, leading to an incomplete snapshot of equipment visible in a site photo.
- **False positive:** A different machine may be misidentified, leading to an unnecessary follow-up or an incorrect interpretation of the photo.
- **Limits:** This image detector does not establish a unique equipment identity, a reliable machine count across repeated photos, operating time, or hire-hour records. The evaluation set is small and includes known orientation and lookalike failures.

## 4. Human review

An architect, site engineer, or equipment coordinator checks the image and proposed boxes before using the output in any project record. They can correct class and box placement and flag cases for retraining. This prototype must not be the sole basis for contractual, financial, or safety decisions.

## 5. License

- **Original repository code and prose:** MIT; see `LICENSE`.
- **Dataset images:** Both identified source projects list [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) on Roboflow Universe. The README and Release notes credit DataCluster Labs and Mohamed Sabek, link to their projects and the license, and describe the changes. No original image ownership is claimed by this repository. The public license grants reuse subject to its terms; source descriptions do not independently establish every contributor's rights or separate privacy permissions.
