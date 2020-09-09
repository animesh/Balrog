# Setting up for Pseudomonas 

## OS: WSL Ubuntu 20.04 
```
git clone https://github.com/animesh/Balrog
mkdir -p /home/animeshs/content/mmseqs2
```

# notebook 
<!-- badges: start -->
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/animesh/Balrog/blob/master/notebooks/Balrog_0.3.1.ipynb)
<!--badges: end -->
```
replace /content -> /home/animeshs/content
```

[colab local setup](https://research.google.com/colaboratory/local-runtimes.html)
```
pip install jupyter_http_over_ws
jupyter serverextension enable --py jupyter_http_over_ws
jupyter notebook --NotebookApp.allow_origin='https://colab.research.google.com' --port=8888 --NotebookApp.port_retries=0
```

## Check in CMD with [mmseqs](https://mmseqs.com/)
[Download](https://mmseqs.com/latest/mmseqs-win64.zip)
[Manual](https://mmseqs.com/latest/userguide.pdf)

```
cd L:\promec\Animesh\mmseqs-win64\mmseqs>
mmseqs.bat easy-search z:\Pseudomonas\Aas-gDNA1-W2-PaE_S8_L001_R.contigs.fasta  z:\Pseudomonas\Aas-gDNA1-W2-PaE_S8_L001_R.contigs.fasta alnResult tmp --search-type 3  --split-memory-limit 96G
```

# Bacterial Annotation by Learned Representation Of Genes
```

<!-- badges: start -->
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/animesh/Balrog/blob/master/notebooks/Balrog_0.3.1.ipynb)
<!--badges: end -->


## Overview
Balrog is a prokaryotic gene finder based on a Temporal Convolutional Network. We took a data-driven approach to prokaryotic gene finding, relying on the large and diverse collection of already-sequenced genomes. By training a single, universal model of bacterial genes on protein sequences from many different species, we were able to match the sensitivity of current gene finders while reducing the overall number of gene predictions. Balrog does not need to be refit on any new genome.

Paper link forthcoming...

![Balrog](images/balrog.jpg)

## Getting started
Click the "Open in Colab" button above or [click here](https://colab.research.google.com/github/salzberg-lab/Balrog/blob/master/notebooks/Balrog_0.3.1.ipynb) to get started. 

Press the play button on the left side of each cell to run it. Alternatively, hold shift or ctrl and press enter to run cells.
Double click the top of a cell to inspect the code inside and change things. Double click the right side of the cell to hide the code.
Have fun!

Because Balrog uses a complex gene model and performs alignment-based search with mmseqs2, each genome takes ~10-15 minutes to process. Feel free to open a GitHub issue if you run into problems or would like a command line version of Balrog.