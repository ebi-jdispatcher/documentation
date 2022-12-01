
## RADAR FAQs

#### What is RADAR?
RADAR - Rapid Automatic Detection and Alignment of Repeats in protein sequences - is a tool to identify short composition biased and gapped approximate repeats, as well as complex repeat architectures involving many different types of repeats in a query sequence.

#### Why is RADAR useful?
RADAR is useful because many large proteins have evolved by internal duplication and many internal sequence repeats correspond to functional and structural units.

#### What version of RADAR is run at the EBI website?
For the precise version number of RADAR being run please go to the submission details tab from your job results.

#### How do I reference use of RADAR at the EBI website?
Please cite use of RADAR with the following:

Rapid automatic detection and alignment of repeats in protein sequences. (2000)Heger A. and Holm L.Proteins 41(2): 224-237. [doi: 10.1002/1097-0134(20001101)41:2<224::AID-PROT70>3.0.CO;2-Z](http://dx.doi.org/10.1002/1097-0134(20001101)41:2%3C224::AID-PROT70%3E3.0.CO;2-Z) 

A new bioinformatics analysis tools framework at EMBL-EBI (2010)Goujon M, McWilliam H, Li W, Valentin F, Squizzato S, Paern J, Lopez RNucleic acids research 2010 Jul, 38 Suppl: W695-9 [doi: 10.1093/nar/gkq313](http://dx.doi.org/10.1093/nar/gkq313)


#### What input does RADAR accept?
The program accepts a single protein sequence in a recognised sequence format. The full list of sequence formats accepted as input is given in this table: [EMBOSS sequence formats](http://emboss.open-bio.org/html/use/ch05s02.html#d0e5958)

The sequence can either be pasted into the web form or uploaded to the web form in a file.

#### Is there a limit on the number of sequences or the size of the file that I submit to RADAR?
The input for RADAR is limited to 1 sequence or to a 10KB file (whichever is smaller). For batch runs of RADAR see our [programmatic access](https://ebi-jdispatcher.github.io/documentation/webservices/) or use the stand-alone version of RADAR.

#### Where can I find information on the different parameters/options?
There are no user configurable parameters for RADAR.

#### What output does RADAR produce?
RADAR returns a set of multiple alignments corresponding to different types of repeats found in the protein sequence. Summary information about the repeat can be found at the top of each multiple alignment:

No. of Repeats: the number of repeat units in this repeat. This corresponds to the number of lines in the multiple alignment.
Total Score: the total score of all repeat units in the multiple alignment. For the calculation of this score, a profile is calculated for the repeat and every repeat unit is scored against the profile. The total score is the sum of the individual scores.
Length: the (estimated) length of one repeat unit.
Diagonal: the offset of the suboptimal alignment used for calculating the template repeat unit. The diagonal is usually roughly equal to the length of the repeat, but doesn't necessarily have to be so. For example in non-contiguous repeats, the repeat length is shorter than the offset of two repeats (i.e. the diagonal).
BW-From: the first residue of the template repeat unit.
BW-To: the last residue of the template repeat unit.
Multiple alignment information:

from-to: (Score/Z-Score) alignment.
from/to: numbers of the first/last residue.
Score: the score of this repeat unit, when scored against the profile of the whole repeat.
Z-Score: number of standard-deviations of the score above the mean for shuffled sequences scored against the same profile.

#### How do I download the outputs?
The output as text can be downloaded by clicking the view/download button in the Summary tab. Colours will not be preserved in the text file, but some browsers will preserve them if you copy/paste the text from the website.

#### How long are results stored at the EBI?
Results are stored at the EBI for a week from the date of job submission.

#### What do the colours mean?
The residues are coloured according to their physicochemical properties:

| Residue       | Colour                               | Property                                        |                    
| -----------   | ----------------------------         | -----------      |
| `AVFPMILW`    | <font color=red>RED</font>           | `Small (small+ hydrophobic (incl.aromatic -Y))`   |
| `DE`          | <font color=blue>BLUE</font>         | `Acidic`   |
| `RK`          |  <font color=magenta>MAGENTA</font>  | `Basic - H` |
| `STYHCNGQ`    | <font color=green>GREEN</font>       | `Hydroxyl + sulfhydryl + amine + G` |
| `Others`      | <font color=gray>GRAY</font>         | `Unusual amino/imino acids etc` |

#### Why do I get a 'Raw Tool Output' page?
This happens when we can't parse the results of your RADAR job - usually because the job has failed for some reason. Have a look at the links on the page, especially the Tool Error Details, for clues as to why this might have happened, and check your input for errors.

#### Why do I get a 'Job not found' page?
This happens when we can't find the job that you have requested. Normally it's a result of trying to look at the page over a week after the job was submitted, so the data is no longer available at the EBI. If you've copied the URL from a recent email job, check for any mistakes in the link.