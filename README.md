# MTrsDRP
Source code and data for "MTrsDRP: interpretable molecular self-attention transformer based on multi-omics for drug response prediction in cancer cell lines"
## Data
- Cell_line_RMA_proc_basalExp.csv -Gene expression data used for model training.
- Cell_line_RMA_proc_basalExp.txt -Gene expression data used for model training.
- Cell_list.csv -List of cancer cell line data information.
- drug_smiles.csv -Contains information about all drug smiles.
- Druglist.csv -All drugs involved in the training of the model.
- METH_CELLLINES_BEMs_PANCAN.csv -DNA methylation data used for model training.
- PANCANCER_Genetic_feature.csv -Genomic mutation data used for model training.
- PANCANCER_IC.csv -Drug response data for known cancer cell lines in the GDSC2 database.
- pychem_cid.csv -pychem cid information for model training drugs.
- small_molecule.csv -Small molecule information for model training drugs.
- unknow_drug_by_pychem.csv-No drugs listed for pychem cid.
## Source codes
- Data_encoding.py:The drug data and cancer cell line data are encoded into pytorch tensor format for subsequent model training. Partitioning of the data into training, test and validation sets will also be completed.
- Model_training.py:Contains the overall framework for the model, using drug data and cancer cell line data for drug response prediction.
- Model_utils.py:Function call support for the data encoding, model training and model validation sections of the code.
- Model_validation.py:The trained model is validated to check the generalisation and accuracy of the model.
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


