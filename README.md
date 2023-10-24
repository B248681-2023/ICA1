# ICA1
Fixing the script (purely for the convenience of the marker, not for more marks. Also to satisfy my own brain):
1. 
**Add "eval" to master_script.sh at start of line 158, on the "bedtools" call.**
Bedtools does not accept file names as comma separated files in a string. It previously worked, I don't know what changed.
Ideally we would re-write the code and temporarily move each bam file into a group directory, use wildcards with bedtools to read the files in that directory, and then move the files back to their original location.

2. 
**Change pathname on line 177 (the file touch) to:  group_coverage_comparisons/"$current_comparison_group"**
**Change both mentions of "coverage_comparisons"'s on line 196 to "group_coverage_comparisons"**
I renamed this variable last minute and missed some instances of the name
