# DBLFold (Deep Boosting Folding)

## Related paper:
Tzu-Hsien Yang* and Li-Chang Teng, "Computational identification of RNA secondary structures using deep boosting learning". (Submitting)

## Prepare the Environment

Suggested running environments: Linux Ubuntu 16.04.6, Python 3.8.13

We recommend that you can use the conda package to create a new environment. This will automatically install the required python packages. 

Here is an example: 

1. Install the Conda package for you system. The installation of the package can be found <a href="https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html">here</a>. 

2. Create the DBLFold Conda environment. This may take a while, depending on the network status.

```
conda create -n "DBLFold" python=3.8.13
```

3. Activate your DBLFold Conda environment. 

```
conda activate DBLFold
```

## Steps to Use DBLFold

1. Download the codes from the following link and unzip the file. Please skip it if you have done this step.

```
wget https://cobis-fs.bme.ncku.edu.tw/DBLFold/DBLFold.tar.gz
```

2. Unzip the file.

```
tar -zxvf DBLFold.tar.gz
```

3. Change the working directory.

```
cd DBLFold
```

4. If this is the first time you use DBLFold, run the following command to install necessary packages. 

```
pip install -r requirements.txt
```

DBLFold can also support GPU acceleration. If you want to utilize GPU, please run the following command instead:

```
conda install pytorch torchvision torchaudio cudatoolkit=<version> -c pytorch
```

Remember to specify the current version of your cuda GPU support.


5. Prepare the input sequence in the <a href="https://www.ncbi.nlm.nih.gov/genbank/fastaformat/">fasta</a> format. Then put these fasta files in one input folder.

6. Run DBLFold to predict the potential RNA secondary structure of the given sequence.

```
python DBLFold_predict.py -i <input_fasta_file_folder> -o <output_directory>
```

The outputs are provided in the <a href="http://rna.urmc.rochester.edu/Text/File_Formats.html#CT">ct</a> format. 

>**Required arguments:**
>
>* -i: The input folder name of the fasta files.
>
>* -o: The output directory of the predicted results.
