.. OMG of SRS documentation master file, created by
   sphinx-quickstart on Sat Apr 28 08:53:54 2018.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to OMG of SRS's documentation!
======================================

.. toctree::
   :maxdepth: 2
   :caption: Contents:



Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

1.Introduction
============
     This document describes the Little Hill Lab's initial requirements for an onlineapplication (Oh My Genes) which allows our   scientists to upload gene expression filesand quickly get differentially expressed genes.

* :ref:`(1.1)Purpose`
         To identify differentially expressed genes given a gene expression file containingtwo cell samples.
* :ref:`(1.2)Additional information`
         Genes (genetic factors) are DNA fragments with genetic effects (some viruses such as tobacco mosaic virus and HIV's genetic material are RNA). Genes support the basic structure and performance of life. All the information stored in the process of race, blood type, inoculation, growth, apoptosis and so on. Environmental and genetic interdependence is an important physiological process of reproduction, cell division and protein synthesis. All life phenomena such as birth, growth, decay, disease, old age and death are related to genes. It is also an intrinsic factor in determining the health of life. Therefore, genes have dual attributes: materiality (existence mode) and Information Nature (fundamental attribute).
         DNA fragments with genetic information are called genes, and other DNA sequences, some play a role directly in their own structures, and some are involved in regulating the performance of genetic information. At least 265 to 350 genes are needed to make a simple life. (this involves the power of the gene working group. The human genome working group is basically similar to that of Drosophila).

* :ref:`(1.3)Intended audience`
            Medical staff
            
2.Overall Description
=====================
* :ref:`(2.1)Product`
            A web application preferably using the Flask framework (http://flask.pocoo.org/)
* :ref:`(2.2)Domain knowledge`
            Control sample - a cell sample prepared in its normal condition.Treatment sample - a cell sample treated by special chemicals, or in which some genesare altered.Differentially expressed genes - the genes which have significantly differentexpression levels between two samples.Up-regulation - a gene is said to be up-regulated if it has higher expression intreatment than in control.logFC - log fold change of gene expression. log_2 [T/C], where T is the geneexpression level from a treatment sample, while C is the gene expression level from acontrol sample.

3.Functionality
===============
* :ref:`(3.1)Overview`
        The web application has a simple interface with a single button [Upload and GO]. Ourscientists upload a plain text file containing gene expression levels from twosamples, representing two experimental conditions. Accepting the file, the softwarewill return a table of differentially expressed genes and a scatter plot of thesegenes whose X-axis is control and Y-axis is treatment. If an invalid gene expressionis given, the web application returns a page informing the user to provide thecorrect format
 * :ref:`(3.2)Input`
          A valid submitted gene expression file has the following format. It is a TAB-delimited, plain text file with three columns (see the attached file for a full example). The file contains an optional head line, followed by each gene'sexpression in a control sample (e.g., ControlSample) and in a treatment sample (e.g.,KnockOutSample)
          
          
          gene_id ControlSample KnockOutSample
          AT1G01010 1.198558083 2.036161827
          AT1G01020 13.75736234 13.370796
          AT1G01030 0.833779536 0.203616183
          AT1G01040 9.58846466 7.126566394
          AT1G01046 0 0
          AT1G01050 23.81482799 21.10821094
          AT1G01060 0.625334652 1.221697096
          AT1G01070 1.719670292 0.950208853
          AT1G01080 28.34850421 25.24840665
          AT1G01090 58.26034505 42.96301455
          AT1G01100 1066.508249 1308.030358
          AT1G01110 2.709783491 1.425313279
 * :ref:`(3.3)Output`
          The web application displays a table and a scatter plot given a gene expression file.The table contains a list of differentially expressed genes with the followingformat:gene_id control_sample treat_sample log_2[FC]AT1G01010 1.198558083 2.036161827 0.76The scatter plot displays differentially expressed genes. The X-axis is Control, andY-axis is Treatment.Replace 'Control' and 'Treatment' with appropriated column names if provided in theuploaded file. The up-regulated genes are shown in red dots, and down-regulatedgenes are shown in blue
