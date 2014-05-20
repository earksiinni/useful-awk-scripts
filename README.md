useful-awk-scripts
==================

Useful Awk scripts and one liners.

Phone numbers
-------------

For a column of strings that end with an asterisk, generate 10 strings that replace the asterisk with the digits 0-9 (e.g., 123456789* becomes 1234567890, 1234567891, 1234567892, etc.):

`awk '{ sub(/\*/, ""); for(i = 0; i <= 9; i++) print $0 i; }' filename`
