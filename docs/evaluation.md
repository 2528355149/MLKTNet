# Evaluation Protocol

## Metrics

Two metrics are reported on the three standard BraTS regions — **WT** (whole tumor),
**TC** (tumor core), and **ET** (enhancing tumor):

- **Dice similarity coefficient (Dice)**;
- **95% Hausdorff distance (HD95)**.

The case-level metric is the average over the three regions.

Edge handling: if both prediction and ground truth are empty in a region, the region is recorded
as `0`; if only one of them is empty, it is recorded as `NaN` and excluded from the statistics.

## Modality combinations

Evaluation covers **all 15 non-empty subsets** of `{FLAIR, T1, T1ce, T2}` (from full modality
down to single modality).

## Inference protocol

Sliding-window inference is performed over each volume; metrics are computed per case, averaged
within each modality combination, and finally averaged over all 15 combinations. The **exact
inference settings** will be released together with the code.

## Comparison setting

Inference sets the 15 modality-availability combinations per case and compares against
11 state-of-the-art methods on **BraTS 2020**, all under the **same data split and evaluation
protocol**.

## Ablation setting

A full-combination ablation of the three proposed modules yields **8 configurations**,
each trained once, on **BraTS 2018 / 2019**. The `baseline` is a student trained with only the
output-level KL distillation.
