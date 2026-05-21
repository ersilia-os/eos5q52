# Antimicrobial activity prediction against Streptococcus pneumoniae from public ChEMBL data

Bioactivity prediction of growth inhibition in Streptococcus pneumoniae, trained as binary (active/inactive) classifiers from publicly available data in ChEMBL. Independent models are trained on multiple bioactivity datasets, corresponding to dose-response (MIC) assays, among others. A ranking score is provided for each model alongside a combined consensus score.

This model was incorporated on 2026-05-19.Last packaged on 2026-05-21.

## Information
### Identifiers
- **Ersilia Identifier:** `eos5q52`
- **Slug:** `antimicrobial-activity-spneumoniae`

### Domain
- **Task:** `Annotation`
- **Subtask:** `Activity prediction`
- **Biomedical Area:** `Pneumonia`
- **Target Organism:** `Streptococcus pneumoniae`
- **Tags:** `Gram-positive bacteria`, `Antimicrobial activity`, `ChEMBL`

### Input
- **Input:** `Compound`
- **Input Dimension:** `1`

### Output
- **Output Dimension:** `23`
- **Output Consistency:** `Fixed`
- **Interpretation:** Probability of antimicrobial activity against Streptococcus pneumoniae from 22 ChEMBL-trained sub-models, plus a quality-weighted consensus score.

Below are the **Output Columns** of the model:
| Name | Type | Direction | Description |
|------|------|-----------|-------------|
| consensus_score | float | high | Tanh-transformed quality-weighted consensus probability across the 22 sub-models. Recommended threshold: 0.964. |
| merged_mic_decoys_a | float | high | Probability from sub-model trained on MIC measurements merged across 12 ChEMBL assays (cutoff 10 uM; n=2740 incl. decoys). Recommended threshold: 0.889. |
| merged_mic_decoys_q | float | high | Probability from sub-model trained on MIC measurements merged across 9 ChEMBL assays (cutoff 10 uM; n=2560 incl. decoys). Recommended threshold: 0.893. |
| merged_mic_decoys_p | float | high | Probability from sub-model trained on MIC measurements merged across 7 ChEMBL assays (cutoff 10 uM; n=2080 incl. decoys). Recommended threshold: 0.869. |
| merged_mic_decoys_o | float | high | Probability from sub-model trained on MIC measurements merged across 8 ChEMBL assays (cutoff 10 uM; n=1940 incl. decoys). Recommended threshold: 0.878. |
| merged_mic_decoys_n | float | high | Probability from sub-model trained on MIC measurements merged across 6 ChEMBL assays (cutoff 10 uM; n=1560 incl. decoys). Recommended threshold: 0.881. |
| merged_mic_decoys_k | float | high | Probability from sub-model trained on MIC measurements merged across 7 ChEMBL assays (cutoff 10 uM; n=1330 incl. decoys). Recommended threshold: 0.895. |
| merged_mic_decoys_i | float | high | Probability from sub-model trained on MIC measurements merged across 6 ChEMBL assays (cutoff 10 uM; n=1190 incl. decoys). Recommended threshold: 0.888. |
| merged_mic_decoys_l | float | high | Probability from sub-model trained on MIC measurements merged across 7 ChEMBL assays (cutoff 10 uM; n=1050 incl. decoys). Recommended threshold: 0.862. |
| merged_mic_decoys_r | float | high | Probability from sub-model trained on MIC measurements merged across 3 ChEMBL assays (cutoff 10 uM; n=1040 incl. decoys). Recommended threshold: 0.857. |

_10 of 23 columns are shown_
### Source and Deployment
- **Source:** `Local`
- **Source Type:** `Internal`
- **DockerHub**: [https://hub.docker.com/r/ersiliaos/eos5q52](https://hub.docker.com/r/ersiliaos/eos5q52)
- **Docker Architecture:** `AMD64`
- **S3 Storage**: [https://ersilia-models-zipped.s3.eu-central-1.amazonaws.com/eos5q52.zip](https://ersilia-models-zipped.s3.eu-central-1.amazonaws.com/eos5q52.zip)

### Resource Consumption
- **Model Size (Mb):** `144`
- **Environment Size (Mb):** `1888`
- **Image Size (Mb):** `2366.73`

**Computational Performance (seconds):**
- 10 inputs: `62.3`
- 100 inputs: `55.39`
- 10000 inputs: `1294.84`

### References
- **Source Code**: [https://github.com/ersilia-os/chembl-antimicrobial-models](https://github.com/ersilia-os/chembl-antimicrobial-models)
- **Publication**: [https://github.com/ersilia-os/chembl-antimicrobial-models](https://github.com/ersilia-os/chembl-antimicrobial-models)
- **Publication Type:** `Other`
- **Publication Year:** `2026`
- **Ersilia Contributor:** [arnaucoma24](https://github.com/arnaucoma24)

### License
This package is licensed under a [GPL-3.0](https://github.com/ersilia-os/ersilia/blob/master/LICENSE) license. The model contained within this package is licensed under a [GPL-3.0-or-later](LICENSE) license.

**Notice**: Ersilia grants access to models _as is_, directly from the original authors, please refer to the original code repository and/or publication if you use the model in your research.


## Use
To use this model locally, you need to have the [Ersilia CLI](https://github.com/ersilia-os/ersilia) installed.
The model can be **fetched** using the following command:
```bash
# fetch model from the Ersilia Model Hub
ersilia fetch eos5q52
```
Then, you can **serve**, **run** and **close** the model as follows:
```bash
# serve the model
ersilia serve eos5q52
# generate an example file
ersilia example -n 3 -f my_input.csv
# run the model
ersilia run -i my_input.csv -o my_output.csv
# close the model
ersilia close
```

## About Ersilia
The [Ersilia Open Source Initiative](https://ersilia.io) is a tech non-profit organization fueling sustainable research in the Global South.
Please [cite](https://github.com/ersilia-os/ersilia/blob/master/CITATION.cff) the Ersilia Model Hub if you've found this model to be useful. Always [let us know](https://github.com/ersilia-os/ersilia/issues) if you experience any issues while trying to run it.
If you want to contribute to our mission, consider [donating](https://www.ersilia.io/donate) to Ersilia!
