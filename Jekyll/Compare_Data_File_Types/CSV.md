## What is the CSV
**CSV (Comma-Separated Values)** is a delimited text file that uses a **comma** to separate values.

| Artist | Title | Released Date | Preferred |
| - | - | - | - |
| Borgeous | Breathe | Aug, 26 2014 | |
| Borgeous & David Solano | Big Bang | Apr, 15 2015 | yes |
| DVBBS & Jay Hardway | Voodoo | Mar, 3 2015 | yes |
| Martin Garrix ("Don Diablo" Remix) | Ocean | Aug, 11 2018 | yes |

The above data could be represented in a CSV-formatted file as follows:
```
Artist, Title, Released Date, Preferred
Borgeous, Breathe, "Aug, 26 2014", 
Borgeous & David Solano, Big Bang, "Apr 15, 2015", yes
DVBBS & Jay Hardway, Voodoo, "Mar 3, 2015", yes
Martin Garrix (""Don Diablo"" Remix), Ocean, "Aug 11, 2018", yes
```
- To separate data, use **comma (,)**
- If there is no datum inside the table, leave it empty
- If you want to use comma in the string, wrap it with the **double-quote sign (")**
- To use **double-quote sign (")**, use the sign twice

1. Each record (row of data) is to be located on a separate line, delimited by a line break. For example:
```
aaa,bbb,ccc CRLF
```

2. The last record in the file may or may not have an ending line break. For example:
```
aaa,bbb,ccc CRLF
   zzz,yyy,xxx
```

3. There may be an optional header line appearing as the first line of the file with the same format as normal record lines. The header will contain names corresponding to the fields in the file and should contain the same number of fields as the records in the rest of the file. For example:
```
field_name,field_name,field_name CRLF
   aaa,bbb,ccc CRLF
   zzz,yyy,xxx CRLF
```

4. In the header and each record, there may be one or more fields, separated by commas. Each line should contain the same number of fields throughout the file. Spaces are considered part of a field and should not be ignored. The last field in the record must not be followed by a comma. For example:
```
aaa,bbb,ccc
```

5. Each field may or may not be enclosed in double quotes. If fields are not enclosed with double quotes, then double quotes may not appear inside the fields. For example:
```
"aaa","bbb","ccc" CRLF
   zzz,yyy,xxx
```

6. Fields containing line breaks (CRLF), double quotes, and commas should be enclosed in double quotes. For example:
```
"aaa","b CRLF
   bb","ccc" CRLF
   zzz,yyy,xxx
```
7. If double quotes are used to enclose fields, then a double quote appearing inside a field must be escaped by preceding it with another double quote. For example:
```
"aaa","b""bb","ccc"
```
