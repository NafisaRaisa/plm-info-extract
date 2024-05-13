Instructions to run the whole pipeline:

1. Creating a virtual environment: -To use this tool, we first have to run the following command: python -m venv .env source .env/bin/activate

2. Cloning the biobert-pytorch -we run the following command to clone the biobert-pytorch repository git clone https://github.com/dmis-lab/biobert-py

3. Installation: -we have to run the following commands to install some packages or models

Install transformers : pip install transformers==3.0.0

Install the nltk, which will tokenize the abstract pip install nltk

Install scispacy pip install scispacy

Install pandas pip install pandas

Install Pytorch pip3 install torch torchvision torchaudio

Install scikit-learn pip install scikit-learn

Install the en_ner_craft_md; this will be used for gene_recognition pip install https://s3-us-west-2.amazonaws.com/ai2-s2-scispacy/releases/v0.5.0/en_ner_craft_md-0.5.0.tar.gz

**Note: One may have to install more packages based on their working environment. For more information about installation, check https://github.com/dmis-lab/biobert-pytorch and https://github.com/allenai/scispacy **

4. Saving the scripts: ` -We will go to the biobert-pytorch/relation-extraction directory. Then save the query_to_pubmed, phenotype_recognition.py, gene_recognition.py convert_to_biobert.py, Evaluate.sh, convert_test_results.py scripts in that directory from the All-scripts. -we will create a directory called datasets within relation-extraction where the test.tsv file will be saved. -We will also create output directory where the test_results.txt file will be saved

5. Running the scripts

First run the query_to_pubmed.py file, which will take the term we are searching for as the input value
Run the phenotype_recognition.py with three command line arguments: the first argument is the address of the directory where the PubMed files are saved, the second argument is the directory where the abstracts will be saved, and the third argument is the address to the directory where we want the resulting files to be saved
Run the gene_recognition.py script with two command line arguments: the first argument is the address to the directory where the resulting files of the phenotype_recognition.py are saved, and the second argument is the address to the directory where we want the resulting data.tsv file of this script to be saved
Run the convert_to_biobert.py; this script converts the data.tsv file into a format that is accepted by the biobert model. The resulting file will be saved in the datasets directory that we previously created
Run the evaluate.sh which will save a test_results.txt file in the output directory that has all the predictions
Run the convert_test_results.py. This script saves all the positive predictions into the positive_results.html and negative predictions into the negative_results.html file in the same directory where the data.tsv file is saved. The resulting files contain sentences with their PMID and sentence number with the gene and phenotype in a different colors.
Note: In all the scripts, one needs to change the directory address based on where they want the files to be saved.
