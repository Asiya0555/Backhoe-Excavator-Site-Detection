# AECO Governance Checklist

## 1. Data provenance

- **Frozen data:** Roboflow project `asiya-begum-aurak-ac-ae/excavator-backhoe-detection-in-construction-site_ab`, version 3, 131 exported images. The SHA256 checksum is recorded in the README.
- **Primary source:** [Excavator Construction Vehicle by DataCluster Labs](https://universe.roboflow.com/datacluster-labs-agryi/excavator-construction-vehicle), shown as CC BY 4.0 on Roboflow Universe. Although its original class is named `excavator`, this project's visible source machines were reviewed and labeled as `Backhoe Loader` where appropriate. The public source project contains 100 images; its description offers a larger commercial collection separately.
- **Additional source:** [Excavators by Mohamed Sabek](https://universe.roboflow.com/mohamed-sabek-6zmr6/excavators-cwlh0), shown as CC BY 4.0 on Roboflow Universe. Imported examples were reviewed and labeled as `excavator` in this project.
- **Collection dates:** Source images include filenames bearing 2022 timestamps; this is not independent verification of the image capture date. Record the source dataset's stated date if available.
- **Changes:** Two target classes were curated; ambiguous and unsuitable examples were excluded, related machine views grouped into splits, labels reviewed, and version 3 auto-oriented and resized images to 640 × 640 with black padding.

## 2. Privacy and PII handling

- **Faces and license plates:** Review the 131 exported photographs before a public Release and record whether any identifiable face, plate, or client/site identifier is visible. **Status: not yet confirmed.**
- **Action if found:** Remove or blur the affected images and generate a new Roboflow version and ZIP, or establish permission to publish. Train and document the exact version ultimately released.
- **Secrets:** The notebook's main data path must work without credentials. No API keys may appear in code, output, or Git history.

## 3. Risk statement

- **False negative:** A visible backhoe loader or excavator may be missed, leading to an incomplete snapshot of equipment visible in a site photo.
- **False positive:** A different machine may be misidentified, leading to an unnecessary follow-up or an incorrect interpretation of the photo.
- **Limits:** This image detector does not establish a unique equipment identity, a reliable machine count across repeated photos, operating time, or hire-hour records. The evaluation set is small and includes known orientation and lookalike failures.

## 4. Human review

An architect, site engineer, or equipment coordinator checks the image and proposed boxes before using the output in any project record. They can correct class and box placement and flag cases for retraining. This prototype must not be the sole basis for contractual, financial, or safety decisions.

## 5. License

- **Original repository code and prose:** MIT; see `LICENSE`.
- **Dataset images:** Both identified source projects list [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) on Roboflow Universe. The README and Release notes credit DataCluster Labs and Mohamed Sabek, link to their projects and the license, and describe the changes. No original image ownership is claimed by this repository. The public license grants reuse subject to its terms; source descriptions do not independently establish every contributor's rights or separate privacy permissions.
