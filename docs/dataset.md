# Datasets & Preprocessing

## Datasets

Experiments are conducted on **BraTS 2018, 2019, and 2020**, with **285 / 335 / 369** training
cases respectively.

- Each case provides four MRI modalities (`FLAIR`, `T1`, `T1ce`, `T2`) and expert annotations.
- A fixed training / validation split is used throughout all experiments.
- **BraTS 2020** is used for the **comparison** experiments; **BraTS 2018 / 2019** for the
  **ablation** studies.

## Preprocessing

A standard BraTS preprocessing pipeline is adopted (background removal, per-modality intensity
normalization, and patch-based sampling). The **exact preprocessing and augmentation settings**
are part of the implementation and will be released together with the code.

## Missing-modality simulation

Missing modalities are simulated by **online random dropping** during training, so that all
**15 non-empty modality combinations** are covered.

## Teacher–student alignment

The teacher is trained on **full modalities** and its features are exported offline; the
student is aligned to them. **Alignment details** will be released with the code.

## Data access

BraTS data must be obtained from the official challenge (registration required).
**We do not redistribute the data or any derived patient-identifiable material.**
