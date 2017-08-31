.. _installation:

==========================================
Installation
==========================================

Before install
--------------

`dms2dfe` requires python 2.7 environment and a linux system (tested on debian).
`Anaconda Python Distribution`_ is recommended for installing required python packages. 
In order to avoid common issues with installation, a conda environment can be created using this file_.

.. code-block:: text

    conda env create -f /path/to/environment.yml

Activate the python environment by following command,

.. code-block:: text

    source activate dms2dfe


.. _Anaconda Python Distribution: https://repo.continuum.io/archive/Anaconda2-4.0.0-Linux-x86_64.sh

.. _file: https://raw.githubusercontent.com/rraadd88/dms2dfe/master/environment.yml

Installation of `dms2dfe`
-------------------------

.. code-block:: text

    pip install dms2dfe

Source releases are hosted at https://github.com/kc-lab/dms2dfe/releases.
Optional dependency UCSF-Chimera can be manually installed as described in deps_ section below.

Questions
---------

Please mention them here: https://github.com/kc-lab/dms2dfe/issues .

.. _deps: (Optional) Manually installed dependencies 
----------------------------------------------------

.. code-block:: text

    Visualizations on the 3D structures (step=5)    : UCSF-Chimera (tested on 1.10.1)

UCSF-Chimera can be downloaded from `here`_.
    
.. _here: https://www.cgl.ucsf.edu/chimera/cgi-bin/secure/chimera-get.py?file=linux_x86_64/chimera-1.10.1-linux_x86_64.bin

Additionally, to use `UCSF-Chimera` through python environment, graphics drivers also need to be configured by installing "mesa-utils" (apt-get install mesa-utils).

(Optional) Manually adding paths to dependencies
------------------------------------------------

Source files of the tools would be located in `current_directory/dms2dfe_dependencies` folder, paths of which to the source files of all the tools would be appended to the `"project_directory"/cfg/info`.

In case dependencies are already installed on the system, custom paths can be appended to the configuration by following command,

.. code-block:: text
    
    from dms2dfe import configure
    configure.main("inputs")

Also these paths can be permenently set to default by following command,

.. code-block:: text
    
    from dms2dfe import configure
    configure.main("defaults")

Following dependencies are auto-installed during initialisation of dms2dfe.
Functions of external dependencies,

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

Troubleshoot
------------

Please refer to :ref:`Troubleshoot` page.
