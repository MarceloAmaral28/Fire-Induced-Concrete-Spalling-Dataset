# Fire-Induced Concrete Spalling Dataset

This repository contains a literature-derived dataset for machine-learning classification of fire-induced concrete spalling. It includes 904 experimental records from 47 bibliographic references.

The data concern reduced concrete specimens exposed to elevated temperatures without external mechanical loading or deformation restraint. Therefore, they do not directly represent loaded or restrained structural elements.

## Data provenance

The compilation includes records previously gathered by Liu and Zhang (2020a, 2020b, 2020c) and Liu et al. (2021, 2022), together with records from additional bibliographic sources included in the present dataset.

These five previously compiled sources correspond to reference IDs 33–35, 37, and 41 in `reference_mapping.csv`. The correspondence between all dataset reference identifiers and the original bibliographic sources is provided in that file.

## Files

| File | Description |
| --- | --- |
| `dataset_original.csv` | Original dataset with 17 predictors, the `Reference` control column, and the `output` target. Missing values are retained. |
| `dataset_processed_17_variables.csv` | Processed dataset with `idx_original`, `Reference`, 17 predictors, and `output`. It contains no missing values. |
| `reference_mapping.csv` | Mapping between the 47 reference identifiers and their bibliographic information. |

## Column roles

- `idx_original` identifies the corresponding row in the original dataset and is used only for traceability.
- `Reference` identifies the source reference and is used for traceability and reference-based partitioning.
- `output` is the binary target: `0` indicates no spalling and `1` indicates spalling.
- All remaining columns in `dataset_processed_17_variables.csv` are the 17 predictors.

`idx_original` and `Reference` are not predictors and must not be included in the model input matrix.

## Preprocessing

The original dataset contains 50 missing values across 22 records. In the processed dataset:

- 22 missing values for maximum aggregate size were assigned 16 mm.
- 14 missing coarse-aggregate-to-binder ratios and 14 missing fine-aggregate-to-binder ratios were estimated by dividing the reported total aggregate content equally between the two fractions.

Apart from these imputations and the addition of `idx_original`, the values and row order were preserved.

## Code availability

The analysis and modeling code is not included in the current release. It is available upon request from the corresponding author.

## Related article

An article associated with this dataset is currently being prepared for submission. Citation details will be added upon publication.

## Citation

Once the associated article is published, citation details will be added here. Users of this dataset should also cite the relevant original sources listed in `reference_mapping.csv`.
