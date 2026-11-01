# Data

The raw bioactivity tables are public and are not stored in this repository.

| File expected by the notebook | Source |
|---|---|
| `AID_540276_datatable_active.csv` | PubChem BioAssay AID 540276, active compounds (Download > CSV data table) |
| `AID_540276_datatable_inactive.csv` | PubChem BioAssay AID 540276, inactive compounds |
| `AID_720532_datatable_active.csv` | PubChem BioAssay AID 720532, active compounds |
| `AID_720532_datatable_inactive.csv` | PubChem BioAssay AID 720532, inactive compounds |

Assay pages: https://pubchem.ncbi.nlm.nih.gov/bioassay/540276 and https://pubchem.ncbi.nlm.nih.gov/bioassay/720532

In Part 1 the notebook reads these files from a Kaggle dataset path (`/kaggle/input/datasets/suyaibalsifat/aid-final/`). Edit the four `/kaggle/input/...` paths in Part 1 and Part 18 to wherever you save the files.
