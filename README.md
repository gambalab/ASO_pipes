# ASO-based Pipeline for Rare Disorders
## Description
This pipeline is designed to facilitate the development of Antisense Oligonucleotides (ASOs) for targeting RNA in a highly specific manner. ASOs are short oligonucleotides chemically modified that can bind to RNA in a target-specific manner to modifying protein expression. This results in the modulation, reduction, or restoration of specific proteins involved in genetic disorders.
This repository serves as a robust framework for researchers working on gene therapy and RNA-targeted treatments for rare diseases. It can be adapted for use in preclinical studies, helping to accelerate the development of precision therapies that address the genetic underpinnings of over 8000 rare disorders.
# Installation
To use this pipeline, you need to have Python 3.9 installed on your system. You can download and install it from the official website https://www.python.org . Once Python is installed, you can run the pipeline following the instructions provided in the documentation.
### 1. Installation of Singularity
VEP require the installation of Singularity first. Follow this link https://singularity-tutorial.github.io/01-installation/ to install it on Ubuntu. 
### 2. Installation of VEP
After installing Singularity, VEP may be used with Singularity based on the VEP Docker image from DockerHub:
``` r
singularity pull --name vep.sif docker://ensemblorg/ensembl-vep
```
You need the following plugins to correctly run the pipeline:
- AlphaMissense
- LOFTEE
- MaxEntScan
- REVEL
- SpliceAI
- SpliceVault

When you use Ensembl VEP in Docker and Singularity, VEP plugins and their dependencies are available in the Docker image. Follow this link https://www.ensembl.org/info/docs/tools/vep/script/vep_plugins.html to download the files required by the plugins and remember that these files must be located in the same directory where the plugins have been installed.
### 3. Installation of Pangolin
Pangolin is a deep-learning based method for predicting splice site strengths. It is available as a command-line tool that can be run on a VCF or CSV file containing variants of interest. 
Pangolin will predict changes in splice site strength due to each variant, and return a file of the same format. Follow this link https://github.com/tkzeng/Pangolin to install Pangolin.

### 4. Installation of BCFtools
BCFtools is a set of utilities that manipulate variant calls in the Variant Call Format (VCF) and its binary counterpart BCF. 

From the terminal exec the following commands:
``` r
git clone --recurse-submodules https://github.com/samtools/htslib.git
git clone https://github.com/samtools/bcftools.git
cd bcftools
 # The following is optional:
 #   autoheader && autoconf && ./configure --enable-libgsl --enable-perl-filters
make
```
### 5. Installation of Jupyter
To run the pipeline you need to install Jupyter, a web-based interactive computing platform. Follow this link https://jupyter.org/install to install it on Ubuntu.


After completing all the necessary installations, download the files into the "data" folder and add the required file/folder paths in the ASOS_PIPELINE.ipynb file.
