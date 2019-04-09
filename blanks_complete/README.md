# Blanks

## Description
 Maybe it's not blank

 We have a file with tabs and spaces. Replacing tabs with 0 and spaces with 1 using sublime text we'll get a binary string.
 Unfortunately, there are some missing bits near the end, but we know that the last byte should be a }.
 Simply removing the last 6 bits and decoding binary to ascii we'll get the flag.

 `radar{blanks_but_not_blankz}`
