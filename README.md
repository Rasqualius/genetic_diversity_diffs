# genetic_diversity_diffs
Tests for significant differences in genetic diversity between populations based on DNA sequence data

#How it works#
This R script carries out a permutation procedure, reasmpling from the combined haplotype frequencies over all your populations, in order to test whether the observed differences in haplotype/nucleotide diversity between your populations are greater than expected by chance.

#Things to note#
1) This program "eats" arlequin files, that have a haplotype block at the top of the file. Check out the example data if you are unsure on this format.
2) You need to make sure the library stringr is loaded in to your R environment
3) The program will look for and consolidate any identical haplotypes
4) It counts indels as a state for the calculation of nucleotide diversity (so make sure sequences of different lengths are 'padded' by missing data, not dashes).
5) If there are haplotypes that do not reciprocally match (i.e. a haplotype with missing data can match to more than one other haplotype, and the haplotypes it matches to do not match to each other), the program will identify the haplotype with the largest amount of missing data. In most cases this will be the culprit, but a better idea is to make sure all of your haplotypes are unique before running this program.
6) Nucleotide diversity will differ slightly from arlequin if there is missing data, as genetic_diversity_diffs calculates the proportional difference between haplotypes only based on non-missing data, whereas arlequin averages the differences over the entire length of alignment to calculate proportional differences. 
7) Nucleotide diversity will also differ slightly between the programs if there are indels, because Arlequin only counts indels as part of the haplotype alignment length if they are variable within the population in question, and genetic_diversity_diffs counts them as part of the length if they are variable across all haplotype definitions (over all of your populations).

If arlequin can accept the file, and genetic_diversity_diffs can't, then email alana dot alexander at ku dot edu. If you are having trouble with arlequin, make sure your hyphens haven't been made into em-dashes by word.

#How to run it#
The easiest way for people less familiar with R, is to paste the entire function into R. You can then call the function by:

