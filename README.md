# Kc-Align

Kc-Algin is a codon-aware multiple aligner that uses Kalgin2 to produce in-frame gapped codon alignments for selection analysis of small genomes (mostly viral and some smaller bacterial genomes). Takes nucleotide seqeunces as inputs, converts them to their in-frame amino acid sequences, performs multiple alignment with Kalign, and then converts the alignments back to their original codon sequence while preserving the gaps. Produces two outputs: the gapped nucleotide alignments in FASTA format and in CLUSTAL format.

# Modes

Kc-Align can be run in three different modes, depending on your input data. 

In "genome" mode, the "reference" and "reads" input parameters are all full genome FASTA files. This mode also requires the 1-based start and end position numbers corresponding to the gene you are interested in aligning from the reference input.

If both the "reference" and "reads" inputs are already in-frame genes, the "gene" mode should be used. This mode does not require start and end position parameters as the reference is already in-frame.

For the case when your "reference" is an in-frame gene while the "reads" are whole genomes, the "mixed" mode can be used. Like gene mode, this mode does not require the start and end point position parameters.

## USAGE:

kc-align --mode genome --reference [reference FASTA] --reads [reads FASTA] --start [start] --end [end]

kc-align --mode gene --reference [reference FASTA] --reads [reads FASTA]

kc-align --mode mixed --reference [reference FASTA] --reads [reads FASTA]