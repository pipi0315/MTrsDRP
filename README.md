# MTrsDRP
Source code and data for "MTrsDRP: interpretable molecular self-attention transformer based on multi-omics for drug response prediction in cancer cell lines"
## Data
- Cell_line_RMA_proc_basalExp.csv -
- Cell_line_RMA_proc_basalExp.txt -
- Cell_list.csv -
- drug_smiles.csv -
- Druglist.csv -
- METH_CELLLINES_BEMs_PANCAN.csv -
- PANCANCER_Genetic_feature.csv -
- PANCANCER_IC.csv -
- pychem_cid.csv -
- small_molecule.csv -
- unknow_drug_by_pychem.csv-
## Source codes
- Data_encoding.py:
- Model_training.py:
- Model_utils.py:
- Model_validation.py:
## Requirements
>requirements.yaml contains all the installation packages required for the model runtime environment
 - torch==1.10.2+cu113
 - python==3.8.3
 - rdkit==2022.3.3
 - deepchem==2.4.0
 - pandas==1.4.3
 - numpy==1.21.4
 - scipy==1.8.1
 - torch-cluster==1.5.9
 - torch-geometric==2.0.4
 - torch-scatter==2.0.9
 - torch-sparse==0.6.12
 - torch-spline-conv==1.2.1
 - torchaudio==0.10.2+cu113
 - torchsummary==1.5.1
 - torchvision==0.11.3+cu113
 # Step-by-step running:
 ## 1. Create data in pytorch tensor format
     python Data_encoding.py
xxxxxx
 ## 2. Train a MTrsDRP model
    python Model_training.py --model 0 --train_batch 1024 --val_batch 1024 --test_batch 1024 --lr 0.0002 --num_epoch 300 --log_interval 20 --cuda_name "cuda:0"
xxxx


