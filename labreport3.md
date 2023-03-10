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

> (source: [https://www.geeksforgeeks.org/grep-command-in-unixlinux/](https://www.geeksforgeeks.org/grep-command-in-unixlinux/))

Another grep command option is the `-r` option, which will modify grep to be able to recursively search through a directory, and grep will visit each file in the directory and sub-directories given to the command. It will then print the lines from the files in that directory which match the pattern. For example,
```
$ grep -r "Apple" written_2/
written_2/travel_guides/berlitz1/WhatToJamaica.txt:        of many tours — is Appleton Distillery, situated in rolling hills just
written_2/travel_guides/berlitz1/WhatToJamaica.txt:        local consumption. Appleton Distillery went one step further and
written_2/travel_guides/berlitz2/Bahamas-WhatToDo.txt:Rum. Bacardi and other Caribbean brands, like Appletons of Jamaica, and almost all international brands of liquor can be found at good prices. Look out for coconut rum and other fruit rums — there’s a tremendous variety.
```
* The command is being used to search the entire directory and subdirectory of the `written_2/` folder for occurences of `"Apple"`. Then, grep has printed each of the lines in the entire directory which contain that Pattern, in this case there are 2 files, and 3 lines containing text which matches the pattern.

```
$ grep -r -c "The" written_2/non-fiction/OUP/Castro/
written_2/non-fiction/OUP/Castro/chA.txt:31
written_2/non-fiction/OUP/Castro/chB.txt:23
written_2/non-fiction/OUP/Castro/chC.txt:15
written_2/non-fiction/OUP/Castro/chL.txt:26
written_2/non-fiction/OUP/Castro/chM.txt:48
written_2/non-fiction/OUP/Castro/chN.txt:4 
written_2/non-fiction/OUP/Castro/chO.txt:6 
written_2/non-fiction/OUP/Castro/chP.txt:35
written_2/non-fiction/OUP/Castro/chQ.txt:4 
written_2/non-fiction/OUP/Castro/chR.txt:25
written_2/non-fiction/OUP/Castro/chV.txt:16
written_2/non-fiction/OUP/Castro/chW.txt:6 
written_2/non-fiction/OUP/Castro/chY.txt:5 
written_2/non-fiction/OUP/Castro/chZ.txt:4
```
* Using the `-r` option in conjunction with the previous `-c` option from before, the behavior of the two grep command options has been combined, where now grep is counting the number of occurences of the pattern, but does so for each file in the directory which matches the pattern, and then displaying the count for each file.

This option is incredibly useful, as it allows for grep to be used on an entire directory, so that the usage of the command can be chained for multiple files, as well as providing that useful capability for other command options when used simultaneously.

> (source: [https://www.geeksforgeeks.org/grep-command-in-unixlinux/](https://www.geeksforgeeks.org/grep-command-in-unixlinux/))

Another option for the grep command is the `-l` option, which will only print the name or names of the files in which the pattern given to the command occurs. For example,
```
$ grep -l "Article" written_2/travel_guides/berlitz1/HistoryJapan.txt 
written_2/travel_guides/berlitz1/HistoryJapan.txt
```
* Here the option modifies grep to print only the name of the file which contains text matching the pattern.
```
$ grep -l -r "Nether" written_2/
written_2/non-fiction/OUP/Fletcher/ch9.txt
written_2/travel_guides/berlitz1/HistoryEdinburgh.txt
written_2/travel_guides/berlitz1/IntroFrance.txt        
written_2/travel_guides/berlitz1/WhatToFWI.txt
written_2/travel_guides/berlitz1/WhereToFrance.txt      
written_2/travel_guides/berlitz1/WhereToFWI.txt
written_2/travel_guides/berlitz2/Algarve-WhatToDo.txt   
written_2/travel_guides/berlitz2/Amsterdam-History.txt  
written_2/travel_guides/berlitz2/Amsterdam-Intro.txt    
written_2/travel_guides/berlitz2/Amsterdam-WhatToDo.txt 
written_2/travel_guides/berlitz2/Amsterdam-WhereToGo.txt
written_2/travel_guides/berlitz2/Bali-History.txt       
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
```
* This example shows the usage of the `-l` options alongside the previous `-r` option. Combining these two together makes it so that grep will search through the directory recursively, searching for the pattern and printing the name of the file it occurs in according to the behavior of the `-l` option.

This particular command option would be useful if you are just trying to see if the file you are searching contains the pattern or not, and are not concerned with the count, or lines in which it occurs.

> (source: [https://www.geeksforgeeks.org/grep-command-in-unixlinux/](https://www.geeksforgeeks.org/grep-command-in-unixlinux/))

Lastly, another option for the grep command is the `-q` option. This is the "quiet" or "silent" mode for grep, which makes it so that the command does not print any output when it runs. However, the command will still return exit codes for when it is successful, or when it fails.
```
$ grep -q "The" written_2/travel_guides/berlitz2/Amsterdam-Intro.txt
$ echo $?
0
```
* Here the command produced no visible output to the terminal, however, it still produced an error code of 0, which can be seen using the `echo` command with the `$?` variable, meaning that the command ran succesfully.

```
$ grep -q "Aether" written_2/travel_guides/berlitz2/Amsterdam-Intro.txt
$ echo $?
1
```
* The exit code returned from grep here is 1 instead of 0, because the command was not able to match the given pattern in the text file provided.

Although this option might not seem particularly useful at first glance, it can actually be useful for use in bash scripts. For example, if one was writing a bash script to search a pattern in a text file using grep, they could check whether or not grep was able to find the pattern using the exit code returned by the command, which they can then utilize through the `$?` variable in the rest of their script.
> (source: [https://man7.org/linux/man-pages/man1/grep.1.html](https://man7.org/linux/man-pages/man1/grep.1.html))
