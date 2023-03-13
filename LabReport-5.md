# Lab Report 5
***
# Researching Commands
***

## Command Option 1: `find -size`

The `find -size` command option of find looks for files that a match a specific size limit, in the target directory. adding the `+1M` or `+150k` modifier allows the command to search for files that are greater that or equals to the value after the `+` in size. It also works with the `-` modifier which makes it such that it searches for files that are less than or equal to the parameter in size.

Source: ChatGPT prompt for `find` command-line options.

**Example 1:** `find written_2 -size -5k -name "*.txt"`

Terminal Symptom:

```
$ find written_2 -size -5k -name "*.txt"

written_2/travel_guides/berlitz1/HandRHongKong.txt
written_2/travel_guides/berlitz1/HandRIbiza.txt
written_2/travel_guides/berlitz1/HandRIstanbul.txt
written_2/travel_guides/berlitz1/HandRJerusalem.txt
written_2/travel_guides/berlitz1/HandRLakeDistrict.txt
written_2/travel_guides/berlitz1/HandRLasVegas.txt
written_2/travel_guides/berlitz1/HandRLisbon.txt
written_2/travel_guides/berlitz1/HandRLosAngeles.txt
written_2/travel_guides/berlitz1/HandRMadeira.txt
written_2/travel_guides/berlitz1/HandRMallorca.txt
written_2/travel_guides/berlitz1/WhatToFrance.txt
written_2/travel_guides/berlitz1/WhatToHawaii.txt
written_2/travel_guides/berlitz1/WhereToHawaii.txt
```

Here, the `find -size` command searches for files in `written_2` that are less than or equal to 5 Kilobytes in size. An additional filter is applied to the command using `-name "*.txt", which tells the find command to only look for files ending in ".txt". All the paths printed out are paths to files that are at the most 5 Kilobytes in size.

**Example 2:** `find written_2 -size +175k`

Terminal Symptom:

```
$ find written_2 -size +175k

written_2/travel_guides/berlitz1/WhereToFrance.txt
written_2/travel_guides/berlitz1/WhereToItaly.txt
written_2/travel_guides/berlitz1/WhereToJapan.txt
written_2/travel_guides/berlitz1/WhereToMalaysia.txt
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
written_2/travel_guides/berlitz2/China-WhereToGo.txt
```

Here, the `find -size` command searches the subdirectories and directories of `written_2` for files that are greater than or equal to 175 Kilobytes in size. All the paths printed out are paths to files that are at least 175 Kilobytes in size.

***
## Command Option 2: `find -name`

The `find -name` command option of find allows you to search for files or directories with a specified name. It then prints the path of the file if it finds it, or nothing if it doesn't.

Source: ChatGPT prompt for `find` command-line options.

**Example 1:** `find written_2 -name "Cuba-History.txt"`

Terminal Symptom:

```
$ find written_2 -name "Cuba-History.txt"

written_2/travel_guides/berlitz2/Cuba-History.txt
```

Here, the `find -name` command goes through all the directories and subdirectories of written_2, looking for a file named "Cuba-History.txt." It returns the path to the file since "Cuba-History.txt" does exist in `written_2`.

**Example 2:** `find written_2/non-fiction/OUP/Fletcher/ -name "ch7.txt"`

Terminal Symptom:

```
$ find written_2/non-fiction/OUP/Fletcher/ -name "ch7.txt"

$ find written_2/non-fiction/OUP/Fletcher

written_2/non-fiction/OUP/Fletcher
written_2/non-fiction/OUP/Fletcher/ch1.txt
written_2/non-fiction/OUP/Fletcher/ch10.txt
written_2/non-fiction/OUP/Fletcher/ch2.txt
written_2/non-fiction/OUP/Fletcher/ch5.txt
written_2/non-fiction/OUP/Fletcher/ch6.txt
written_2/non-fiction/OUP/Fletcher/ch9.txt
```

Here, the `find -name` command prints nothing, since it could not find a file named "ch7.txt" in the target directory. A subsequent find command call shows that the target directory indded doesn't have a file named "ch7.txt".

***
## Command Option 3: `find -type`

The `find -type` command option of find searches through the target directory for specific types of files. `-type f` searches for regular files, whereas `type -d` searches for directories. The command option prints out the paths of its findings.

Source: ChatGPT prompt for `find` command-line options.

**Example 1:** `find written_2 -type d`

Terminal Symptom:

```
$ find written_2 -type d

written_2
written_2/non-fiction
written_2/non-fiction/OUP
written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Berk
written_2/non-fiction/OUP/Castro
written_2/non-fiction/OUP/Fletcher
written_2/non-fiction/OUP/Kauffman
written_2/non-fiction/OUP/Rybczynski
written_2/travel_guides
written_2/travel_guides/berlitz1
written_2/travel_guides/berlitz2
```

Here, the `find -type d` command goes through `written_2` recursively and prints the paths off all directories and sub-directories present inside `written_2`.

**Example 2:** `find written_2/travel_guides -type f`

Terminal Symptom:

```
$ find written_2/travel_guides -type f

written_2/travel_guides/berlitz1/HandRHawaii.txt
written_2/travel_guides/berlitz1/HandRHongKong.txt
written_2/travel_guides/berlitz1/HandRIbiza.txt
written_2/travel_guides/berlitz1/HandRIsrael.txt
....
written_2/travel_guides/berlitz1/WhereToMadrid.txt
written_2/travel_guides/berlitz1/WhereToMalaysia.txt
written_2/travel_guides/berlitz1/WhereToMallorca.txt
written_2/travel_guides/berlitz2/Algarve-History.txt
written_2/travel_guides/berlitz2/Algarve-Intro.txt
written_2/travel_guides/berlitz2/Algarve-WhatToDo.txt
....
written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt
written_2/travel_guides/berlitz2/Vallarta-History.txt
written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt
```
*Shortened Ouput for Lab Report*

Here, the `find -type f` command goes through the directories and subdirectories in `written_2/travel_guides` and prints the paths of all the regular files that it finds, it excludes printing the paths of the directories and subdirectories of `written_2/travel_guides`.

***
## Command Option 4: `find -`

The `find -` command option of find 

Source: ChatGPT prompt for `find` command-line options.

**Example 1:** ` `

Terminal Symptom:

```
```

Here, 

**Example 2:** ` `

Terminal Symptom:

```
```

Here, 

***
