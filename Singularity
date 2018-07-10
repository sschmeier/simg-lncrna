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
   conda install --yes star=2.6.0c
   conda install --yes samtools=1.8
   conda install --yes stringtie=1.3.4
   conda install --yes gffcompare=0.10.1
   conda install --yes gffread=0.9.9
   conda install --yes bioawk=1.0
   conda install --yes ucsc-gtftogenepred=357
   conda install --yes circexplorer2=2.3.2
   conda install --yes bedtools=2.27.1
   conda clean --index-cache --tarballs --packages --yes