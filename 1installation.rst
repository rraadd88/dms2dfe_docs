.. _installation:

==========================================
Installation
==========================================

Before install (Recommended)
----------------------------

`dms2dfe` requires python 2.7 environment and a linux system (tested on debian).
`Anaconda Python Distribution`_ is recommended for installing required python packages. 
In order to avoid common issues with installation, a conda environment can be created.

.. code-block:: text
    
    wget https://raw.githubusercontent.com/rraadd88/dms2dfe/master/environment.yml
    conda env create -f environment.yml

Activate the python environment by following command,

.. code-block:: text

    source activate dms2dfe

.. _Anaconda Python Distribution: https://repo.continuum.io/archive/Anaconda2-4.0.0-Linux-x86_64.sh

Installation of `dms2dfe`
-------------------------

To install the package written in python 2.7, simply execute following command:

.. code-block:: text

    pip install dms2dfe

Source releases are hosted at https://github.com/kc-lab/dms2dfe/releases.
Optional dependency UCSF-Chimera can be manually installed as described in deps_ section below.

Questions
---------

Please mention them here: https://github.com/kc-lab/dms2dfe/issues .

.. _deps: 

(Optional) Manually installed dependencies 
------------------------------------------

.. code-block:: text

    Visualizations on the PDB structures (step=5)    : UCSF-Chimera (tested on 1.10.1)

Through visuazation modules of `dms2dfe`, position wise fitness scores would be written in the B-factor (temperature factor) of PDB structures. 
Users can use UCSF-Chimera to make visualizations automatically (download link `here`_). Please refer to :ref:`Troubleshoot` page for any issues.

This dependency is optional because users can use any PDB viewer of their choice to visualize the .pdb files (located in `project_directory/plots/aas`).

.. _here: https://www.cgl.ucsf.edu/chimera/cgi-bin/secure/chimera-get.py?file=linux_x86_64/chimera-1.10.1-linux_x86_64.bin

(Optional) Manually adding paths to dependencies
------------------------------------------------

Following are the external dependencies that are auto-installed during initialisation of dms2dfe.

.. code-block:: text

    Quality control .fastq files           : Trimmomatic (0.33)
    Alignining .fastq files                : Bowtie2 (2.2.1)
    Convert sam to sorted bam              : samtools (0.1.18)
    Feature extraction from PDB structure  : DSSP (2.0.4)
    Feature extraction from MSA            : Clustalo (1.2.2)
    Feature extraction: residue depth      : MSMS (2.6.1)
    Feature extraction: conservation scores: Rate4site (3.0.0)
    
With default configuration, these dependencies would be locally configured and their paths would be appended to `"project_directory"/cfg/info` file.

In case dependencies are already installed on the system, custom paths to the sources can be appended manually in the `"project_directory"/cfg/info` file.


Troubleshoot
------------

Please refer to :ref:`Troubleshoot` page.
