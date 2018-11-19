Bootstrap: docker
From: continuumio/miniconda3:4.5.4

%labels
   AUTHOR schmeier@tuta.io

%environment
# ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
# This sets global environment variables for anything run within the container
  export PATH="/opt/conda/bin:/usr/local/bin:/usr/bin:/bin:"
  unset CONDA_DEFAULT_ENV
  export ANACONDA_HOME=/opt/conda


%post
   export PATH=/opt/conda/bin:$PATH
   echo "We add conda channels."
   conda config --add channels defaults
   conda config --add channels conda-forge
   conda config --add channels bioconda
   echo "We install tools."
   conda install --yes salmon=0.11.3 star=2.6.1b samtools=1.9 stringtie=1.3.4 gffcompare=0.10.1 gffread=0.9.9  bioawk=1.0  ucsc-gtftogenepred=366 circexplorer2=2.3.3 bedtools=2.27.1 pandas=0.23.3  colorama=0.3.9 rseqc=2.6.4 cpat=1.2.3  r-readr=1.1.1  r-samr=2.0  bioconductor-tximport=1.6.0  bioconductor-deseq2=1.18.1 bioconductor-limma=3.34.9 bioconductor-edger=3.20.7 bioconductor-ihw=1.6.0  multiqc=1.6a0 
   conda clean --index-cache --tarballs --packages --yes