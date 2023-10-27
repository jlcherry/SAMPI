# SAMPI
Sequence sampling tool for phylogenetics

Usage: sampi.py [OPTIONS] [input_fname [output_fname]]

  OPTIONS
  
    -v,--verbose   Print a lot of information
    -s,--seed      With an integer, sets random number seed
    -c,--comment   With a string, sets comment in top of output fasta
    -h,--help      This help
    
SAMPI is a tool for choosing a subset of isolate sequences that maintains representation of categories of isolates that may be rare in the full set.  It does so by selecting at most a certain number of isolates from each category.  The user specifies the attributes that define a category and the maximum number of sequences to choose from each.  Attributes can be any character strings provided by the user.  Common choices include year of isolation, country, and clinical attributes.

The program optionally applies various criteria to determine which isolates to choose from a category.  Uniformity of isolation dates can be optimized, according to certain measures, within each category.  Isolate sequences can also be prioritized according to various desirable qualities: completeness of available isolation date information (year/month/date vs. year/month vs. year only), length (i.e., completeness) of the sequence, rarity of ambiguity characters in the sequence, and rarity of frameshift-causing gaps.  The user specifies which of these prefererences are applied and the order of their precedence.  Uniformity of dates, if applied, takes precedence over any other criteria.  Choices among sequences that are equivalent under the criteria are made at random, and hence will generally vary between otherwise identical runs, though a random number seed can be provided to assure reproducibility.
