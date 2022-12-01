#### What is PSI-Search?
PSI-Search is a sequence similarity search tool that combines the sensitivity of the Smith-Waterman search algorithm (SSEARCH) with the PSI-BLAST profile construction strategy to find distantly related protein sequences in our protein databases.

#### Why is PSI-Search useful?
Finding existing database entries that are homologous with your query sequence makes it possible to transfer information to your query sequence. This can be useful when annotating genomes, predicting protein function, characterising protein families and exploring distant evolutionary relationships for example.

#### What is Homologous Over-Extension (HOE)?
Homologous Over-Extension, or HOE, is one of the main causes of PSSM corruption in iterative searches, which can result in database hits being labelled as statistically valid when they are unrelated to your query sequence. PSI-Search at EMBL-EMBL-EBI incorporates an option (enabled by default) to reduce the likelihood of this occuring, by masking the alignment boundaries.

For more information about HOE errors please see the following paper:

`Homologous over-extension: a challenge for iterative similarity searches (2010)Gonzalez MW and Pearson WRNucleic Acids Res. 2010 April; 38(7): 2177–2189.` [doi: 10.1093/nar/gkp1219](http://dx.doi.org/10.1093/nar/gkp1219)

#### How can I use PSI-Search?
The PSI-Search web form is available [here](http://www.ebi.ac.uk/Tools/sss/psisearch/). There are two ways to use this service at EMBL-EBI. The first is interactively (default) and the second is by email. Using it interactively, the user must wait for the results to be displayed in the browser window. The email option means that the results will not be displayed in the browser window but instead a link to the results will be sent by email. The email option is the better one to take when submitting large amounts of data or a job that might take a long time to run.

PSI-Search runs a little differently to non-iterative search methods. The first run is no different to a SSEARCH similarity search - this search is used to find sequences which can be used to build the PSSM. Once sequences have been selected for inclusion in the PSSM the next run (first iteration), initated by pressing the "Run next iteraction" button, will build a PSSM from these selections and PSI-Search will conduct a search using this PSSM. The results from this iteration can themselves be used to construct a new PSSM and another search.

#### What version of PSI-Search is run at EMBL-EBI?
For the precise version number please see the submission details tab in your job results.

#### How do I reference use of PSI-Search at EMBL-EBI?
Please cite use of PSI-Search at our website with the following: 

`PSI-Search: iterative HOE-reduced profile SSEARCH searching(2012)Li W, McWilliam H, Goujon M, Cowley A, Lopez R and Pearson WRBioinformatics (2012) 28 (12): 1650-1651.` [doi: 10.1093/bioinformatics/bts240](http://dx.doi.org/10.1093/bioinformatics/bts240)

`A new bioinformatics analysis tools framework at EMBL-EBI (2010)Goujon M, McWilliam H, Li W, Valentin F, Squizzato S, Paern J, Lopez RNucleic acids research 2010 Jul, 38 Suppl: W695-9` [doi:10.1093/nar/gkq313](http://dx.doi.org/10.1093/nar/gkq313)

#### What inputs does PSI-Search accept?
The program accepts a single protein sequence in a recognised sequence format. The full list of sequence formats accepted as input is given in this table: [EMBOSS sequence formats](http://emboss.open-bio.org/html/use/ch05s02.html#d0e5958) but please note that PSI-Search does not accept sequences with STOP characters (`*`) present.

The sequence can either be pasted into the web form or uploaded to the web form in a file.

#### Is there a limit on the number of sequences or the size of the file that I submit to PSI-Search?
The input for PSI-Search is limited to a single sequence with a maximum of 1MB data. If you want to run several sequences you can script batch runs of PSI-Search using our [web services](https://ebi-jdispatcher.github.io/documentation/webservices/)

#### Where can I find information on the different parameters/options?
To view parameter settings for PSI-Search click the 'More options' buttons. Clicking on the parameter name will take you to the relevant help information.

#### What outputs does PSI-Search produce?
The main PSI-Search output is the table of database hits and this is shown as the Summary Table tab. The raw output from the PSI-Search tool can be found in the Tool Output tab. The Visual Output tab gives a visual representation of the results, which helps identify which region in both your query sequence and the database sequence (subject) is aligning. The Functional Predictions tab scans all the database sequence results for hits against the InterPro collection of motif and families databases, as well as showing the region of alignment. Finally, the PSSM file is also output from any iteration where one has been generated.

#### How do I download the results?
There are several downloads that are possible from PSI-Search. The simplest download is probably the Tool Output which can be downloaded as a text or XML file containing the hits and scores. From the Summary Table it is possible to download a file containing the sequence entries (only) that have been selected from the results using the download button. Buttons from the tabs with images can be used to download either a scalable vector graphics format file, or you can right click on any image to save it as a PNG format file.

#### How can I view my results after I've downloaded them?
Alignments/output saved as a text file can be opened in most text viewing/processing programs. XML output can be viewed in most browsers or imported into spreadsheet programs. PNG files can be viewed by image viewers or web browsers. SVG files might require more advanced image editors to view.

#### Why don't I get a PSSM after the first run of PSI-Search?
The first run of PSI-Search is just like running a SSEARCH - you need this initial run in order to select the results from which the PSSM will be built. The next run is the first iteration that uses a PSSM and the Summary Table tab from those results will include a link to the PSSM file that was used to generate them.

#### How do I build a PSSM/select sequences to be used for my next iteration?
To select sequences to be included in building the PSSM use the selection tools in the Summary Table tab. By default all results with an Expect score lower than the threshold will be selected, but you can manually modify this. Once you have selected the sequences click the "Run next iteration" button to build a PSSM from those selected sequences and to run PSI-Search with that PSSM.

#### How do the fixed scale/dynamic scale options work in the visual results?
Fixed scale produces a bar with an Expect score from 0 to 100. Dynamic sets the left most of the bar to the smallest Expect score seen in the results, to the right most of the largest Expect score seen.

#### How long are results stored at EMBL-EBI?
Results are stored at EMBL-EBI for a week from the date of job submission.

#### What do the alignment symbols mean?
The exact format depends on the format selected on the input form, but by default:

`:` (colon) represents an identical match
`.` (period) represents a similar match (BLOSUM50 value greater than or equal to 0) 
`- `(hyphen) represents a gap in the sequence 
`X` represents part of the sequence that was filtered for low complexity.

#### Why do I get a 'Raw Tool Output' page?
This happens when we can't parse the results of your PSI-Search job - usually because the job has failed for some reason. Have a look at the links on the page, especially the Tool Error Details, for clues as to why this might have happened, and check your input for errors.

#### Why do I get a 'Job not found' page?
This happens when we can't find the job that you have requested. Normally it's a result of trying to look at the page over a week after the job was submitted, so the data is no longer available at the EMBL-EBI. If you've copied the URL from a recent email job, check for any mistakes in the link.