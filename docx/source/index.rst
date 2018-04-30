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
        * :ref:` AT1G01010 1.198558083 2.036161827`  
        * :ref:`AT1G01020 13.75736234 13.370796`    
        * :ref:`AT1G01030 0.833779536 0.203616183`    
        * :ref:`AT1G01040 9.58846466 7.126566394`  
        * :ref:`AT1G01046 0 0`   AT1G01046 0 0
        * :ref:``   AT1G01050 23.81482799 21.10821094
        * :ref:` AT1G01050 23.81482799 21.10821094`  
        * :ref:`AT1G01070 1.719670292 0.950208853` 
        * :ref:`AT1G01080 28.34850421 25.24840665`  
        * :ref:`AT1G01090 58.26034505 42.96301455`  
        * :ref:`AT1G01100 1066.508249 1308.030358`  
        * :ref:`AT1G01110 2.709783491 1.425313279`  
  
  
  
* :ref:`(3.3)Output`
          The web application displays a table and a scatter plot given a gene expression file.The table contains a list of differentially expressed genes with the followingformat:gene_id control_sample treat_sample log_2[FC]AT1G01010 1.198558083 2.036161827 0.76The scatter plot displays differentially expressed genes. The X-axis is Control, andY-axis is Treatment.Replace 'Control' and 'Treatment' with appropriated column names if provided in theuploaded file. The up-regulated genes are shown in red dots, and down-regulatedgenes are shown in blue
  
  
4.oh my genes system
======================
 * :ref:`(4.1)the system's front page`
           oh my genes software team, the first Linux server oriented web page visualization analysis system, the leading B/S architecture, specifically for bacterial genome sequencing data analysis. Help you do one-stop, data quality control, sequence assembly, gene prediction, gene annotation.

           (1）The system is mature, stable and friendly based on Galaxy open source framework.
          （2）Zero base, no command line, and programming skills
          （3）Integrated sample management and data management functions
          （4）The analysis modules are derived from the widely accepted algorithms and open source programs in the published literature.
 * :ref:`(4.2)Analysis function list` 
             Original data quality control： The analysis module creates a PE library directory under the selected sample directory, imports the original PE sequencing data in the History Panel, and uses Trimmomatic PE to cut and filter. Thus, the optimized sequence of the sample is obtained. Note that the name of the library is composed of numbers, letters and underlines, and the beginning and the end cannot be underlined. If the library catalog already exists, it cannot be created, and indicates that the Library Directory has an error.
             
             
             Raw data statistics：The analysis module, according to the selected samples, carries on the data statistics to the imported sequencing sequence.
The analysis module refers to FASTX-Toolkit v0.0.13 software (http://hannonlab.cshl.edu/fastx_toolkit/index.html).


             The web application： has a simple interface with a single button [Upload and GO]. Ourscientists upload a plain text file containing gene expression levels from twosamples, representing two experimental conditions. Accepting the file, the softwarewill return a table of differentially expressed genes and a scatter plot of thesegenes whose X-axis is control and Y-axis is treatment. If an invalid gene expressionis given, the web application returns a page informing the user to provide thecorrect format
  
 5.use case
==========
* :ref:`(5.1)use case`
         RNA-seq technology is rapidly innovated in genomics research, and the statistical methods of RNA-seq data are developing. Timely review and comparison of recent statistical methods can provide a useful guide for selecting suitable methods for data analysis. People have a liking for the ability to detect differentially expressed genes. Here we compare four recent statistical methods, edgeR, DESeq, baySeq, and a two step Poisson model (TSPM) method based on a series of simulation based on different distribution models or real data. We compared the ability of these methods to detect differentially expressed genes according to the significance of sorting genes and false positive rates. All comparison methods are implemented with freely available software. We also discussed the usability and functionality of these software versions currently available. "
         
         Comparison of 1, RNA-seq and microarray
"Compared to the hybrid microarray technology, RNA-seq has a number of advantages, including a larger level of expression, more information to detect allelic specific expression, new promoter, new subtype, lower noise, and higher flux. Therefore, RNA-seq is preparing to replace microarray technology in the next few years to become a major platform for gene expression research.
2, RNA-seq experiment and analysis technology summary
"In a typical RNA-seq experiment, a RNA sample is converted into a cDNA fragment library, and then sequenced on a high - throughput commercial platform, such as the Genome Analyzer of the Illumina, the HeliScope of the Helicos BioSciences, the SOLiD of Applied Biosystems, and the Sequencing system. Raw data consist of a large number of DNA fragment sequences (called reads), which need to undergo a series of analysis steps. Oshlack et al. (2010) provides an excellent review of the analysis process, which includes mapping reads, summarizing the reads counts of each gene, normalization and detection of differentially expressed genes. Table 1 provides a list of software for each step analysis. In general, the reads produced by RNA-seq studies should be assigned to genes or other taxa based on mapping to the target genome or de novo assembly transcriptome. Some quantitative methods for gene expression level of RNA-seq data are still being studied. The complexity of variable shear transcripts and subtypes makes it an active research area. Because subtype detection is not the focus of this article, interested readers can refer to references of Hiller (2009) and Salzman (2011) and their estimation of subtype abundance in RNA-seq data. "Gene" is a generalized term that we use throughout the rest of this article. It can refer to a single exon or exon of a gene model or all exons. Gene expression is measured by mapping the number of reads to a gene. Therefore, RNA-seq produces a discrete measure of gene expression, which is different from the fluorescence intensity measure which can be regarded as continuous variable in microarray technology. Therefore, the statistical methods used to analyze microarray data can not be applied directly, and it is urgent to develop a suitable statistical method to deal with massive RNA-seq data. "
