.. dms2dfe documentation master file, created by
   sphinx-quickstart on Mon Apr  4 12:56:49 2016.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.
.. _dms2dfe:

Overview
--------

dms2dfe (**D**\ eep **M**\ utational **S**\ canning (DMS) data to **D**\ istribution of **F**\ itness **E**\ ffects (DFE)) is an integrative analysis workflow designed for end-to-end enrichment analysis of Deep Mutational Scaning [1] data. Among many experimental designs Deep Mutational Scaning asssay, this workflow, currently, is only applicable for pairwise comparisons of samples.
`dms2dfe` makes use of efficient libraries such as `pandas` [2]_ to handle data tables `pysam` [3]_ to handle sequence alignment files and `scikit-learn` [4]_ to generate regression and classification models.

.. image:: _static/overview.png
   :height: 500px
   :align: center

Basic usage
-----------

:ref:`Installation`

To install the package, simply execute following command:

.. code-block:: text

    pip install dms2dfe

Note: python 2.7 and linux (tested on debian) are required.

:ref:`Usage`

From bash command line, create a project directory

.. code-block:: text

    dms2dfe project_directory

Insert input parameters in the configuration files (.csv) located in `project_directory/cfg`   

Run the analysis,

.. code-block:: text

    dms2dfe project_directory

Publication
-----------

**dms2dfe: Comprehensive Workflow for Analysis of Deep Mutational Scanning Data**  

Rohan Dandage, Kausik Chakraborty  

doi: http://dx.doi.org/10.1101/072645  

Questions
---------

Please mention them here: https://github.com/rraadd88/dms2dfe/issues .

Citations
---------

.. [1] Fowler, D.M., and S. Fields. 2014. Deep mutational scanning: a new style of protein science. Nature methods. 11: 801–7.

.. [2] McKinney, W. & Team, P. D. Pandas - Powerful Python Data Analysis Toolkit. Pandas - Powerful Python Data Anal. Toolkit 1625 (2015).

.. [3] Heger, A. Pysam. github.com (2009). at <https://github.com/pysam-developers/pysam>

.. [4] Pedregosa, F. et al. Scikit-learn: Machine Learning in Python. … Mach. Learn. … 12, 2825–2830 (2012).


Pages
---------

.. toctree:: 
    :maxdepth: 1
    
    1installation
    2usage
    3programs
    4io
    6test
    5api
    1installation_deps
    7troubleshoot
    6test_applications
    8future

Indices and tables
==================

* :ref:`genindex`
* :ref:`search`