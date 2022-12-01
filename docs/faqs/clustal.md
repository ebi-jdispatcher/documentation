
#### Why is Clustal Omega useful?
Aligning multiple sequences highlights areas of similarity which may be associated with specific features that have been more highly conserved than other regions. These regions in turn can help classify sequences or to inform experiment design. 

Multiple sequence alignment is also an important step for phylogenetic analysis, which aims to model the substitutions that have occured over evolution and derive the evolutionary relationships between sequences. 

Clustal Omega improves on ClustalW in a number of ways - alignment accuracy and improved scaling to many sequences are the main results. 

#### How can I use Clustal Omega?
The Clustal Omega multiple sequence alignment web form is available [here](http://www.ebi.ac.uk/Tools/msa/clustalo/). There are two ways to use this service at EMBL-EBI. The first is interactively (default) and the second is by email. Using it interactively, the user must wait for the results to be displayed in the browser window. The email option means that the results will not be displayed in the browser window but instead a link to the results will be sent by email. The email option is the better one to take when submitting large amounts of data or a job that might take a long time to run. 

#### What version of Clustal Omega is run at EMBL-EBI?
For the precise version number of Clustal Omega being run please go to the submission details tab from your job results. 

#### How do I reference use of Clustal Omega at EMBL-EBI?

Please cite use of Clustal Omega with the following:

`Fast, scalable generation of high-quality protein multiple sequence alignments using Clustal Omega Sievers F, Wilm A, Dineen DG, Gibson TJ, Karplus K, Li W, Lopez R, McWilliam H, Remmert M, Söding J, Thompson JD, Higgins D Molecular Systems Biology 7 Article number: 539` [doi:10.1038/msb.2011.75](https://dx.doi.org/10.1038/msb.2011.75)

`A new bioinformatics analysis tools framework at EMBL-EBI (2010) Goujon M, McWilliam H, Li W, Valentin F, Squizzato S, Paern J, Lopez R Nucleic acids research 2010 Jul, 38 Suppl: W695-9` [doi:10.1093/nar/gkq313](https://dx.doi.org/10.1093/nar/gkq313) 

Programmatic use via Web Services should cite:
`Search and sequence analysis tools services from EMBL-EBI in 2022. (2022) Madeira F, Pearce M, Tivey, ARN, Basutkar P, Lee J, Edbali O, Madhusoodanan N, Kolesnikov A, Lopez R Nucleic acids research 2022; Jul;50:W276–W279` [DOI: 10.1093/nar/gkac240](https://doi.org/10.1093/nar/gkac240)

#### What inputs does Clustal Omega accept? 
The program accepts nucleic acid or protein sequences, in the following multiple sequence formats:

NBRF/PIR
EMBL/UniProt
Pearson (FASTA)
GDE
ALN/Clustal
GCG/MSF
RSF 

Please note raw sequence data (just the sequence with no recognised formatting) will not work with Clustal Omega. If using sequences from NCBI we recommend saving them as FASTA format first. Sequence format conversion tools are available [here] (http://www.ebi.ac.uk/Tools/sfc/).

Very long or badly aligning nucleotide sequences (so that the alignment approaches 100k characters in length) may cause Clustal Omega to fail.

The sequences can either be pasted into the web form or uploaded to the web form in a file. It is very important that each of the sequences has a unique name. If they do not, the program will fail. There must be no empty lines, white spaces or control characters between sequences or at the top of the file. This will also cause the program to fail.

#### How do I input multiple sequences into a single box?
Paste the sequences in an accepted format into the same box: Clustal Omega accepts multiple sequence formats as input - these formats allow for multiple sequences to be placed in the same file or input box, as they each contain ways for Clustal Omega to distinguish where new sequences start. It is important to use correctly formated sequences for this reason.

#### Is there a limit on the number of sequences or the size of the file that I submit to Clustal Omega?
The input for Clustal Omega is limited to a maximum of 4000 sequences or to a 4MB file (whichever is smaller). If you need to align higher than this number of sequences/a larger file we recommended you download Clustal Omega and run it locally. When the input file or the number of sequences is large, Clustal Omega can run for days and in some cases may not finish at all - we recommend use of the email results option for long running jobs. To use Clustal Omega in a batch/scripted fashion please see our [programmatic accss page](https://ebi-jdispatcher.github.io/documentation/webservices/) 
#### What does a 'stream closed' error mean?
This error sometimes occurs if you try to upload a really large input to our tools, far in excess of the limits described above. Make sure your input falls within the previously described limits. 

#### Where can I find information on the different parameters/options?
To view parameter settings for Clustal Omega click the 'More options' buttons. Clicking on the parameter name will take you to the relevant help information. 

#### What substitution matrix/default parameters are used by Clustal Omega?
Clustal Omega uses the HHalign algorithm and its default settings as its core alignment engine. The algorithm is described in Söding, J. (2005) 'Protein homology detection by HMM–HMM comparison'. Bioinformatics 21, 951-960.

The default transition matrix is Gonnet, gap opening penalty is 6 bits, gap extension is 1 bit. 

#### What are the best settings for aligning two sequences?
Trick question! Multiple sequence alignment tools like Clustal Omega are designed to align three or more sequences. To align two sequences you should use our [pairwise alignment tools](http://www.ebi.ac.uk/Tools/psa/)

#### Why do I get a 'minimum 2 sequences required' error?
This occurs when something is wrong with your sequence input. It is often caused by using a sequence format not supported by Clustal Omega, or a problem with the formatting for example sequence data not being on a newline from the sequence header line. Clustal Omega requires sequences to be formatted, not just raw sequence data.

Information about sequence formats can be found at the [EMBOSS sequence formats guide](http://emboss.sourceforge.net/docs/themes/SequenceFormats.html). If you're not sure, try using FASTA format. Sequence format conversion tools are available [here](http://www.ebi.ac.uk/Tools/sfc/). 

#### Why do I get a 'Two sequences cannot share the same identifier' error?
Clustal Omega needs unique sequence identifiers, which it defines as the first word on the sequence identifier line. Check that you've not got a duplicate identifier somewhere in the input, that you're not using spaces or tabs in your identifiers, and that the first 30 characters of your identifier are unique if using Clustal format files. 

#### What does 'Entry found which does not contain a sequence' mean?
Clustal Omega produces this error when it can't find the sequence data to go with a sequence identifier. This can happen if sequence data is missing from the input or the data is on the same line as the header - make sure the sequence data is on a new line. 

#### Why does Clustal Omega truncate my identifier?
The default output format (ALN/Clustal format) truncates sequence identifiers to 30 characters - this may also affect the ability of the job to run if the first 30 characters are not unique. The PHYLIP format truncates even more restrictively, to 10 characters. To prevent truncation change the output format to a type that does not have a limit, such as pearson/FASTA. 

#### What outputs does Clustal Omega produce?
Clustal Omega produces several outputs, depending on the options you selected when submitting the job. By default the main output is the alignment file. A simple phylogenetic tree (via neighbour joining) can be found in the Phylogenetic Tree tab. A pairwise identity scores matrix and other outputs can be viewed/downloaded in the Results Summary tab. 

#### How do I see alignments with numbers?
By default, Clustal Omega outputs Clustal format alignments without numbering, to change this simply click 'more options' and change the output alignment format to 'Clustal w/ numbers'.

#### How do I download the alignment?
The quickest way to download the alignment is to click the 'Download Alignment File' button in the alignments tab of the results. You can view all the files that are produced on the 'Results Summary' tab, which includes the tool output and any guide tree files as well as the alignment file. Colours are not saved as part of the alignment.

#### How can I view my alignment after I've downloaded it?
The alignment will be in the format you specified in the input section, or Clustal by default if you didn't specify anything. They are all text files, so can be opened in any text viewing program that can deal with unix text characters (end of line characters for example). In Windows you can use NotePad.

More specialist tools are available to investigate alignments and allow you to mark them up with colours for example. [Genedoc](http://www.nrbsc.org/gfx/genedoc/) and [Jalview](http://www.jalview.org/) are two such tools.

#### Why are there no pairwise scores for Clustal Omega?
Clustal Omega uses a different method to calculate the guide tree compared to ClustalW, so we do not output the rough all-against-all pairwise alignment scores used to guide the alignment (as they don't exist). However we do calculate a pairwise identity matrix from the results, which can be downloaded from the Results Summary tab.

#### How do I see the guide tree for Clustal Omega?
By default Clustal Omega uses a sampling method called mBed to speed up the guide tree calculations so a traditional tree is not shown. To create a phylogenetic tree go to the Phylogenetic Tree tab in the results.

#### How do I download/save the phylogenetic tree?
The tree data can be saved by clicking the 'View Phylogetic Tree file' button or by clicking the tree link in the Results Summary tab. Using this data you can recreate the tree in any tree viewing software that takes Newick format tree data.

The tree image cannot be saved directly as it is a dynamic java-driven interface, however you can take a screenshot and then save this in an image editing program, or as mentioned above use the tree data to recreate the tree in another tree viewing program and save it from there.

#### How can I view my tree after I've downloaded it?
The tree data is in the widely used Newick format, there are several online or standalone tree viewing programs available that can take this and recreate the tree from this data.


#### How long are results stored at EMBL-EBI?
Results are stored at EMBL-EBI for a week from the date of job submission and can be accessed via https://www.ebi.ac.uk/Tools/services/web/toolresult.ebi?jobId=<JOBID>.


#### What do the consensus symbols mean in the alignment?
An `*` (asterisk) indicates positions which have a single, fully conserved residue.

A `:` (colon) indicates conservation between groups of strongly similar properties as below - roughly equivalent to scoring > 0.5 in the Gonnet PAM 250 matrix:

STA
NEQK
NHQK
NDEQ
QHRK
MILV
MILF
HY
FYW

A `.` (period) indicates conservation between groups of weakly similar properties as below - roughly equivalent to scoring =< 0.5 and > 0 in the Gonnet PAM 250 matrix:

CSA
ATV
SAG
STNK
STPA
SGND
SNDEQK
NDEQHK
NEQHRK
FVLIM
HFY

Note that TV is included in the weaker scoring groups despite scoring 0.0 in the PAM 250 matrix, this is because it is a fairly common substitution as they are both beta-branched. In fully buried residues that is at the cost of a hydrogen bond. In fact, being relatively gentle, this substitution has been used in the past to make TS mutants. (Information courtesy of Toby Gibson).

The same symbols display for DNA/RNA alignments, so while * (asterisk) characters are still useful, the other characters should be ignored for DNA/RNA alignments.

#### Why do I get a 'Raw Tool Output' page?
This happens when we can't parse the results of your Clustal Omega job - usually because the job has failed for some reason. Have a look at the links on the page, especially the Tool Error Details, for clues as to why this might have happened, and check your input for errors.


#### Why do I get a 'Job not found' page?
This happens when we can't find the job that you have requested. Normally it's a result of trying to look at the page over a week after the job was submitted, so the data is no longer available at EMBL-EBI. If you've copied the URL from a recent email job, check for any mistakes in the link.

#### Why do I see 'Java is required'?
Some of the options for Clustal Omega results pages require Java to work properly. If Java isn't installed with your browser or it doesn't have permission to run (for example it has been disabled due to being out of date) then there may be some results options missing, for example the button to launch Jalview or the display of trees.

To update your version of Java go to the [Java.com download page](https://java.com/en/download/index.jsp).

#### What does the 'Error. Click' message mean in the Jalview box?
Jalview relies on Java, which requires that applications present correct certificates for security reasons. If the Jalview program doesn't have a currently valid certificate then it will be prevented from running and this error will remain until we recieve an update from the author.

To still run Jalview with this error you will need to go to the [Jalview website](https://www.jalview.org/) and run the desktop version of the program.
Top

#### How to interpret the resultant tree?
The values shown in the tree represent the "length" of the branches, which is an indication for evolutionary distance between the sequence, i.e these numbers represent the amount of genetic change.Generally, the larger the number, the larger the amount of genetic change.

During the construction of the tree, the algorithm takes the aligned sequences and builds a sequence distance matrix that is then used to arrive at an "optimal" tree by a clustering method. The workflow will be like Unaligned sequences->Clustal Omega->Aligned sequences->Clustal Phylogeny->Phylogenetic tree + PIM

