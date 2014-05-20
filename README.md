useful-awk-scripts
==================

Useful Awk scripts and one liners that I've come up with.

CSV
---

Fix a comma-delimited CSV that contains split rows.  Replace `17` in `fcount = 17` with the number of fields that your CSV has:

`awk -F, 'BEGIN { fcount = 17; pnf = fcount; } NF != fcount { if(pnf == fcount) {pln = $0; pnf = NF;} else {print pln $0; pnf = fcount;} } NF == fcount { print $0 }'`

Phone numbers
-------------

For a column of strings that end with an asterisk, generate 10 strings that replace the asterisk with the digits 0-9 (e.g., 123456789* becomes 1234567890, 1234567891, 1234567892, etc.):

`awk '{ sub(/\*/, ""); for(i = 0; i <= 9; i++) print $0 i; }'`
