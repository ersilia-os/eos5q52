# Antimicrobial activity prediction against Streptococcus pneumoniae from public ChEMBL data

Bioactivity prediction of growth inhibition in Streptococcus pneumoniae, trained as binary (active/inactive) classifiers from publicly available data in ChEMBL. Independent models are trained on multiple bioactivity datasets, corresponding to single-point (Inhibition) and dose-response (MIC) assays, among others. A ranking score is provided for each model alongside a combined consensus score.

This model was incorporated on 2026-05-19.Last packaged on 2026-06-02.

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
- **Output Dimension:** `9`
- **Output Consistency:** `Fixed`
- **Interpretation:** Probability of antimicrobial activity against Streptococcus pneumoniae from 8 ChEMBL-trained sub-models, plus a quality-weighted consensus score.

Below are the **Output Columns** of the model:
| Name | Type | Direction | Description |
|------|------|-----------|-------------|
| consensus_score | float | high | Tanh-transformed quality-weighted consensus probability across the 8 sub-models. Recommended threshold: 0.586. |
| chembl_single_point_0 | float | high | Probability from sub-model trained on ChEMBL single-point low-data catch-all pool of 92 assays (178 compounds). Recommended threshold: 0.537. |
| chembl_dose_response_0 | float | high | Probability from sub-model trained on ChEMBL dose-response signal-based pool of 301 assays (4070 compounds; incl. 1048 added negatives). Recommended threshold: 0.498. |
| chembl_dose_response_1 | float | high | Probability from sub-model trained on ChEMBL dose-response signal-based pool of 347 assays (3180 compounds). Recommended threshold: 0.557. |
| chembl_dose_response_2 | float | high | Probability from sub-model trained on ChEMBL dose-response signal-based pool of 149 assays (1680 compounds; incl. 306 added negatives). Recommended threshold: 0.514. |
| chembl_dose_response_3 | float | high | Probability from sub-model trained on ChEMBL dose-response signal-based pool of 172 assays (1500 compounds; incl. 335 added negatives). Recommended threshold: 0.489. |
| chembl_dose_response_4 | float | high | Probability from sub-model trained on ChEMBL dose-response signal-based pool of 169 assays (1048 compounds; incl. 39 added negatives). Recommended threshold: 0.492. |
| chembl_dose_response_5 | float | high | Probability from sub-model trained on ChEMBL dose-response signal-based pool of 62 assays (798 compounds; incl. 180 added negatives). Recommended threshold: 0.475. |
| chembl_dose_response_6 | float | high | Probability from sub-model trained on ChEMBL dose-response signal-based pool of 35 assays (581 compounds). Recommended threshold: 0.768. |


### Source and Deployment
- **Source:** `Local`
- **Source Type:** `Internal`
- **DockerHub**: [https://hub.docker.com/r/ersiliaos/eos5q52](https://hub.docker.com/r/ersiliaos/eos5q52)
- **Docker Architecture:** `AMD64`, `ARM64`
- **S3 Storage**: [https://ersilia-models-zipped.s3.eu-central-1.amazonaws.com/eos5q52.zip](https://ersilia-models-zipped.s3.eu-central-1.amazonaws.com/eos5q52.zip)

### Resource Consumption
- **Model Size (Mb):** `247`
- **Environment Size (Mb):** `1890`
- **Image Size (Mb):** `2391.08`

**Computational Performance (seconds):**
- 10 inputs: `51.85`
- 100 inputs: `48.71`
- 10000 inputs: `1425.96`

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
