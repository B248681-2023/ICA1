# ICA1
**Add "eval" to master_script.sh at start of ~ line 158, on the "bedtools" call.**
Bedtools does not accept file names as comma separated files in a string. It previously worked, I don't know what changed.
Ideally we would re-write the code and temporarily move each bam file into a group directory, use wildcards with bedtools to read the files in that directory, and then move the files back to their original location.
