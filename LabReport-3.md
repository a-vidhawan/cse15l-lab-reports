# Lab Report 3
***
# Researching Commands
***

## Command Option 1: `grep -r`

The `grep -r` command option of grep recursively searches the directory and subsdirectories (if any) of the provided source, for a specified String.

**Example 1:** `grep -r "inheritance" written_2`

Terminal Symptom:

```
$ grep -r "inheritance" written_2

written_2/travel_guides/berlitz1/WhereToHongKong.txt:many churches all speak of the Portuguese inheritance as well as the

written_2/travel_guides/berlitz2/Crete-WhereToGo.txt:The main site (the one with the admission fee) covers only a tiny part of
the whole, but it protects one of the most important archaeological finds on the island — the Code of Laws dating from the 
Dorian period, around 500 b.c. The huge stone tablet was incised with script dictating codes governing daily life including 
rules on marriage, property, and inheritance rights. The remains of a small theater lie just in front of the code area, and the
site entrance is dominated by the apse of the 6th century basilica of Ágios Títos (St. Titus). The remains of the saint were 
originally interredhere but were moved to Iráklion following Arab raids which destroyed the rest of the building in 825.
```
Here, the `grep -r` command searches the directories and subdirectories of `written_2`, looking for the String "inheritance" in a file. It returns the names of the files it finds "inheritance" in and returns the lines as well.

**Example 2:** `grep -r "Lucayans" written_2`

Terminal Symptom:

```
$ grep -r "Lucayans" written_2

written_2/travel_guides/berlitz2/Bahamas-History.txt:Centuries before the arrival of Columbus, a peaceful Amerindian people who
called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the 
Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience 
of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 
12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them 
today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the 
gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.

written_2/travel_guides/berlitz2/Bahamas-History.txt:The Spaniards never bothered to settle in the Bahamas, but the number of 
shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, 
Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which 
was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes 
of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the 
Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in
the Caribbean.
```

Here, the `grep -r` command searches through the directories and subdirectories of `wriiten_2`, searching for the String "Lucayans". It returns the name of the file that "Lucayans" is in and also the lines.

***
## Command Option 2: `grep -c`

The `grep -c` command option of grep shows the number of lines that contain a specified word in a file. Here, it is used in combination with ` -r` to allow us to search through the files in `written_2`. It prints out the name of every file it looked in, followed by the number of lines that contained the required String.

**Example 1:** `grep -c -r "Lucayans" written_2`

Terminal Symptom:

```
$ grep -c -r "Lucayans" written_2

written_2/non-fiction/OUP/Abernathy/ch1.txt:0
written_2/non-fiction/OUP/Abernathy/ch14.txt:0
written_2/non-fiction/OUP/Abernathy/ch15.txt:0
written_2/non-fiction/OUP/Abernathy/ch2.txt:0
written_2/non-fiction/OUP/Abernathy/ch3.txt:0
written_2/non-fiction/OUP/Abernathy/ch6.txt:0
....
written_2/travel_guides/berlitz2/Athens-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Athens-WhereToGo.txt:0
written_2/travel_guides/berlitz2/Bahamas-History.txt:2
written_2/travel_guides/berlitz2/Bahamas-Intro.txt:0
written_2/travel_guides/berlitz2/Bahamas-WhatToDo.txt:0
....
written_2/travel_guides/berlitz2/PuertoRico-WhatToDo.txt:0
written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt:0
written_2/travel_guides/berlitz2/Vallarta-History.txt:0
written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt:0
```
*Output shortened for Lab Report*

Here, the `grep -c -c` command recursively goes through all the files in the directories and subdirectories of `written_2`, printing out the file name and number of lines that contain "Lucayans". As you can see, it prints 0 for almost all files except for one in the middle that has the number '2' next to it, since that is the only file that contains "Lucayans" and has it twice.

**Example 2:** `grep -c -r "Italy" written_2`

Terminal Symptom:

```
$ grep -c -r "Italy" written_2

written_2/non-fiction/OUP/Abernathy/ch1.txt:0
written_2/non-fiction/OUP/Abernathy/ch14.txt:0
written_2/non-fiction/OUP/Abernathy/ch15.txt:0
....
written_2/non-fiction/OUP/Fletcher/ch2.txt:2
written_2/non-fiction/OUP/Fletcher/ch5.txt:0
written_2/non-fiction/OUP/Fletcher/ch6.txt:0
written_2/non-fiction/OUP/Fletcher/ch9.txt:1
written_2/non-fiction/OUP/Kauffman/ch1.txt:0
....

written_2/non-fiction/OUP/Rybczynski/ch2.txt:2
....
written_2/travel_guides/berlitz1/HistoryFrance.txt:3
written_2/travel_guides/berlitz1/HistoryFWI.txt:0
written_2/travel_guides/berlitz1/HistoryGreek.txt:1
written_2/travel_guides/berlitz1/HistoryHawaii.txt:0
written_2/travel_guides/berlitz1/HistoryHongKong.txt:0
written_2/travel_guides/berlitz1/HistoryIbiza.txt:0
written_2/travel_guides/berlitz1/HistoryIndia.txt:0
written_2/travel_guides/berlitz1/HistoryIsrael.txt:0
written_2/travel_guides/berlitz1/HistoryIstanbul.txt:2
written_2/travel_guides/berlitz1/HistoryItaly.txt:44
....
written_2/travel_guides/berlitz2/Vallarta-History.txt:0
written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt:0
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt:0
```

Here, the `grep -c -r` command recursively searches through all files in the directories and subdirectories of `written_2` for "Italy". As you can see in the shortened output, it prints out the names of all files it checked, and prints number of lines that had "Italy" next to it. In some instances a file has 1 or 2 lines containing "Italy". there is even a file that has 44 lines containing "Italy".

***
## Command Option 3: `grep -`

The `grep -` command option of grep 

**Example 1:** `grep - "" written_2`

Terminal Symptom:

```

```

Here, 

**Example 2:** `grep - "" written_2`

Terminal Symptom:

```

```

Here, 

***
## Command Option 4: `grep -`

The `grep -` command option of grep 

**Example 1:** `grep - "" written_2`

Terminal Symptom:

```

```

Here, 

**Example 2:** `grep - "" written_2`

Terminal Symptom:

```

```

Here, 

***
