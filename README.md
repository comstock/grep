# grep & awk scripts

## awk scripts for DRS deposit reports

### awk scripts for image-only deposit reports

    awk /xml/ {print "http://nrs.harvard.edu/"$2} Fabien_B6167982090676897383.txt

### awk scripts for PDS deposit reports

    awk /JP2/ {print "http://nrs.harvard.edu/"$2"\t"$5} Batch052365047367421786808.txt

