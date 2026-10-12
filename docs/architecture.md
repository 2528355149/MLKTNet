# Method Overview

> **High-level description only.** The technical details, equations, and the exact
> implementation will be released together with the code.

**MLKTNet** is a modality-aware knowledge-transfer network for multi-modal brain tumor
segmentation under **randomly missing modalities**.

It follows a **multi-level (channel / semantic / structural / output) knowledge-transfer**
design: knowledge from a full-modality teacher is transferred to a lightweight student, so that
the student remains robust across missing-modality combinations — **without synthesizing
missing data** and **without maintaining a separate branch per modality combination**.

The student takes a fixed 4-channel input (missing modalities zero-filled) together with a
4-dimensional modality-availability vector, so **a single set of weights covers all 15
non-empty modality combinations**.

The individual modules, their objectives, and the full training / inference configuration are
described in the paper and will be released with the code.
