# iVPSV
**iVPSV**: An **i**ntuitive **V**isualisation **P**latform for **S**tructural **V**ariation data on desktops

# Brief Background

An **i**ntuitive **V**isualisation **P**latform for **S**tructural **V**ariation (**iVPSV**) is a lightweight program for working with structural variation data generated from short and long-read sequencing data (e.g. vcf, gff, gtf, bam, and fasta). This program is to provide a graphical environment for biologists using NGS data who are less experienced in command lines. As a lightweight (but powerful) desktop/laptop application, we have tested it for short (e.g. Illumina paired-end) and long-read data (PacBio and Oxford Nanopore) focusing on small and medium scale datasets that can be widely used to the greater research community. However, please note that visualising a big dataset would not be recommended due to the limitation of computational resources on desktops. 


# Citation

Hyungtaek Jung et al: **iVPSV**: An intuitive visualisation platform for structural variation data on desktops, [Peparation for Submission](https://www.wageningenacademic.com/doi/abs/10.3920/978-90-8686-940-4_353).

# Contents

    •	STABLE
    •	INSTALLATION
    •	LICENSE 
    •	GETTING STARTED
    •	FAQ
    •	WIKI PAGE
    •	AUTHOR
    •	COPYRIGHT
    
## STABLE (version 1.0.XXX)
**iVPSV** is made up of six programs and packages (See LICENSE), mainly written in Python 3.7+.

## INSTALLATION
Windows: Please download the program from [this link](https://github.com/TaekAndBrendan/ivpsv/ivpsv-08.5.7z)
!!! Please note, for antivirus issues, please follow these steps: 1) click "undo action token" from "other actions", 2) click "start undo", and 3) re-install the program. Alternatively, if you see this dialog box "Suspicious File Warning", "It contains a suspicious file. Do you want to proceed with decompression?", please just click "Yes". Any other issues, we highly encourage users to use the [Issues](https://github.com/OZTaekOppa/iVPSV/issues).

Linux or Mac: To install iVPSV, run the following series of commands.

~~~
### Create the virtual environment
python -m venv venv 
source venv/bin/activate

### Get source
git clone https://github.com/OZTaekOppa/iVPSV
cd ivpsv

### Install packages
### pip -m pip install --upgrade pip # if you get errors, try to upgrade pip 
pip install -r requirements.txt 

### Run
python ivpsv.py
~~~

## License

**iVPSV** is provided under the MIT license and is based on other open-source software, Python packages and JavaScript library:

[PyQt5](https://pypi.org/project/PyQt5/) for a Python binding of the cross-platform GUI toolkit Qt

[gffutils](https://github.com/daler/gffutils) for working with and manipulating the [GFF](https://seqan.readthedocs.io/en/master/Tutorial/InputOutput/GffAndGtfIO.html), [GFF3](https://github.com/The-Sequence-Ontology/Specifications/blob/master/gff3.md) and [GTF](https://biocorecrg.github.io/PhD_course/gtf_format.html) format files

[PyVCF](https://pyvcf.readthedocs.io/en/latest/#) for parsing variant call format by mimicking the csv module in the Python stdlib, as opposed to more flexible serialisation formats like JSON or YAML

[bamnostic](https://bamnostic.readthedocs.io/en/latest/index.html) for OS-agnositic Binary Alignment Map (BAM) file parser and random access tool

[D3.js](https://d3js.org/) for producing dynamic, interactive data visualisation with HTML, SVG and CSS

[jQuery](https://jquery.com/) for simplifying HTML DOM tree traversal, manipulation, event handling, CSS animation, and Ajax


## Tested Datasets
[Reference genome](https://www.ncbi.nlm.nih.gov/assembly/GCF_000001735.3/#/st)

[Reference gff3 and gtf](https://ftp.ncbi.nlm.nih.gov/genomes/all/GCF/000/001/735/GCF_000001735.3_TAIR10/GO_TO_CURRENT_VERSION/)

[Illumina PE reads](https://www.ncbi.nlm.nih.gov/sra/?term=PRJEB31147) and [it's publication](https://www.nature.com/articles/s41467-020-14779-y)

[NovaSeq PE reads](https://ngdc.cncb.ac.cn/gsa/browse/CRA004538) and [it's publication](https://www.sciencedirect.com/science/article/pii/S1672022921001741)

[Oxford Nanopore reads](https://ngdc.cncb.ac.cn/gsa/browse/CRA004538) and [it's publication](https://www.sciencedirect.com/science/article/pii/S1672022921001741)

[PacBio reads](https://www.ncbi.nlm.nih.gov/sra/?term=PRJEB31147) and [it's publication](https://www.nature.com/articles/s41467-020-14779-y)


## Tested Programs
Shor-read aligners: [BWA-MEM](https://github.com/lh3/bwa), [Bowtie2](https://github.com/BenLangmead/bowtie2) and [Minimap2](https://github.com/lh3/minimap2) with SR (short genomic paired-end reads) and MD (output the MD tag) mode

Long-read aligners: [Minimap2](https://github.com/lh3/minimap2) MAB-PB, MAB-ONT and MD mode

Short-read structural variation caller: [Manta](https://github.com/Illumina/manta)

Long-read structuravl variation callers: [cuteSV](https://github.com/tjiangHIT/cuteSV) and [SVIM](https://github.com/eldariont/svim)


## GETTING STARTED

**iVPSV**, mainly written in Python 3.7+ and JavaScript, has two specific features: a data input module and a result visualisation window. The data input module enables end-to-end file selection. The result visualisation window is mainly designed to visualise the outcome selected by a user. Please note that all required input files (e.g. vcf, gff, gtf, bam, and fasta) must be prepared from third-party programs before running the **iVPSV**. And, all input files must be in your local drive on your desktops.


### Main data input module (MIM)

![Figure 1: Integration of the main window with a data input module of iVPSV.](./figures/iVPSV_Pics1.png)
**Figure 1: Integration of the main window with a data input module of iVPSV.**

I) One main input module (vcf only, red box) and three extra work modules (green box) to VCF Viewer, SV Navigator (BAM/GFF/GTF), and FASTA Extractor (Fig 1A). 

II) Filtering options for Chromosomes, structural variation length, structural variation type (INS, DEL, INV, DUP, and BND), and Chromosome start/end (red box) (Fig 1A).

III) Three extra main modules (green box) to assist with main input modules and extra features using a right mouse click. 

IV) Informative how to use and outcome window (Fig 1B).


![Figure 2: Integration of main data input module of iVPSV.](./figures/iVPSV_Pics2.png)
**Figure 2: Integration of main data input module of iVPSV.**

MIM Step 1: Browse and select your input file (one vcf file from I) (Fig 2A and B). Once browsed and selected, click OK. It is highly recommended to make sure your working directory is your local drive for moving to the next steps.

MIM Step 2: Browse and select the filtering options from II (Fig 2C). The default will be all chromosomes that will take a longer time to visualise. The checked "Pass" will default to see the passed structural variation outcome from the vcf file.

MIM Step 3: Natigate the summarised outcomes (Fig 2D and E) (e.g. bar graphs). Move your mouse on each graph to see more interactive information. Zoom in/out mode is also acceptable.

MIM Step 4: To see real-time log reporting and monitoring for an executed job, a pop-up dialogue box will be available. 


### Extra main work module (EWM)

These are integrated with the main data input module based on the type of file that is to be analysed and visualised. 

* **Variant Call Format (VCF)** # A VCF Structural Variation file format generated by third-party programs (Must be in the same folder)
* **BLAST-Like Alignment Tool (BAM)** # BAM alignment file format (.bam.fai must be in the same folder) (default filtering quality: 15)
* **General Feature Format and Gene Transfer Format (GFF/GTF)** # GFF/GTF file format (Must be in the same folder)
* **Fasta file (FASTA)**  # Fasta file format (.fasta.fai must be in the same folder)
    
Each of these modules contains many user-friendly navigation/interactive modes for manipulating, filtering, sorting, or analysing these types of files.

#### VCF Viewer
The VCF module is designed to easily import and run searches on a local computer and database. Using "Extra VCF File", a multiple vcf file can be uploaded and analysed. The same filtering options can be applied for the multiple vcf files too.
Figure 3 shows an easy step for each stage of the VCF module.

![Figure 3: User-friendly standalone work modules in iVPSV: VCF Viewer.](./figures/iVPSV_Pics3.png)
**Figure 3: User-friendly standalone work modules in iVPSV: VCF Viewer.**

Most steps include further manual options for a user-specified parameter. 

VCF Step 1) Browse and select your input file (multiple vcf files). Once browsed and selected, click OK. Or, you can delete unwanted vcf file from the topdown selection (Fig 3A and B). 

VCF Step 2) Browse and select the filtering options from II (Fig 3A and B). Once browsed and selected, click Filter (Fig 3C). The default will be all chromosomes that will take a longer time to visualise. The checked "Pass" will default to see the passed structural variation outcome from the vcf file.

VCF Step 3) Navigate the summarised outcomes (Fig 3D and E) (e.g. bar graphs). Move your mouse on each graph to see more interactive information. Zoom in/out mode is also acceptable. Screen capture is recommended to save the outcome.

**Note: Please make sure all files are in your local drive for moving the next steps.  

#### SV Navigator
The SV Navigator is designed to easily import and run searches on a local computer and database. Using "BAM and GFF3", a multiple bam file can be uploaded and analysed. The same filtering options can be applied for the multiple bam files too. Please note bam.bai file must be in the same folder.
Figure 4 shows an easy step for each stage for the SV Navigator.

![Figure 4: User-friendly standalone work modules in iVPSV: SV Navigator Part1.](./figures/iVPSV_Pics41.png) 
**Figure 4: User-friendly standalone work modules in iVPSV: SV Navigator Part1.**


![Figure 4: User-friendly standalone work modules in iVPSV: SV Navigator Part2.](./figures/iVPSV_Pics42.png)
**Figure 4: User-friendly standalone work modules in iVPSV: SV Navigator Part2.**

BAM Step 1) Browse and select your input file (multiple bam files) (Fig 4A and B). Once browsed and selected, click Filter (Fig 4C). Or, you can delete unwanted bam files from the topdown selection. The GFF3 file can be uploaded via the same Browse and select (Fig 4D).

BAM Step 2) Browse and select the filtering options from II (Fig 4A and B). The default will be all chromosomes that will take a longer time to visualise. The checked "Pass" will default to see the passed structural variation outcomes from the vcf and bam file. 

BAM Step 3) Once browsed, selected, filtered (Fig 4C), click Fetch (Fig 4E) to see the BAM and GFF3 information. Selected structural variation types (Fig 4F) can be navigated by clicking Previous and Next (Fig 4G).

BAM Step 4) Navigate the summarised outcomes from VCF Viewer (Fig 3D and E) as well as BAM and GFF3 information (Fig 4H ~ J). Move your mouse on each graph to see more interactive information.

**Note: Please make sure all files are in your local drive for moving the next steps. And, the large bam and gff3 files could take a longer time to upload and create a local database.


#### FASTA Extractor
It is designed to easily extract (indexed ID with its sequence) of your target genomic sequence on a local computer. 
Figure 5 shows an easy step for each stage for the FASTA module.

![Figure 5: User-friendly standalone work modules in iVPSV: FASTA Extractor.](./figures/iVPSV_Pics5.png)
**Figure 5: User-friendly standalone work modules in iVPSV: FASTA Extractor.**

FASTA Step 1) Browse and select your input file (fasta and fasta.fai files). Once browsed and selected, click OK (Fig 5A). 

FASTA Step 2) Browse and select the filtering options from Chromes start (forward) and end (reverse) location (Fig 5B). 

FASTA Step 3) Selected and extracted sequence will be saved in your preferred location (local drive) (Fig 5C ~ E) 


## FAQ

We encourage users to use the [Issues](https://github.com/OZTaekOppa/iVPSV/issues).

## WIKI PAGE

Please see the GitHub page.

## AUTHOR
Hyungtaek Jung

## COPYRIGHT

The full **iVPSV** is distributed under the MIT license. 
