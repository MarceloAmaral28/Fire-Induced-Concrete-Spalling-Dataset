# Fire-Induced Concrete Spalling Dataset

This repository contains a literature-derived dataset for machine-learning classification of fire-induced concrete spalling. It includes 904 experimental records from 47 references.

The data concern reduced concrete specimens exposed to elevated temperatures without external mechanical loading or deformation restraint. Therefore, they do not directly represent loaded or restrained structural elements.

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

An article associated with this dataset is currently being prepared for submission. Citation details will be added upon publication.

## Related article

An article associated with this dataset is currently being prepared for submission. Citation details will be added upon publication.
