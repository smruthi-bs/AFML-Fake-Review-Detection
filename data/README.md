# Data Folder

**DO NOT UPLOAD DATASETS HERE.**

This folder is for storing the local datasets. To run the project:

1. Go to our Shared Google Drive: https://drive.google.com/drive/folders/1APbogrSPWCCZwwCnpbZFH0V2C6bSwu08?usp=sharing
2. Download `TRAIN_model_ready_final_mode.csv` and `TEST_model_ready_final_mode.csv`.
3. Place them in this folder.
4. Download the `graph/` folder from Drive and place it in `data/graph/`.

**File Structure should look like:**
```text
/data
├── TRAIN_model_ready_final_mode.csv
├── TEST_model_ready_final_mode.csv
├── train_bert_embeddings.npy
├── test_bert_embeddings.npy
└── graph/
    ├── hetero_graph_train.pt
    ├── user_map.json
    └── gmap_map.json
