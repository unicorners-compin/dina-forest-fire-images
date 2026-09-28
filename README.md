# Forest-fire image set used in the DINA case study

This release contains 4,469 JPEG image samples collected and manually labeled
by the authors for a binary fire/non-fire task: 2,208 `fire` samples and 2,261
`non-fire` samples. It is not a release of the third-party RescueNet dataset.
Acquisition dates, devices, and a detailed annotation protocol are not asserted
because they have not been verified for this release.

## License and attribution

The images, labels, and metadata in this release are provided by the DINA study
authors under the Creative Commons Attribution 4.0 International license
(CC BY 4.0): https://creativecommons.org/licenses/by/4.0/legalcode . When using
them, credit the DINA study authors (Zhiyuan Ren, Tao Zhang, and Wenchi Cheng),
link to this repository and the license, and indicate if changes were made.
This license does not apply to the third-party RescueNet dataset or to software
outside this dataset release.

## Files

- `images/fire/` and `images/non-fire/`: labeled JPEG samples.
- `file-manifest.csv`: relative image path, class, file SHA-256, and decoded-pixel
  SHA-256. Every released image has been checked against the archived source
  manifest.
- `submitted-assignments.tsv` and `submitted-split-manifest.json`: the exact
  historical train/validation/test assignment used for the submitted receiver
  model (2,996/736/737 samples). TSV columns are filename group, split, class,
  and path relative to `images/`.
- `retrospective-clean-assignments.tsv` and
  `retrospective-clean-split-manifest.json`: a later source-cluster audit and
  revised assignment (2,985/741/743 samples). TSV columns are filename group,
  conservative source cluster, old split, revised split, class, and relative
  path. This revised test set is a retrospective sensitivity resource, not the
  previously untouched test set for the submitted results.

The historical split grouped images by filename prefix. A later content audit
identified related images under different prefixes and across historical
partitions. Consequently, the historical split must not be described as fully
source-disjoint. In `submitted-split-manifest.json`, `source_group_overlap: 0`
refers only to the original filename-prefix groups; it is not a claim that
content-related source images do not cross partitions. The revised split separates the source relationships found by
that audit; it does not establish that every possible relation was found.

These are image-classification samples, not the raw UAV packet captures,
receiver model weights, or the third-party RescueNet corpus. The packet-network
results in the submitted paper used the historical split and are not silently
replaced by results from the retrospective split.
