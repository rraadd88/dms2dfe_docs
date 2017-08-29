.. _installation:

==========================================
Installation
==========================================

Requirements
------------

Required python packages would be auto installed while installing `dms2dfe`. `Anaconda Python Distribution`_ is recommended for installing dependent python packages.

.. _Anaconda Python Distribution: https://repo.continuum.io/archive/Anaconda2-4.0.0-Linux-x86_64.sh

Especially we recommend installing `gcc` and `pysam` prior installing `dms2dfe`.

.. code-block:: text

    conda install -c anaconda gcc
    conda install -c bioconda pysam==0.8.4

Except for DESeq2 and UCSF-Chimera (optional), all other dependencies are auto-installed. 
Please refer to :ref:`dependencies` for more information.

Installation of `dms2dfe`
-------------------------

Download the latest release from https://github.com/kc-lab/dms2dfe/releases .

.. code-block:: text

    cd dms2dfe
    pip install .

Troubleshoot
------------

Please refer to :ref:`Troubleshoot` page.

Questions
---------

Please mention them here: https://github.com/kc-lab/dms2dfe/issues .

Manually installed dependencies
-------------------------------

.. code-block:: text

    Differential analysis of counts             : DESeq2 (tested on 1.6.3 R version 3.2.2 )
    Visualizations on the 3D structures         : UCSF-Chimera (tested on 1.10.1)

DESeq2 installation (from within R)

.. code-block:: text

    source("https://bioconductor.org/biocLite.R")
    biocLite("DESeq2")

UCSF-Chimera can be downloaded from `here`_.
    
.. _here: https://www.cgl.ucsf.edu/chimera/cgi-bin/secure/chimera-get.py?file=linux_x86_64/chimera-1.10.1-linux_x86_64.bin

Additionally, to use `UCSF-Chimera` through python environment, graphics drivers also need to be configured by installing "mesa-utils" (apt-get install mesa-utils).

Auto-installed dependencies
---------------------------

Functions of external dependencies and the requirement,

.. code-block:: text

    Feature extraction from PDB structure       : DSSP (2.0.4)
    Quality control .fastq files                : Trimmomatic (0.33)
    Alignining .fastq files                     : Bowtie2 (2.2.1)
    Convert sam to sorted bam                   : samtools (0.1.18)

Dependencies would be auto configured by `dms2dfe.configure` module while envoking `dms2dfe.pipeline`. 
In exceptional cases they can configured by following command,

.. code-block:: text
    
    from dms2dfe import configure
    configure.main("path/to/project_directory","deps")

Source files of the tools would be downloaded in `current_directory/dms2dfe_dependencies` folder, paths of which to the source files of all the tools would be appended to the `"project_directory"/cfg/info`.

These paths can be manually appended to default configuration of a `project` by following command,

.. code-block:: text
    
    from dms2dfe import configure
    configure.main("inputs")

Also these paths can be manually, permenently appended to default configuration of `dms2dfe` by following command,

.. code-block:: text
    
    from dms2dfe import configure
    configure.main("defaults")

Troubleshoot
------------

Please refer to :ref:`Troubleshoot` page.
