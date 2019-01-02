This test use a real diploid genome assembly, please finish the first two tests before running test3.
You are recommend to use run_all.batch in this test.
Switch to the directory ./project_example3, 
and make sure that you set $PATH in run_all.batch correctly so that all HM2 executables can be accessed.

For result evaluation and trouble shooting,
you may not want to run all scripts at a time,
so you may comment out the scripts in run_all.batch.

This test allow you to thest from hm.batchA to E.

To begin the test, you need to know the following information.

####
#### diploid genome assmebly
Please download bbv18wm.fa.gz on this website and put it in the directory project_example3. 
  https://github.com/mapleforest/HaploMerger2/releases/tag/HaploMerger2_20161129/
  https://github.com/mapleforest/HaploMerger2/releases/download/HaploMerger2_20161129/bbv18wm.fa.gz

bbv18wm is a diploid genome assembly 
created by CABOG v6.1, with ~40x read data, Illumina 150PE, and 2kb/3kb/8kb mate-pairs.
For more information of this assembly, please see https://www.ncbi.nlm.nih.gov/assembly/GCA_001625405.1/ .
TotalScaffolds=10354
TotalBasesInScaffolds=697399180
TotalSpanOfScaffolds=707122162
N25ScaffoldBases=478784
N50ScaffoldBases=264466
N75ScaffoldBases=128963
TotalContigsInScaffolds=49397
N25ContigBases=56197
N50ContigBases=30004
N75ContigBases=14704

####
#### mate-pair libaries for re-scaffolding
To run hm.batchC you should download the 2/3/8/20 kb mate-pair reads libaries from
and put them in the directory project_example3/libraries:
  https://github.com/mapleforest/HaploMerger2/releases/tag/HaploMerger2_20161129/
  https://github.com/mapleforest/HaploMerger2/releases/download/HaploMerger2_20161129/scaffolding_libaries.tar.gz

OR, you could download them from the NCBI SRA database:
Accession SRX1421071:
Store reads of run 2kb_libraries_pair1 as a gzipped Fasta file named pe2kb40bp.1.fa.gz.
Store reads of run 2kb_libraries_pair2 as a gzipped Fasta file named pe2kb40bp.2.fa.gz.
Note that SSPACE does not care about the read name; only the read order matters.
Accession SRX1421072:
Store reads of run 3kb_libraries_pair1 as a gzipped Fasta file named pe3kb40bp.1.fa.gz.
Store reads of run 3kb_libraries_pair2 as a gzipped Fasta file named pe3kb40bp.2.fa.gz.
Note that SSPACE does not care about the read name; only the read order matters.
Accession SRX1421073:
Store reads of run 8kb_libraries_pair1 as a gzipped Fasta file named pe8kb40bp.1.fa.gz.
Store reads of run 8kb_libraries_pair2 as a gzipped Fasta file named pe8kb40bp.2.fa.gz.
Note that SSPACE does not care about the read name; only the read order matters.
Accession SRX1421071:
Store reads of run 20kb_libraries_pair1 as a gzipped Fasta file named pe20kb40bp.1.fa.gz.
Store reads of run 20kb_libraries_pair2 as a gzipped Fasta file named pe20kb40bp.2.fa.gz.
Note that SSPACE does not care about the read name; only the read order matters.

####
#### paired-end libraries for Gap filling 
To run hm.batchE you should download the reads libaries
from the NCBI SRA database and put them in the directory project_example3/libraries.
Accession SRX1364942:
Please separate read#0 and read#1 into two gzipped Fastq file named 5_1/2.cor.fq.gz.
Accession SRX1364943:
Please separate read#0 and read#1 into two gzipped Fastq file named 7_1/2.cor.fq.gz.

####
#### IMPORTANT NOTES
Note 1: The example 3 is ran and tested on a 24-core machine with 64Gb memory.
Note 2: GapCloser require 32Gb memory on this project.
Note 3: If everything goes smoothly, the whole run takes less than 4 hours to finish. 

Note 4: To save time, I tweek these parameters/options:
1. threads are set to 16 or 20 in hm.batchA1, hm.batchA2, hm.batchB1, hm.batchB2, hm.batchB4, 
    hm.batchC1, hm.batchD1, hm.batchD2 and hm.batchE1,  
    so, if your machine does not have that many cpu cores, please reduce the thread number;
2. the "--step" in all_lastz.ctl is set to 20;
3. only one round is scheduled for running for hm.batchA, hm.batchC and hm.batchD;
4. "minimumLinks" in hm.batchC1 is set to 3;
5. "minLen" in hm.batchD3 is set to 4000bp;
6. in hm.batchB5, "including_unpaired" is set to 0 in order not to include 
   unpaired_refined.fa.gz in the final assembly.
   
####
#### Comparison with the correct output
The correct output is placed in the directory test3_correct_output.
Because many result files are too large to include,
I just list them in the file named "_0_Result_files_list_and_sizes.txt".
You result files (especially *.fa.gz) should have the same sizes as shown in this file.   
