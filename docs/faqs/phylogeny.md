# Simple Phylogeny FAQs

#### What is Simple Phylogeny?
Simple Phylogeny is a tool to perform basic phylogenetic analysis on a multiple sequence alignment.

#### Why is Simple Phylogeny useful?
Phylogenetics aims to model the substitutions that have occured over evolutionary time and derive and represent the evolutionary relationships between sequences.

#### How can I use Simple Phylogeny?
The Simple Phylogeny web form is available [here](http://www.ebi.ac.uk/Tools/phylogeny/simple_phylogeny/). There are two ways to use this service at EMBL-EBI. The first is interactively (default) and the second is by email. Using it interactively, the user must wait for the results to be displayed in the browser window. The email option means that the results will not be displayed in the browser window but instead a link to the results will be sent by email. The email option is the better one to take when submitting large amounts of data or a job that might take a long time to run. 

#### What version of Simple Phylogeny is run at EMBL-EBI?
We run Simple Phylogeny from the ClustalW2 package at EMBL-EBI, for the precise version number go to the submission details tab from your job results.

#### How do I reference use of Simple Phylogeny at EMBL-EBI?
Please cite use of Simple Phylogeny at our website with the following: 

`ClustalW and ClustalX version 2 (2007)Larkin MA, Blackshields G, Brown NP, Chenna R, McGettigan PA, McWilliam H, Valentin F, Wallace IM, Wilm A, Lopez R, Thompson JD, Gibson TJ and Higgins DGBioinformatics 2007 23(21): 2947-2948.` 

`A new bioinformatics analysis tools framework at EMBL-EMBL-EBI (2010)Goujon M, McWilliam H, Li W, Valentin F, Squizzato S, Paern J, Lopez RNucleic acids research 2010 Jul, 38 Suppl: W695-9` 

Programmatic use via Web Services should cite:

`Search and sequence analysis tools services from EMBL-EBI in 2022. (2022) Madeira F, Pearce M, Tivey, ARN, Basutkar P, Lee J, Edbali O, Madhusoodanan N, Kolesnikov A, Lopez R Nucleic acids research 2022; Jul;50:W276–W279` [DOI: 10.1093/nar/gkac240](https://doi.org/10.1093/nar/gkac240)


#### What inputs does Simple Phylogeny accept?
The program accepts protein multiple sequence alignments, in the following multiple sequence formats:

Pearson (FASTA)
ALN/ClustalW
GCG/MSF
RSF (see the Clustal help pages for details about formats)
Please note GenBank (from NCBI) or raw sequence data will not work with Simple Phylogeny. If using sequences from NCBI be sure to save them as FASTA format first.

The sequences can either be pasted into the web form or uploaded to the web form in a file. It is very important that each of the sequences has a unique name. If they do not, the program will fail. There must be no empty lines, white spaces or control characters between sequences or at the top of the file. This will also cause the program to fail.

#### How do I input multiple sequences into a single box?
Paste the sequences in an accepted format into the same box: Simple Phylogeny accepts multiple sequence formats as input - these formats allow for multiple sequences to be placed in the same file or input box, as they each contain ways for Simple Phylogeny to distinguish where new sequences start. It is important to use correctly formated sequences for this reason.

#### Is there a limit on the number of sequences or the size of the file that I submit to Simple Phylogeny?
The input for Simple Phylogeny is limited to a maximum of 500 sequences or to a 1MB file (whichever is smaller). When the input file or the number of sequences is large, Simple Phylogeny can run for days and in some cases may not finish at all. If you plan to input large amounts of data/sequences you should use the email results option. For batch runs of Simple Phylogeny see our [programmatic access page](https://ebi-jdispatcher.github.io/documentation/webservices/).

#### Where can I find information on the different parameters/options?
The parameter settings are in the box below the sequence input. Clicking on the parameter name will take you to the relevant help information.

#### Why do I get a 'minimum 2 sequences required' error?
This occurs when something is wrong with your sequence input. It is often caused by using a sequence format not supported by Simple Phylogeny, or a problem with the formatting for example sequence data not being on a newline from the sequence header line. Simple Phylogeny requires sequences to be formatted, not just raw sequence data.

Information about sequence formats can be found at the [EMBOSS sequence formats guide](http://emboss.sourceforge.net/docs/themes/SequenceFormats.html). If you're not sure, try using FASTA format. You can also use tools like [Readseq](https://www.ebi.ac.uk/Tools/misc.html) to convert between sequence formats.
top

#### Why do I get a 'Two sequences cannot share the same identifier' error?
Simple Phylogeny needs unique sequence identifiers, which it defines as the first word on the sequence identifier line. Check that you've not got a duplicate identifier somewhere in the input, that you're not using spaces or tabs in your identifiers, and that the first 30 characters of your identifier are unique if using Clustal format files.

#### What does 'Entry found which does not contain a sequence' mean?
Simple Phylogeny produces this error when it can't find the sequence data to go with a sequence identifier. This can happen if sequence data is missing from the input or the data is on the same line as the header - make sure the sequence data is on a new line.

#### Why does Simple Phylogeny truncate my identifier? 
Clustal file format (.aln) truncates sequence identifiers to 30 characters - this may also affect the ability of the job to run if the first 30 characters are not unique.

#### How can I apply distance correction to my tree?
By default no distance correction is applied. Using the 'Distance Correction' option you can apply distance correction to phylogenetic trees. The distance correction method is Kimura:

`A simple method for estimating evolutionary rates of base substitutions through comparative studies of nucleotide sequences.(1980)Kimura MJournal of Molecular Evolution 1980 16:111120.`

More information about this and other evolutionary models for DNA substitution can be found at Wikipedia: [Models of DNA evolution, Kimura](http://en.wikipedia.org/wiki/Models_of_DNA_evolution#K80_model_.28Kimura.2C_1980.29.5B2.5D).

#### What outputs does Simple Phylogeny produce?
Simple Phylogeny produces several outputs, depending on the options you selected when submitting the job. By default the main output is a phylogenetic tree, with both the tree data (Newick format) and an image representation of the tree. Other outputs can be viewed/downloaded in the results summary tab.

#### How do I download/save the phylogenetic tree?
The tree data can be saved by clicking the 'View Phylogetic Tree file' button or by clicking the tree link in the Results Summary tab. Using this data you can recreate the tree in any tree viewing software that takes Newick format tree data.

The tree image cannot be saved directly as it is a dynamic Java-driven interface, however you can take a screenshot and then save this in an image editing program, or as mentioned above use the tree data to recreate the tree in another tree viewing program and save it from there.

#### How can I view my tree after I've downloaded it?
The tree data is in the widely used Newick format, there are several online or standalone tree viewing programs available that can take this and recreate the tree from this data.

#### I'm using Internet Explorer 9 and why aren't my button presses working?
Unfortunately there is a compatibility problem with Internet Explorer 9 and some of the ways we create drop down menus on our website. This has the occasional side effect of making it impossible to click on buttons for example to change to a different results tab, or show colours. If you experience difficulties we recommend firstly trying the compatibility view icon on the URL bar of Internet Explorer. If this doesn't work please try another browser.

#### How can I see distance values/branch lengths on my tree?
Unfortunately we can't display a scale bar or branch lengths on the branches themselves, however the show distances button will add distance values to the node label. These show the length of the branch immediately leading to the node. Interbranch distances are not shown on the tree, but can be seen in the tree data file.

#### What units are the distance values?
The distance values show the number of substitutions (nucleotides or amino acid residues) as a proportion of the length of the alignment (excluding gaps). These numbers represent the amount of genetic change.Generally, the larger the number, the larger the amount of genetic change. 

#### Can I add bootstrap values to my tree?
We do not allow bootstrap analysis of phylogenetic trees for throughput reasons. If you wish to perform a more rigorous phylogenetic analysis we recommend using a different tool.

#### What is the difference between a cladogram and a phylogram?
A phylogram is a branching diagram (tree) that is assumed to be an estimate of a phylogeny. The branch lengths are proportional to the amount of inferred evolutionary change. A cladogram is a branching diagram (tree) assumed to be an estimate of a phylogeny where the branches are of equal length. Therefore, cladograms show common ancestry, but do not indicate the amount of evolutionary "time" separating taxa. It is possible to see the tree distances by clicking on the diagram to get a menu of options. The options available allow you to do things like changing the colours of lines and fonts and showing the distances.

#### How long are results stored at EMBL-EBI?
Results are stored at EMBL-EBI for a week from the date of job submission.

#### Why do I get a 'Raw Tool Output' page?
This happens when we can't parse the results of your Simple Phylogeny job - usually because the job has failed for some reason. Have a look at the links on the page, especially the Tool Error Details, for clues as to why this might have happened, and check your input for errors.

#### Why do I get a 'Job not found' page?
This happens when we can't find the job that you have requested. Normally it's a result of trying to look at the page over a week after the job was submitted, so the data is no longer available at EMBL-EBI. If you've copied the URL from a recent email job, check for any mistakes in the link.

#### Why do I see 'Java is required'?
The phylogenetic tree representation requires Java to work properly. If Java isn't installed with your browser or it doesn't have permission to run (for example it has been disabled due to being out of date) then there may be some results options missing.

To update your version of Java go to the [Java.com download page](https://java.com/en/download/index.jsp).