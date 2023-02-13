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
Here, the `grep` command searches the directories and subdirectories of `written_2`, looking for the String "inheritance" in a file. It returns the names of the files it finds "inheritance" in and returns the lines as well.

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

Here, the `grep` command searches through the directories and subdirectories of `wriiten_2`, searching for the String "Lucayans". It returns the name of the file that "Lucayans" is in and also the lines.

***
## Command Option 2: `grep -c`

The `grep -c` command option of grep shows the number of lines that contain a specified word in a file. Here, it is used in combination with `grep -r` to help us search through a number of directories faster. It prints out the name of every file it looked in, followed by the number of lines that contained the required String.

**Example 1:** `grep -c "" written_2`

Terminal Symptom:

```
```



**Example 2:** `grep -c "" written_2`

Terminal Symptom:

```
```


***
## Command Option 3: `grep -`

The `grep -` command option of grep 

**Example 1:** `grep - "" written_2`

Terminal Symptom:

```
```



**Example 2:** `grep - "" written_2`

Terminal Symptom:

```
```


***
## Command Option 4: `grep -`

The `grep -` command option of grep 

**Example 1:** `grep - "" written_2`

Terminal Symptom:

```
```



**Example 2:** `grep - "" written_2`

Terminal Symptom:

```
```


***
