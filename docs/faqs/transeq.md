#### What is EMBOSS Transeq?
EMBOSS Transeq is a program to translate nucleic acid sequences into their corresponding peptide sequences.

#### What is EMBOSS?
EMBOSS - European Molecular Biology Open Software Suite - is a collection of useful tools for molecular biology. More information can be found at the [EMBOSS home page](http://emboss.open-bio.org/).

#### Why is EMBOSS Transeq useful?
Translating nucleic acid sequences into peptide sequences can reveal information about the reading frame and allow further analysis on the possible peptide.
Top

#### How can I use EMBOSS Transeq?
The EMBOSS Transeq web form is available [here](http://www.ebi.ac.uk/Tools/st/emboss_transeq/). There are two ways to use this service at the EBI. The first is interactively (default) and the second is by email. Using it interactively, the user must wait for the results to be displayed in the browser window. The email option means that the results will not be displayed in the browser window but instead a link to the results will be sent by email. The email option is the better one to take when submitting large amounts of data or a job that might take a long time to run.

The EMBOSS Transeq service can also be accessed programmatically via [webservices](https://ebi-jdispatcher.github.io/documentation/webservices/).

#### What version of EMBOSS Transeq is run at the EBI?
For the precise version number of EMBOSS Transeq being run please go to the submission details tab from your job results.

#### How do I reference use of EMBOSS Transeq at the EBI?
Please cite use of EMBOSS Transeq with the following:

`EMBOSS: The European Molecular Biology Open Software Suite Rice P., Longden I. and Bleasby A. Trends in Genetics. 2000 16(6):276-277` [doi:10.1016/S0168-9525(00)02024-2](http://dx.doi.org/10.1016/S0168-9525(00)02024-2)

`A new bioinformatics analysis tools framework at EMBL-EBI (2010) Goujon M, McWilliam H, Li W, Valentin F, Squizzato S, Paern J, Lopez R Nucleic acids research 2010 Jul, 38 Suppl: W695-9`

#### What inputs does EMBOSS Transeq accept?
The program accepts nucleic acid sequences in a known sequence format. The full list of sequence formats accepted as input by EMBOSS tools is given in this table: [EMBOSS sequence formats](http://emboss.open-bio.org/html/use/ch05s02.html#d0e5958)

The sequences can either be pasted into the web form or uploaded to the web form in a file. 

#### How do I input multiple sequences into a single box?
Paste the sequences in an accepted format into the same box: EMBOSS Transeq accepts multiple sequence formats as input - these formats allow for multiple sequences to be placed in the same file or input box, as they each contain ways for EMBOSS Transeq to distinguish where new sequences start. It is important to use correctly formated sequences for this reason. 

#### Is there a limit on the number of sequences or the size of the file that I submit to EMBOSS Transeq?
The input for EMBOSS Transeq is limited to a maximum of 500 sequences or to a 1MB file (whichever is smaller). For batch runs of EMBOSS Transeq see our [programmatic access page](http://www.ebi.ac.uk/Tools/webservices/) 

#### Where can I find information on the different parameters/options?
Clicking on the parameter names will take you to the relevant help information. Additional parameters can be adjusted by clicking on the more options button. 

#### What outputs does EMBOSS Transeq produce?
EMBOSS Transeq outputs a single translated text file in FASTA format. 

#### How do I download the translation?
The quickest way to download the alignment is to click the 'Download Alignment File' button in the alignments tab of the results. Colours are not saved as part of the file. You can also copy/paste the text, in which case colours might be preserved, depending on your browser. 

#### Why is the translation/frame different from another tool I'm using?
EMBOSS Transeq uses the Staden convention: Frame -1 is the reverse-complement of the sequence having the same codon phase as frame 1. Frame -2 is the same phase as frame 2. Frame -3 is the same phase as frame 3. 

#### How long are results stored at the EBI?
Results are stored at the EBI for a week from the date of job submission. 

#### What do the colours mean when I show them on the translation?
This option colours the residues according to their physicochemical properties:

| Residue       | Colour                               | Property                                        |                    
| -----------   | ----------------------------         | -----------      |
| `AVFPMILW`    | <font color=red>RED</font>           | `Small (small+ hydrophobic (incl.aromatic -Y))`   |
| `DE`          | <font color=blue>BLUE</font>         | `Acidic`   |
| `RK`          |  <font color=magenta>MAGENTA</font>  | `Basic - H` |
| `STYHCNGQ`    | <font color=green>GREEN</font>       | `Hydroxyl + sulfhydryl + amine + G` |
| `Others`      | <font color=gray>GRAY</font>         | `Unusual amino/imino acids etc` |


#### Why do I get a 'Raw Tool Output' page?
This happens when we can't parse the results of your EMBOSS Transeq job - usually because the job has failed for some reason. Have a look at the links on the page, especially the Tool Error Details, for clues as to why this might have happened, and check your input for errors. 

#### Why do I get a 'Job not found' page?
This happens when we can't find the job that you have requested. Normally it's a result of trying to look at the page over a week after the job was submitted, so the data is no longer available at the EBI. If you've copied the URL from a recent email job, check for any mistakes in the link.