# Rohan_Kapoor_9599023170-IITB-Assignment-Jul-Dec2020-Batch2

## Handwritten Form Reader Web App

### 1. Create new environment
If using anaconda then create new environment using this in the conda prompt else you can use the navigator as well
```
conda create -n envname python=3.7
```
If not using anaconda then see this link
https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/

Note: Python version is 3.7

### 2. Install the required packages 
All the required packages are mentioned in the requirements.txt files.
Note: Anaconda does not have few packages like opencv so install them using the python package manager (pip)
```
pip install -r requirements.txt
```

### 3. Generating the dataset
Option 1 - Use the provided dataset in the tfrecords format

Option 2 - https://github.com/Belval/TextRecognitionDataGenerator/tree/master
Go to this link and download the repository or you can also clone the repository using 
```
git clone https://github.com/Belval/TextRecognitionDataGenerator.git
```
or you can simply do
```
pip install trdg
```

After this simply run the run.py file in the trdg folder in anaconda prompt or an ide
```
python ./run.py -c 1000
```
This will generate 1000 images
You can see help for various options present and go to the official documentation https://textrecognitiondatagenerator.readthedocs.io/en/latest/index.html for more details

