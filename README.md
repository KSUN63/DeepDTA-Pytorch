# DeepDTA-Pytorch
Pytorch Implementation of the original DeepDTA paper. [Original GitHub Repo](https://github.com/hkmztrk/DeepDTA/)

Requirements (most of them come with Anaconda except torch, pytorch-cuda, and tqdm)
```
python==3.8.16  
numpy==1.24.1  
pandas==1.5.2  
matplotlib==3.5.3  
scipy==1.8.1  
torch==2.1.0  
pytorch-cuda==11.7  
tqdm==4.65.0  
```

The data format should be in the form of a csv file with four columns: proteins, ligands, affinity, split, where proteins store all the sequence information, ligands store the isomeric smile strings of the molecular binders, and affinity was either the Kd/Ki value or the bidning affinity in kcal/mol (this needs to be consistent for all data). The final split column will have three possible values that indicate the train-val-test splitting: 'train', 'val', and 'test'. See an example in `examples/cleaned_mpro.csv`

To run the code, go to deepdta_retrain.py to do the appropriate modification of fp and then run python deepdta_retrain.py

For analysis, there's a separate jupyter notebook files for some preliminary scatter plots and using the trained model to analyze a held-out set of data. Make sure to change the name of ligand_dict and protein_dict and the model you want to use to your choices. This part of analysis is mainly for choosing the best hyperparameters of protein and ligand kernel size. In the first fp you can use `examples/cleaned_mpro.csv`. Then, in the held out data csv, you can use `examples/bindingDB_processed.csv`.

Also, feel free to check out our paper that tests this implementation on a better PDBBind Splitting here. [![arXiv](https://img.shields.io/badge/arXiv-2308.09639v2-B31B1B)](https://arxiv.org/abs/2308.09639v2)

## Citation
```bibtex
@article{lppdbbind,
	title = {Leak {Proof} {PDBBind}: {A} {Reorganized} {Dataset} of {Protein}-{Ligand} {Complexes} for {More} {Generalizable} {Binding} {Affinity} {Prediction}},
	journal = {ArXiv},
	author = {Li, Jie and Guan, Xingyi and Zhang, Oufan and Sun, Kunyang and Wang, Yingze and Bagni, Dorian and Head-Gordon, Teresa},
	month = may,
	year = {2024},
	pmid = {37645037},
	pmcid = {PMC10462179},
	pages = {arXiv:2308.09639v2},
}

@article{10.1093/bioinformatics/bty593,  
    author = {Öztürk, Hakime and Özgür, Arzucan and Ozkirimli, Elif},  
    title = "{DeepDTA: deep drug–target binding affinity prediction}",  
    journal = {Bioinformatics},  
    volume = {34},  
    number = {17},  
    pages = {i821-i829},  
    year = {2018},  
    month = {09},  
    issn = {1367-4803},  
    doi = {10.1093/bioinformatics/bty593},  
    url = {https://doi.org/10.1093/bioinformatics/bty593},  
    eprint = {https://academic.oup.com/bioinformatics/article-pdf/34/17/i821/25702584/bty593.pdf},  
}
```
