.. _example:

==========================================
Example Datasets
==========================================

Following are few examples of execution and outputs from analysis of datasets.

1. Olson_et_al_2014_ (GB1)
This dataset contains frequencies of single site mutants obtained by DMS of GB1 protein based of their binding affinity to the partner.

2. Firnberg_et_al_2014_ (TEM1).
This dataset contains frequencies of single site codon level mutants obtained by DMS of E. coli TEM-1 beta-lactamase in Ampicilin at 256 ug/ml (Amp256) and (Amp0.5). 

3. Melnikov_et_al_2014_ (APH2)
This dataset contains frequencies of single site mutants obtained by DMS of E. coli aminoglycoside-3 -phosphotransferase-II (APH(3')II) mutants selected for resistance against Kanamicin at 1:4 MIC of wild type (sample KKA2_S1_Kan14_L1) and at 1:1 MIC of wild type (sample KKA2_S1_Kan11_L1). 


Download and analyze datasets
=============================

Exaple datasets are hosted at https://github.com/rraadd88/ms_datasets . 
In the downloaded folder `ms_dataset`, directory `analysis` is to be used to analyze different datasets as follows. 

.. code-block:: text

    git clone https://github.com/rraadd88/ms_datasets.git
	cd ms_dataset/analysis
	dms2dfe <project directory>

Here, '<project directory>' can be `Firnberg_et_al_2014`, `Melnikov_et_al_2014` or `Olson_et_al_2014`

Note: dataset `Melnikov_et_al_2014` would need sequencing data to be dowloaded from SRA. A script named `get_seq_data.py` (located at `ms_datasets/analysis`) would download the `fastq` files (~300Mb) in `Melnikov_et_al_2014/data_input` folder. 

.. code-block:: text

    get_seq_data.py Melnikov_et_al_2014

Outputs
=======

The outputs of the run can be vaidated with those kept in 'ms_datasets/outputs'.

Overall testing
================

Following set of commands would enable overall testing of the package.

.. code-block:: text

    # create conda environment
    wget https://raw.githubusercontent.com/rraadd88/dms2dfe/master/environment.yml
    conda env create -f environment.yml
    source activate dms2dfe

    # install the package
    pip install dms2dfe

    # download the datasets
    wget https://github.com/rraadd88/ms_datasets/archive/v0.0.4.zip
    unzip v0.0.4.zip

    # analyze the datasets
    cd ms_datasets-0.0.4/analysis
    dms2dfe Olson_et_al_2014
    dms2dfe Firnberg_et_al_2014
    # download input sequencing data (~300Mb)
    python get_seq_data.py Melnikov_et_al_2014
    dms2dfe Melnikov_et_al_2014

    # testing optional (time taking) step 3
    dms2dfe Olson_et_al_2014 --step 3
    dms2dfe Firnberg_et_al_2014 --step 3
    dms2dfe Melnikov_et_al_2014 --step 3

Citations
---------

.. [Firnberg_et_al_2014] Firnberg, E., J.W. Labonte, J.J. Gray, and M. Ostermeier. 2014. A comprehensive, high-resolution map of a Gene’s fitness landscape. Molecular Biology and Evolution. 31: 1581–1592.

.. [Olson_et_al_2014] Olson, C. Anders, Nicholas C. Wu, and Ren Sun. 2014. “A Comprehensive Biophysical Description of Pairwise Epistasis throughout an Entire Protein Domain.” Current Biology 24 (22): 2643–2651. doi:10.1016/j.cub.2014.09.072. http://dx.doi.org/10.1016/j.cub.2014.09.072.

.. [Melnikov_et_al_2014] Melnikov, A., P. Rogov, L. Wang, A. Gnirke, and T.S. Mikkelsen. 2014. Comprehensive mutational scanning of a kinase in vivo reveals substrate-dependent fitness landscapes. Nucleic Acids Research. 42: 1–8.