There are two files and one directory in this directory, including README.txt, genome.fa.gz and test2_correct_output. The genome.fa.gz file contains the example diploid genome sequences.

Let us test if the essential part of HM2 works correctly in your system (test2).
1.	Copy run_all.batch, hm.batchA/B/D*, all_lastz.ctl and scoreMatrix.q from ./project_template to ./project_example2.
2.	Switch to the directory ./project_example2, and make sure that you set $PATH correctly so that all HM2 executables can be accessed.
3.	This time, we use the master shell script to do the test. Open, modify and save run_all.batch: 
    (a) set the $PATH correctly in line 13;
    (b) by adding a "#" to the beginning of the corresponding command lines, you should comment out all other shell scripts except hm.batchA/B/D*; 
    (c) replace "your_assembly_name" with "genome" in line 22-24; 
    (d) replace "your_assembly_name_A" with "genome_A" in line 33-37;
    (e) replace "your_assembly_name_A_ref_C" with "genome_A_ref" in line 55-57.
4.	Return to the terminal and run:
$ sh ./run_all.batch >run_all.log 2>&1   # # collect all screen output to run_all.log
    You can also run each script of hm.batchA/B/D* step by step to see how it is working.
5.	Each script will finished in seconds and you will see each script outputs certain directories, files and logs in the current directory. You are supposed to get these final results:
from hm.batchA1-3
./genome_A.fa.gz      ## the diploid assembly with misjoins removed
from hm.batchB1-5
./genome_A_ref.fa.gz   ## the reference haploid assembly
./genome_A_alt.fa.gz   ## the alternative haploid assembly
from hm.batchD1-3
./genome_A_ref_D.fa.gz  ## the reference assembly with tandems removed
6.	You may compare you outputs with those in test2_correct_output for trouble shooting.


####
# cp ../project_template/hm.batchB* ./ ; cp ../project_template/hm.batchA* ./ ; cp ../project_template/hm.batchD* ./ ; cp ../project_template/all_lastz.ctl ./ ; cp ../project_template/scoreMatrix.q ./ ; cp ../project_template/run_all.batch ./ 
