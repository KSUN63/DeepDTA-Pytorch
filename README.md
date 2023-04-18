# DeepDTA-Pytorch
Pytorch Implementation of the original DeepDTA paper (https://github.com/hkmztrk/DeepDTA/)

The data format should be in the form of a csv file with four columns: proteins, ligands, affinity, split, where proteins store all the sequence information, ligands store the isomeric smile strings of the molecular binders, and affinity was either the Kd/Ki value or the bidning affinity in kcal/mol (this needs to be consistent for all data). The final split column will have three possible values that indicate the train-val-test splitting: 'train', 'val', and 'test'.

To run the code, go to deepdta_retrain.py to do the appropriate modification of fp and then run python deepdta_retrain.py

For analysis, there's a separate jupyter notebook files for some preliminary scatter plots and using the trained model to analyze a held-out set of data. Make sure to change the name of ligand_dict and protein_dict and the model you want to use to your choices.
