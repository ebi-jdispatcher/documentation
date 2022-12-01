#### What is FASTM?
FASTM is a sequence similarity search tool that searches a database using local alignments to a collection of fragments.

#### Why is FASTM useful?
Finding existing database entries that are homologous with your query sequence makes it possible to transfer information to your query sequence. This can be useful when annotating genomes, predicting protein function, characterising protein families and exploring distant evolutionary relationships for example.

#### How can I use FASTM?
The FASTM web form is available [here](http://www.ebi.ac.uk/Tools/sss/fastm/). There are two ways to use this service at EMBL-EBI. The first is interactively (default) and the second is by email. Using it interactively, the user must wait for the results to be displayed in the browser window. The email option means that the results will not be displayed in the browser window but instead a link to the results will be sent by email. The email option is the better one to take when submitting large amounts of data or a job that might take a long time to run.

#### What version of FASTM is run at EMBL-EBI?
For the precise version number please see the submission details tab in your job results.

#### How do I reference use of FASTM at EMBL-EBI?
Please cite use of FASTM at our website with the following: 

`Getting more from less: algorithms for rapid protein identification with multiple short peptide sequences.(2002)Mackey AJ, Haystead TA, Pearson WRMolecular & Cellular Proteomics : MCP [2002, 1(2):139-147]` [doi: 10.1074/mcp.M100004-MCP200](http://dx.doi.org/10.1074/mcp.M100004-MCP200) 

`A new bioinformatics analysis tools framework at EMBL-EBI (2010)Goujon M, McWilliam H, Li W, Valentin F, Squizzato S, Paern J, Lopez RNucleic acids research 2010 Jul, 38 Suppl: W695-9` [doi:10.1093/nar/gkq313](http://dx.doi.org/10.1093/nar/gkq313)

#### What inputs does FASTM accept?
The program accepts a single sequence file of a modified FASTA sequence format. This comprises a FASTA header line with an identifier for the set of sequences and optionally a description, followed by the individual sequences each starting on a newline and separated with commas.

The sequence can either be pasted into the web form or uploaded to the web form in a file.


#### Is there a limit on the number of sequences or the size of the file that I submit to FASTM?
The input for FASTM is limited to a single sequence file with a maximum of 1MB data. If you want to run several sequences you can script batch runs of FASTM using our [web services](http://www.ebi.ac.uk/Tools/webservices/)

#### Where can I find information on the different parameters/options?
To view parameter settings for FASTM click the 'More options' buttons. Clicking on the parameter name will take you to the relevant help information.

#### What outputs does FASTM produce?
The main FASTM output is the table of database hits and this is shown as the Summary Table tab. The raw output from the FASTM tool can be found in the Tool Output tab. The Visual Output tab gives a visual representation of the results, which helps identify which region in both your query sequence and the database sequence (subject) is aligning. For alignments against protein databases, the Functional Predictions tab scans all the database sequence results for hits against the InterPro collection of motif and families databases, as well as showing the region of alignment.

#### How do I download the results?
There are several downloads that are possible from FASTM. The simplest download is probably the Tool Output which can be downloaded as a text or XML file containing the hits and scores. From the Summary Table it is possible to download a file containing the sequence entries (only) that have been selected from the results using the download button. Buttons from the tabs with images can be used to download either a scalable vector graphics format file, or you can right click on any image to save it as a PNG format file.

#### How can I view my results after I've downloaded them?
Alignments/output saved as a text file can be opened in most text viewing/processing programs. XML output can be viewed in most browsers or imported into spreadsheet programs. PNG files can be viewed by image viewers or web browsers. SVG files might require more advanced image editors to view.

#### I'm using Internet Explorer 9 and why aren't my button presses working?
Unfortunately there is a compatibility problem with Internet Explorer 9 and some of the ways we create drop down menus on our website. This has the occasional side effect of making it impossible to click on buttons for example to change to a different results tab, or show colours. If you experience difficulties we recommend firstly trying the compatibility view icon on the URL bar of Internet Explorer. If this doesn't work please try another browser.

#### How do the fixed scale/dynamic scale options work in the visual results?
Fixed scale produces a bar with an Expect score from 0 to 100. Dynamic sets the left most of the bar to the smallest Expect score seen in the results, to the right most of the largest Expect score seen.

#### How long are results stored at EMBL-EBI?
Results are stored at EMBL-EBI for a week from the date of job submission.

What do the alignment symbols mean?
The exact format depends on the format selected on the input form, but by default:

`:` (colon) represents an identical match

`.` (period) represents a similar match (BLOSUM50 value greater than or equal to 0) 

`-` (hyphen) represents a gap in the sequence 

`X` represents part of the sequence that was filtered for low complexity.

#### Why do I get a 'Raw Tool Output' page?
This happens when we can't parse the results of your FASTM job - usually because the job has failed for some reason. Have a look at the links on the page, especially the Tool Error Details, for clues as to why this might have happened, and check your input for errors.

#### Why do I get a 'Job not found' page?
This happens when we can't find the job that you have requested. Normally it's a result of trying to look at the page over a week after the job was submitted, so the data is no longer available at the EMBL-EBI. If you've copied the URL from a recent email job, check for any mistakes in the link.