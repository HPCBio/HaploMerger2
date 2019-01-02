There are two files and one directory in this directory, including README.txt, genome.fa.gz and test1/2_correct_output. The genome.fa.gz file contains the example diploid genome sequences.

Let us test if the essential part of HM2 works correctly in your system (test1).
1.	Copy hm.batchB1-5, all_lastz.ctl and scoreMatrix.q from ./project_template to ./project_example1.
2.	Switch to the directory ./project_example1, and make sure that you set $PATH correctly so that all HM2 executables can be accessed.
3.	Use genome.fa.gz as the input file (no need to type the suffix ¡°fa.gz¡±) and run the following shell scripts step by step while observing the information on the monitor:
$ sh ./hm.batchB1.initiation_and_all_lastz   genome
$ sh ./hm.batchB2.chainNet_and_netToMaf   genome
$ sh ./hm.batchB3.haplomerger   genome
$ sh ./hm.batchB4.refine_unpaired_sequences   genome
$ sh ./hm.batchB5.merge_paired_and_unpaired_sequences   genome
4.	Each script will finished in seconds and you will see each script outputs certain directories, files and logs in the current directory.
5.	After hm.batchB5 is done, you are supposed to get two final result files named ./genome_ref.fa.gz and ./genome_alt.fa.gz with four scaffold sequences in each of them.
6.	You may also compare your outputs with those in test1_correct_output for trouble shooting.

####
# cp ../project_template/hm.batchB* ./ ; cp ../project_template/all_lastz.ctl ./ ; cp ../project_template/scoreMatrix.q ./

