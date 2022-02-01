# Machine Learning for genomics

## Data

### Replication specific:

Database name |Organisms                | Data type | Link | Access| Commentaries|
--------------|-------------------------|-----------|------|-------|-------------|
Replication domain |ARABIDOPSIS, Chinese Hamster (C. GRISEUS) , Fruit Fly (D.Megalonaster), Chicken (G. Gallus), Human (Homo sapiens), Mouse (Mus Musculus) , Yeast (S. Pombe) | RT , 4C , GE ,... |  https://www2.replicationdomain.com  | Open
The genetic architecture of DNA replication timing in human pluripotent stem cells | Human | RT chip-seq histone individual genomes | https://www.nature.com/articles/s41467-021-27115-9 | Data comes from various sources, some with restricted access (genetic ones)  |

### Epigenetic:

Database name |Organisms                | Data type | Link | Access| Commentaries|
--------------|-------------------------|-----------|------|-------|-------------|
ENCODE        | Human (Homo sapiens), Mouse (Mus Musculus), Caenorhabditis elegans , Fruit Fly (D. Melanogaster) | Histones, TRanscription factors | https://www.encodeproject.org/ | Open |
IHEC          | Human (Homo sapiens), Mouse (Mus Musculus)     | Subset of Histones, Methylome, transcriptome | https://epigenomesportal.ca/ihec/grid.html?assembly=1&build=2020-10 | Open |
Roadmap epigenome | Human (Homo sapiens) | Histones, DNase, RNASeq, Methylation |https://egg2.wustl.edu/roadmap/web_portal/index.html | Open
Deep Blue     | Human | Histones, chip-seq DNase| https://deepblue.mpi-inf.mpg.de/dashboard.php#ajax/dashboard.php | Open | regroup different databases (Encode, CHIP Atlas, CEEHRC ,Blueprint epigenome, Roadmap epigenomics) Has a programatic acces |
Yeast Epigenome | Yeast (S. Cerevisae ) | CHip seq exo| http://www.yeastepigenome.org | Open | 400 different targets, bulk download available https://github.com/CEGRcode/2021-Rossi_Nature
Chromatin dynamics during DNA replication |  Yeast (S. Cerevisae ) | CHip seq | ENA; https://www.ebi.ac.uk/ena/)PRJEB11501, PRJEB13262, and PRJEB11977.  | Open


## Models and code

Name    | Type of models  | Input type | Output Type | Main Results| Usability      | Reproductibility | Alterable | Data | Commentaries|  Link|
--------|-----------------|------------|-------------|-------------|----------------|------------------|-----------|------|-------------|------|
Avocado | Dense NN        | assay, cell type, genomic position (positionnal encoding at 25 bp) | value of the experiment at the given position| Creates an embedding for a cell type an assay an all elong the genome| Great (tutorials availabel) | Ok on a smaller training set | Code is clean | Open (from ENCODE) but need to be gathered | I modified the code to use CNN for embedding. (It seems to work well) . There is a preprint that use data in human to improve result on mouse. Could the assay embedding be changed to a protein embedding?  | https://github.com/jmschrei/avocado
MARS | Graph NN | Single cell transcriptome | cell embedding  | Allows to discover and classify celll type | | | | | | https://github.com/snap-stanford/mars
