Unix Commands for Accessing Files

The "more" command allows viewing file content one page or line at a time, useful for large files.
The "less" command provides similar functionality but also allows backward navigation through the file.
Structure and Content of Genomic Files

Genome files are in FASTA format, with sequences identified by headers starting with ">" followed by sequence lines.
Multi-FASTA files contain multiple sequences, each with its own header and nucleotide string.
Exploring Gene and Sample Files

Gene annotation files contain columns detailing gene names, variants, chromosome locations, and gene structure.
Sample files list the portions of the organism sampled in experiments, such as root, leaf, and fruit.
The same commands ("more" and "less") can be used to view these different file types across directories for various species.

------------------------------------------
Commands for Viewing File Content
------------------------------------------

The command head displays the top lines of a file, defaulting to 10 lines, but can be adjusted with options like -50 to show the first 50 lines.
The command tail shows the last lines of a file, also defaulting to 10 lines, with options such as -15 to display the last 15 lines.
Using cat for File Content

The cat command (short for concatenate) can display the entire content of a file or combine multiple files into one continuous output.
When used on large files, cat outputs everything at once, which may require capturing the output for easier viewing later.
File Examples in Genomic Data

Example files include peach.genome, peach.genes, and peach.samples, containing genomic sequences and gene variant information.
These commands help explore specific parts of large genomic data files efficiently without loading the entire file at once.

------------------------------------------
Standard Input and Output in Unix
------------------------------------------

Unix commands like cat and wc read input from files or the command line and display output to the terminal.
There are three standard files: standard input, standard output, and standard error, which handle data flow in Unix.
Redirecting Input and Output

The greater than sign (>) redirects command output from the terminal to a file.
The less than sign (<) redirects input from a file to a command instead of the terminal.
Using Pipes to Connect Commands

The pipe symbol (|) takes the output of one command and uses it as the input for another command.
For example, piping ls output to wc -l counts the number of items, and piping cat output to more allows viewing large files one page at a time.

Comparing Files with diff

The diff command compares two files line by line and reports differences, including the location and type of changes.
It shows which lines were added, deleted, or changed, helping to identify modifications between file versions.

Analyzing Genome Structure

The genome file contains chromosome sequences in FASTA format, where each chromosome is identified by a header line starting with a ">" symbol.
Counting chromosomes can be done by counting these header lines using commands like grep with the -c option or piping grep output to wc -l.
Gene and Variant Analysis

Gene and variant information is stored in a file with gene names in the first column and variant names in the second.
Counting unique genes involves extracting the first column and using commands like uniq or sort -u, followed by wc -l to get the count.
Similarly, counting variants involves extracting the second column and applying the same unique counting methods.
Determining Variant Distribution per Gene

To find how many genes have a single variant versus multiple variants, the file is processed to count occurrences of each gene name.
Using uniq -c shows the number of variants per gene.
Filtering results with grep can separate genes with one variant from those with multiple variants, allowing quantification of each group.
Using comm to Compare Sorted Files

The comm command compares two sorted files and outputs lines unique to each file and lines common to both.
Files must be sorted for comm to work correctly; sorting can be done using the sort command.
Options with comm allow filtering to show only lines unique to one file or common to both, aiding in detailed comparisons.
