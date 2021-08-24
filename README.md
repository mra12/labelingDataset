# labeling Dataset
A dataset of labels extracted from VirusTotal reports of **2.47 million Android apk hashes**.

## Information
The csv of the labels that was extracted from the VirusTotal reports is provided in `labeling_dataset.csv.gz` . A cell's value of `-1` is used whenever there was no result from the 
engine for the given apk file hash value. The column names are provided in `cols_labeling_dataset.csv`. 
###### Note 
`-1` is a `string` and not an `integer`
## If you use information from this repo, please cite our paper
Rashed M, Suarez-Tangil G. An Analysis of Android Malware Classification Services. Sensors. 2021; 21(16):5671. https://doi.org/10.3390/s21165671

## BibTeX
@Article{s21165671,\
AUTHOR = {Rashed, Mohammed and Suarez-Tangil, Guillermo},\
TITLE = {An Analysis of Android Malware Classification Services},\
JOURNAL = {Sensors},\
VOLUME = {21},\
YEAR = {2021},\
NUMBER = {16},\
ARTICLE-NUMBER = {5671},\
URL = {https://www.mdpi.com/1424-8220/21/16/5671},\
ISSN = {1424-8220},\
DOI = {10.3390/s21165671}\
}

## Required Software
`gzip`
- Debian-based Linux: you may install it using the following command `apt-get install gzip`
- MacOS: `gzip` is pre-installed
- Windows: you may download `gzip` from http://gnuwin32.sourceforge.net/packages/gzip.htm 

## How to use the file?
There are two ways to use the file:
1. Extract the gzip file and then you will have a csv output file. For that you need to install gzip and then extracting .csv.gz. The user may use the command `gunzip labelingDataset.csv.gz`
2. Extract information from the zipped file directly (following the same logic of [AndroZoo's csv](https://androzoo.uni.lu/lists)):
   To extract the first column and save to a file called `list_of_selected_sha256`, run the following command:\ `zcat labelingDataset.csv.gz | cut -d',' -f1 > list_of_selected_sha256`  
   To obtain rows of apk hashes that were first seen after the 1st of May, 2016, run this command:\ `zcat labeling_dataset.csv.gz | grep -v ',snaggamea' | awk -F, '{if ( $2 >= "2016-05" ) {print} }'`
   


