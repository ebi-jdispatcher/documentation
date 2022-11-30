# FAQs

!!! warning

    This page is under development.

#### How many sequences can I align at once?
Each tool has its own limit, please refer to the relevant webform page for individual tools.
The EBI service has limits and therefore a smaller number of very long sequences will often stop before an 
alignment is completed. 
Our tool algorithms are NOT intended to produce genome synteny maps.

#### What input formats can I use?
Each tool has different requirements, however GCG, FASTA, EMBL (Nucleotide only), 
GenBank, PIR, NBRF, PHYLIP or UniProtKB/Swiss-Prot (Protein only) formats can be used in the majority of tools. 
Please refer to the individual tool input pages.
Incorrect input format is one of the most common reasons for job failure.

#### How do I download an alignment?
The quickest way to download the alignment is to click the 
'Download Alignment File' button in the alignments tab of the results. 
You can view all the files that are produced on the 'Results Summary' tab, 
which includes the tool output and any guide tree files as well as the alignment file.

#### How do I save a coloured alignment?
There are several ways in which to save your colour file.

1. Most obvious is to screenshot the alignment from the output and print to pdf or save as a high res image.
2. Once you have your results, select result summary and if your browser allows the link to Jalview, 
you can use this tool to present many colour formats and save as pdf, png, etc. 
If your browser does not allow the link you can go to the Jalview website and use the tool from there.
3. The EMBOSS suite of tools includes Prettyplot which can be used to download, colour and save alignments 
to either pdf or png. We do not host this service at the EBI and are unable to provide user support for this.
4. For more colouring options you could choose to run Mview

#### How can I view a phylogenetic tree?
The tree data can be saved by clicking the 'View Phylogetic Tree file' button or by clicking the tree link in the Results Summary tab. Using this data you can recreate the tree in any tree viewing software that takes Newick format tree data.

The tree image cannot be saved directly as it is a dynamic java-driven interface, however you can take a screenshot and then save this in an image editing program, or as mentioned above use the tree data to recreate the tree in another tree viewing program and save it from there. 

#### How can I view my tree after I've downloaded it?
The tree data is in the widely used Newick format, there are several online or standalone tree viewing programs available that can take this and recreate the tree from this data. 

