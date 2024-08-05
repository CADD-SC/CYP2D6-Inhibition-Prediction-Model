# CYP2D6-Inhibition-Prediction-Model
Machine learning-based prediction model for CYP2D6 inhibition prediction

## Introduction ## 

Welcome to our repository, here we provide machine learning model to efficiently predict the CYP2D6 inhibition of target drug compounds in early stage of drug discovery process. CYP2D6 is a highly polymorphic enzyme within the Cytochrome P450 family, involved in the metabolism of approximately 25% of all clinically used drugs. These include antidepressants, antipsychotics, beta-blockers, and opioid analgesics. Inhibition of CYP2D6 can lead to significant changes in drug metabolism, resulting in either reduced efficacy or increased toxicity. 

## Classification criteria ##

**The model uses an IC<sub>50</sub> threshold:**

The model classifies a compound based on its predicted <em>IC<sub>50</sub></em> value. If the <em>IC<sub>50</sub></em> value is less than 10μM, the compound is classified as class 1; otherwise, it is classified as class 0. 

Additionally, the model provides the probability that each compound belongs to its respective class. If classified as class 1, the compound is considered an inhibitor, along with the associated probability.

## Dependencies ##

- Python ≥ 3.9
- scikit-learn ≥ 1.26.4
- numpy == 11.5.0
- hpsklearn == 1.0.3
- hyperopt == 0.2.7
- xgboost == 2.0.3
- rdkit
- pandas

## Execution ##
**To run the prediction:**

```
$ python model.py --prediction --file_name [filename] 
```
<strong>Note:</strong> For the prediction step, prepare a .csv file containing SMILES without bioclass (e.g., test_set.csv)

**To run the validation:**

```
$ python model.py --validation --file_name [filename] 
```
<strong>Note:</strong> For the validation step, prepare a .csv file containing SMILES with bioclass (0 or 1) (e.g., valid_set.csv)

**Output:**

Our model generates output in binary value (1 or 0), where 1 indicates compound to be inhibitor, while 0 indicates non-inhibitor.

Additionally, the model provides the probability that each compound belongs to its respective class. If classified as class 1, the compound is considered an inhibitor, along with the associated probability.
 
**Please ensure that all the necessary files (CYP2D6.pkl, data_preprocessing.py, scaler, features.txt, input_file.csv, model.py) are kept in the working directory**

**<ins>To download the prediction model file (CYP2D6.pkl), please refer to the "Tags --> v2.3.4" tab</ins>**
