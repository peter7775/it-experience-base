|                                     |     |
| ----------------------------------- | --- |
| BEGIN { statements }                |  statements are executed once before any input line has been read   |
| END { statements }                  |   statements are executed once after all input has been read  |
| expression { statements }           |  statements are executed at each input line where expresion is true   |
| /regular expression/ { statements } |   statements are executed at each input line that contains a string matched by the
regular expression  |
| compound pattern { statements }     |  a compound pattern combines expressions with && (AND), II (OR), I (NOT), and parentheses; the statements are executed at each input line where the compound pattern is true.  |
| pattern1, pattern2 { statements }   |   a range pattern matches each input line from a line matched by pattern 1 to the next line matched by pattern 2, inclusive; the statements are executed at each matching line  |