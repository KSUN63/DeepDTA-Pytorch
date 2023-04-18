# DeepDTA-Pytorch
Pytorch Implementation of the original DeepDTA paper (https://github.com/hkmztrk/DeepDTA/)

Requirements (most of them come with Anaconda except torch, pytorch-cuda, and tqdm)

python==3.8.16  
numpy==1.24.1  
pandas==1.5.2  
matplotlib==3.5.3  
scipy==1.8.1  
torch==2.1.0  
pytorch-cuda==11.7  
tqdm==4.65.0  



The data format should be in the form of a csv file with four columns: proteins, ligands, affinity, split, where proteins store all the sequence information, ligands store the isomeric smile strings of the molecular binders, and affinity was either the Kd/Ki value or the bidning affinity in kcal/mol (this needs to be consistent for all data). The final split column will have three possible values that indicate the train-val-test splitting: 'train', 'val', and 'test'.

To run the code, go to deepdta_retrain.py to do the appropriate modification of fp and then run python deepdta_retrain.py

For analysis, there's a separate jupyter notebook files for some preliminary scatter plots and using the trained model to analyze a held-out set of data. Make sure to change the name of ligand_dict and protein_dict and the model you want to use to your choices.


## Citation

@article{10.1093/bioinformatics/bty593,
    author = {Öztürk, Hakime and Özgür, Arzucan and Ozkirimli, Elif},
    title = "{DeepDTA: deep drug–target binding affinity prediction}",
    journal = {Bioinformatics},
    volume = {34},
    number = {17},
    pages = {i821-i829},
    year = {2018},
    month = {09},
    abstract = "{The identification of novel drug–target (DT) interactions is a substantial part of the drug discovery process. Most of the computational methods that have been proposed to predict DT interactions have focused on binary classification, where the goal is to determine whether a DT pair interacts or not. However, protein–ligand interactions assume a continuum of binding strength values, also called binding affinity and predicting this value still remains a challenge. The increase in the affinity data available in DT knowledge-bases allows the use of advanced learning techniques such as deep learning architectures in the prediction of binding affinities. In this study, we propose a deep-learning based model that uses only sequence information of both targets and drugs to predict DT interaction binding affinities. The few studies that focus on DT binding affinity prediction use either 3D structures of protein–ligand complexes or 2D features of compounds. One novel approach used in this work is the modeling of protein sequences and compound 1D representations with convolutional neural networks (CNNs).The results show that the proposed deep learning based model that uses the 1D representations of targets and drugs is an effective approach for drug target binding affinity prediction. The model in which high-level representations of a drug and a target are constructed via CNNs achieved the best Concordance Index (CI) performance in one of our larger benchmark datasets, outperforming the KronRLS algorithm and SimBoost, a state-of-the-art method for DT binding affinity prediction.https://github.com/hkmztrk/DeepDTASupplementary data are available at Bioinformatics online.}",
    issn = {1367-4803},
    doi = {10.1093/bioinformatics/bty593},
    url = {https://doi.org/10.1093/bioinformatics/bty593},
    eprint = {https://academic.oup.com/bioinformatics/article-pdf/34/17/i821/25702584/bty593.pdf},
}
