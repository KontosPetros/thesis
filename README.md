# ZooLake plankton classification thesis

Repository for Petros Kontos' diploma thesis on deep-learning classification of 35 ZooLake plankton classes. The experimental comparison covers a custom CNN, EfficientNetB2, MobileNetV1, and ConvNeXtBase under from-scratch and transfer-learning strategies.

## Current status

- The exact thesis version sent for supervisor review on 2026-09-04 is frozen under `thesis/supervisor-review-2026-09-04/`.
- Checksums for the currently public result artifacts are recorded in `results/artifact_checksums.sha256`.
- A detailed experiment registry has been prepared separately and will be published only after the publication scope of non-public evidence is explicitly confirmed.
- No new experiment should replace a reported value unless its notebook, split manifest, configuration, and result artifact are archived together.

## Key result

ConvNeXtBase has the strongest verified test result: 96.54% accuracy and 91.15% macro-F1. It follows a separately documented protocol and a deduplicated semantic split manifest, so it is not presented as a strictly controlled architecture-only comparison with the common-protocol runs.

## Repository map

| Path | Contents |
| --- | --- |
| `results/` | Checksums for public result artifacts |
| `data/manifests/` | Manifest inventory and reproducibility gaps |
| `thesis/` | Frozen supervisor-review snapshots |

The original notebooks and result archives remain at the repository root for the moment. They will be reorganized only after references and checksums are preserved, to avoid breaking provenance during cleanup.

## Reproducibility rules

1. Use seed `12345` where the run specifies it.
2. Keep train augmentation separate from validation/test preprocessing.
3. Select checkpoints using validation loss only.
4. Evaluate the test set after the checkpoint is fixed.
5. Report accuracy, macro precision, macro recall, macro-F1, and top-2 accuracy at full precision in machine-readable files.
6. Treat the ConvNeXtBase protocol and manifest as a separate experimental group.

## Known audit items

- The archived Custom CNN oversampling artifact contains six oversampled classes, including `unknown_plankton`, and 13,012 post-sampling rows. The thesis text currently states five classes and 12,961 rows; the metrics themselves match the archived artifact.
- The final EfficientNetB2 oversampling values appear in the frozen thesis snapshot, but the matching full run package/configuration is not in the public repository. That row is marked `thesis_snapshot_only`.

Do not edit result tables from memory; verify them against the frozen snapshot and the matching public result artifact.
