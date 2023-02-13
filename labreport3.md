# Lab Report 3
## Researching Commands
### **Additional options for the grep command:**

The *grep* command in bash is used for finding occurences of a string or pattern within a file or files, and will output all of the lines which contain that pattern. There are different ways to modify the behavior of the grep command, which are called options, and can be used in the command line for grep as follows: `grep -[option(s)] pattern [files]`

**For each of the following examples, the directory structure being used is as follows:**
```
written_2
    ├───non-fiction
    │   └───OUP
    │       ├───Abernathy
    │       ├───Berk
    │       ├───Castro
    │       ├───Fletcher
    │       ├───Kauffman
    │       └───Rybczynski
    └───travel_guides
        ├───berlitz1
        └───berlitz2
```

One of these options is the `-c` option, which will change the behavior of grep to only output the count of the number of lines which match the given pattern. The following are two examples using this option. 
```
$ grep -c "italy" written_2/travel_guides/berlitz1/HistoryItaly.txt 
0
```
* Here, the grep command is searching the HistoryItaly.txt file for lines that contain an occurence of "italy", which there are none and therefore output is 0.
```
$ grep -c "the" written_2/travel_guides/berlitz1/HistoryItaly.txt
420
```
* The grep command is searching the same text file, but this time for all occurences of the pattern "the", of which there are 420 in the file, therefore instead of grep displaying each line, only the count of the number of lines is displayed to the terminal.

This option can be useful for whenever you might want to JUST know the number of times something occurs in a file or files, and not necesarilly worried about the exact lines in which it occurs.

> (source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/)

Another grep command option is the `-r` option, which will modify grep to be able to recursively search through a directory, and grep will visit each file in the directory and sub-directories given to the command. It will then print the lines from the files in that directory which match the pattern. For example,
```
$ grep -r "Apple" written_2/
written_2/travel_guides/berlitz1/WhatToJamaica.txt:        of many tours — is Appleton Distillery, situated in rolling hills just
written_2/travel_guides/berlitz1/WhatToJamaica.txt:        local consumption. Appleton Distillery went one step further and
written_2/travel_guides/berlitz2/Bahamas-WhatToDo.txt:Rum. Bacardi and other Caribbean brands, like Appletons of Jamaica, and almost all international brands of liquor can be found at good prices. Look out for coconut rum and other fruit rums — there’s a tremendous variety.
```


Another option for the grep command is the `-l` option, which will only print the name or names of the files in which the pattern given to the command occurs. For example,
```
$ grep -l "" written_2/
```