#### What is a subsitution matrix?
A substitution matrix describes the rate at which one character in a sequence changes to other character states over time, see [more](https://en.wikipedia.org/wiki/Substitution_matrix) 

#### What is a distance matrix?
Distance matrices are used in phylogeny as [non-parametric](https://en.wikipedia.org/wiki/Non-parametric) distance methods and were originally applied to [phenetic](https://en.wikipedia.org/wiki/Phenetic) data using a matrix of pairwise distances. These distances are then reconciled to produce a tree (a [phylogram](https://en.wikipedia.org/wiki/Phylogram), with informative branch lengths). [See more](https://en.wikipedia.org/wiki/Distance_matrices_in_phylogeny).

#### Which distance/substitution matrix should I use?
There are several distance matrices that can be used (selected) when performing sequence search or sequence alignment. The most widely used distance (substitution) matrix is BLOSUM62, but PAM matrices are also popular. The following publication describes in depth what are the factors one should consider when choosing a substitution matrix:

Pearson WR. Selecting the Right Similarity-Scoring Matrix. Current protocols in bioinformatics. [2013;43:3.5.1-3.5.9. doi:10.1002/0471250953.bi0305s43](http://europepmc.org/articles/PMC3848038).

#### What does percentage identity refer to?
The percent identity value is a single numeric score determined for each pair of aligned sequences. It measures the number of identical residues (“matches”) in relation to the length of the alignment. As displayed in the matrix (PIM), real numbers show 2 decimal points. The number shows the % of difference between two sequences (although this might differ between different tree viewers). A score of 0.01 means that there is a difference of 1% between two sequences.

Please note that different alignment programs might calculate and report sequence percentage identity in different ways. Typically the program developer/researcher had a particular view on how to treat gaps and other regions of the multiple sequence alignments. [This publication](https://europepmc.org/abstract/MED/16984632) by Raghava and Barton, 2006 tries to discuss how this might be an issue when interpreting PIM results.

#### What are the meaning of the scores shown in a phylogenetic tree?
The scores shown in a phylogenetic tree (or dendrogram) produced as the output of a Multiple Sequence Alignment (MSA), correspond to a sequence distance measure. In a way, the values shown in the phylogenetic tree (also) try to represent the "length" of the branches, which is indicative of the evolutionary distance between the sequences.

Generally speaking, the way most MSA algorithms work is that each pair of input sequences is aligned, and used to compute the pairwise identity of the pair. During the construction of the tree, the algorithm takes the aligned sequences and builds a sequence distance matrix that is then used to arrive at an "optimal" tree by a clustering method, typically Neighbour-Joining (NJ) or UPGMA (Unweighted Pair Group Method with Arithmetic Mean). Sequence identities are converted to a measure of distance. Finally, the distance matrix is converted to a tree using a clustering method (NJ or UPGMA). After progressive alignment and from the final multiple alignment, pairwise identities of each pair of sequences are computed again. This produces a new distance matrix, from which a new tree is estimated. The clustering algorithm used is often Neighbour-joining, and this is the tree which is provided as the output. The reliability of the clustering performed is tested statistically by a process called bootstrap, whereby the clustering is performed 100's or 1000's times, returning a measure of confidence.

#### What do the colours represent in protein alignments?
| Residue       | Colour                               | Property                                        |                    
| -----------   | ----------------------------         | -----------      |
| `AVFPMILW`    | <font color=red>RED</font>           | `Small (small+ hydrophobic (incl.aromatic -Y))`   |
| `DE`          | <font color=blue>BLUE</font>         | `Acidic`   |
| `RK`          |  <font color=magenta>MAGENTA</font>  | `Basic - H` |
| `STYHCNGQ`    | <font color=green>GREEN</font>       | `Hydroxyl + sulfhydryl + amine + G` |
| `Others`      | <font color=gray>GRAY</font>         | `Unusual amino/imino acids etc` |

#### What do consensus symbols represent in a Multiple Sequence Alignment?
An * (asterisk) indicates positions which have a single, fully conserved residue. 

A : (colon) indicates conservation between groups of strongly similar properties as below - roughly equivalent to scoring > 0.5 in the Gonnet PAM 250 matrix:

`STA`
`NEQK`
`NHQK`
`NDEQ`
`QHRK`
`MILV`
`MILF`
`HY`
`FYW` 

A . (period) indicates conservation between groups of weakly similar properties as below - roughly equivalent to scoring =< 0.5 and > 0 in the Gonnet PAM 250 matrix: 

`CSA`
`ATV`
`SAG`
`STNK`
`STPA`
`SGND`
`SNDEQK`
`NDEQHK`
`NEQHRK`
`FVLIM`
`HFY`

Note that TV is included in the weaker scoring groups despite scoring 0.0 in the PAM 250 matrix, this is because it is a fairly common substitution as they are both beta-branched. In fully buried residues that is at the cost of a hydrogen bond. In fact, being relatively gentle, this substitution has been used in the past to make TS mutants. (Information courtesy of Toby Gibson).

The same symbols display for DNA/RNA alignments, so while * (asterisk) characters are still useful, the other characters should be ignored for DNA/RNA alignments. 

#### What do consensus symbols represent in a Pairwise Alignment?
Pairwise sequence alignments are generated by tools such as EMBOSS Needle, Water, Stretcher and Matcher. The alignment markup highlights where the sequences mismatched, gapped, identical or similar. 

In general the markup line uses a space for a mismatch or a gap, '.' for any small positive score, ':' for a similarity which scores more than 1.0, and '|' for an identity where both sequences have the same residue regardless of its score ('W' matching 'W' scores much more than 'L' matching 'L' because a conserved tryptophan is more significant than a conserved leucine).

The 'markx' set of alignment formats (produced by the FASTA suite of programs written by Bill Pearson) use '.' for similarity and ':' for an identity. The '|' character is not used. This was a design decision by Bill Pearson when he wrote the FASTA programs.

A detailed overview of the different formats is provided in the EMBOSS documentation, which is available [here](http://emboss.sourceforge.net/docs/themes/AlignFormats.html)

#### What do upper and lower case letters represent in consensus results?
Lower case characters are used for unaligned residues. More information is available in this [publication](http://onlinelibrary.wiley.com/doi/10.1002/1097-0134(20001101)41:2%3C224::AID-PROT70%3E3.0.CO;2-Z/fullhttp://onlinelibrary.wiley.com/doi/10.1002/1097-0134(20001101)41:2%3C224::AID-PROT70%3E3.0.CO;2-Z/full). 

#### How can I view my resulting multiple sequence alignment (MSA) with Jalview?
[Jalview](http://www.jalview.org/) is a free program for multiple sequence alignment editing, visualisation and analysis. Jalview has been developed in the Barton Group at the University of Dundee, and can be used to view and edit sequence alignments, analyse them with phylogenetic trees and principal components analysis (PCA) plots and explore molecular structures and annotation.

To launch Jalview from the Multiple Sequence Alignment result page, click on the Jalview Logo provided in the "Result Viewers" tab of the results pages. A file named "lauchJalview.jvl" will be downloaded automatically. In order to open the downloaded application you need to either install an installer available [here](http://www.jalview.org/getdown/release/) and this will load your MSA results or launch Jalview manually.

Citing Jalview: 

`Waterhouse A.M., Procter J.B., Martin D.M.A., Clamp M., Barton G.J. (2009)
Jalview Version 2-a multiple sequence alignment editor and analysis workbench.
Bioinformatics 25: 1189-1191. Pubmed: 19151095 DOI: doi:10.1093/bioinformatics/btp033 `

#### What do gap penalties (Gap Opening, Gap Extension, etc.) correspond to?
Gap penalties generally refer to the penalty that is subtracted from the alignment score that is computed during the sequence alignment set as performed by multiple sequence alignment (MSA) and pairwise sequence alignment (PSA) programs. For example, Clustal Omega defines Gap Opening Penalty has the penalty for opening a gap in the alignment, which makes the gaps less frequent for increasing gap opening values. Gap Extension Penalty corresponds to the penalty for extending a gap by one residue. Increasing this value will make the gaps shorter. There are some MSA programs that also define Terminal Gap penalties (example [Kalign](https://www.ebi.ac.uk/Tools/msa/kalign/)), which correspond to the penalty of adding additional gaps at the C- or N-terminus of the sequences. Each tool has its own Gap penalty implementation and thresholds, please refer to the relevant [webform](https://www.ebi.ac.uk/services) or [webservices](https://www.ebi.ac.uk/seqdb/confluence/display/JDSAT/Job+Dispatcher+Sequence+Analysis+Tools+Home) page for individual tools.

#### What is the difference between Global Alignment and Local Alignment Tools?
Global alignment alignment tools create an end-to-end alignment of the sequences to be aligned, whereas, local alignment tools find one, or more, alignments describing the most similar region(s) within the sequences to be aligned. 

#### What is the maximum input file size for MSA ?
| Tool            | Sequence Limit                                |             
| -----------     | ----------------------------                  | 
| `Clustal Omega` | `4000 sequences and 4MB of data`                | 
| `Kalign`        | `2000 sequences and 2MB of data>`               | 
| `MAFFT`         |  `500 sequences or a maximum file size of 1 MB` | 
| `MUSCLE`        | `500 sequences and 1MB of data`                | 
| `MView`         |`2MB of data`                                   | 
| `T-Coffee`      | `500 sequences or a maximum file size of 1 MB`  | 




