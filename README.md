# awk scripts for DRS deposit reports

### awk scripts for image-only deposit reports

    # following returns URN links only
    awk '/JP2/ {print "http://nrs.harvard.edu/"$11}' Fabien_B6167982090676897383.txt

    # following returns OSN [tab] URN link
    awk '/JP2/ {print $5"\thttp://nrs.harvard.edu/"$11}' Fabien_B6167982090676897383.txt

    * Note: improve by adding -F '\t' flag to awk so that only tabs are regarded as column seperators.

### awk scripts for PDS deposit reports
    # -F "\t" makes explicit that TAB is the column seperator and /xml/ only returns values for rows with XML (assume METS) files.
    awk -F "\t" '/xml/ {print "\thttp://nrs.harvard.edu/"$2}' Batch052365047367421786808.txt
    
## DRS deposit confirmation report structure

|column #   |heading   | 
|---|---|
| 1  | OBJ-ID  |
| **2**  | **OBJ-DELIV-URN**  |
| 3  | OBJ-URN  |
| 4  | DEPOSITOR  |
| 5  | OBJ-OSN  |
| 6  | BILLING  |
| 7  | OWNER  |
| 8  | OBJ-TYPE  |
| 9  | OBJ-ROLES  |
| 10  | FILE-ID  |
| **11**  | **FILE-URN**  |
| 12  | FILE-FORMAT |
| 13  | FILE-SIZE  |
| 14  | FILE-FORMAT  |
| 15  | FILE-ORIGPATH  |

## Searching DRS via CVS upload
Each column heading must be one or more of the following: (not tested)

* file_id_num
* file_huldrsadmin_ownerSuppliedName_string
* file_huldrsadmin_uri_string_sort

