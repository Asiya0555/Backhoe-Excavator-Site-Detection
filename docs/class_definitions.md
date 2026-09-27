# Classes and labeling rules

This is a two-class **object detection** dataset. Draw a box around the visible extent of each identifiable target machine, including its attachments when visible. The label describes the complete machine, not just its bucket or digging arm.

| ID | Class | Visual rule |
|---:|---|---|
| 0 | `Backhoe Loader` | A tractor-like wheeled machine with a front loading bucket and a rear digging arm. Use the visible vehicle configuration, not its color or one attachment alone. |
| 1 | `excavator` | A machine with an excavating boom and upper body on a tracked or wheeled undercarriage, without the backhoe loader's front-loader/rear-backhoe arrangement. |

For a partly cropped or obstructed machine, assign a class only when enough distinguishing structure remains visible. Review or exclude ambiguous crops rather than guessing from a yellow vehicle, a bucket, or an isolated arm. If neither target is present, keep the image as a **negative example** with no target box; `null` and `background` are not training classes. Similar views of the same machine should remain together in one data split where identifiable.

The dataset is an image-level prototype: a box does not identify a unique machine across dates or prove its working time.
