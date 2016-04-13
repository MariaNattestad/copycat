# Copycat

Copycat is a simple script to capture and bin the read coverage across a genome from a bam file of read alignments. 

It relies on bedtools to get coverage for each individual nucleotide in the genome using bedtools genomecov, then bins and organizes these coverage values into 10kb bins and outputs the coverage information in a .csv format (for upload to SplitThreader) and in a .seg format (for viewing the copy number profile in IGV)

Usage:
copycat alignments.sorted.bam genome_file output_prefix

- alignments.sorted.bam:
  - Bam file must be sorted.
  - Remember to filter for mapping quality first if desired: \n\tsamtools view -q -b BAM.bam > FILTERED_BAM.bam

- genome_file:
  - The genome file should be structured as chromosome_name<tab>chromosome_size\n\tFor example:\n\tchr1\t249250621\n\tchr2\t243199373

- output_prefix
  - Prefix for all output files. Output files will be output_prefix.coverage, output_prefix.coverage.10kb, output_prefix.coverage.10kb.csv, output_prefix.coverage.10kb.for_IGV.seg

