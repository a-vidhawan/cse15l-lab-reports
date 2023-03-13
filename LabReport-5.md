# Lab Report 5
***
# Researching Commands
***

## Command Option 1: `find -`

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
