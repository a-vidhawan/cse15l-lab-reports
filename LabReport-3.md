# Lab Report 3
***
# Researching Commands
***

## Command Option 1: `grep -r`

The `grep -r` command option of grep recursively searches the directory and subdirectories (if any) of the provided source, for a specified String. It then prints out the path to the file and the line in the file containing the specified String.

Source: ChatGPT prompt for `grep` command-line options

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

Source: ChatGPT prompt for `grep` command-line options

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

Here, the `grep -c -r` command recursively goes through all the files in the directories and subdirectories of `written_2`, printing out the file name and number of lines that contain "Lucayans". As you can see, it prints 0 for almost all files except for one in the middle that has the number '2' next to it, since that is the only file that contains "Lucayans" and has it twice.

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
*Shortened Output for Lab Report*

Here, the `grep -c -r` command recursively searches through all files in the directories and subdirectories of `written_2` for "Italy". As you can see in the shortened output, it prints out the names of all files it checked, and prints number of lines that had "Italy" next to it. In some instances a file has 1 or 2 lines containing "Italy". there is even a file that has 44 lines containing "Italy".

***
## Command Option 3: `grep -l`

The `grep -l` command option of grep 'lists' the files that are found to contain the specified String. The output in the terminal consists of only the paths to the files that contain the specified String, and not the actual lines that contain them. Here, it is used in combination with ` -r` to allow us to search through the files in `written_2`.

Source: ChatGPT prompt for `grep` command-line options

**Example 1:** `grep -l -r "Lucayans" written_2`

Terminal Symptom:

```
$ grep -l -r "Lucayans" written_2

written_2/travel_guides/berlitz2/Bahamas-History.txt
```

Here, the `grep -l -r` command recursively goes through all files in the directories and subdirectories of `written_2` for "Lucayans". It prints out the name, path of the 1 file that contains "Lucayans". 

**Example 2:** `grep -l -r "Italy" written_2`

Terminal Symptom:

```
$ grep -l -r "Italy" written_2

written_2/non-fiction/OUP/Castro/chP.txt
written_2/non-fiction/OUP/Fletcher/ch2.txt
written_2/non-fiction/OUP/Fletcher/ch9.txt
written_2/non-fiction/OUP/Rybczynski/ch2.txt
written_2/travel_guides/berlitz1/HistoryFrance.txt
written_2/travel_guides/berlitz1/HistoryGreek.txt
written_2/travel_guides/berlitz1/HistoryIstanbul.txt
written_2/travel_guides/berlitz1/HistoryItaly.txt
....
written_2/travel_guides/berlitz2/California-WhereToGo.txt
written_2/travel_guides/berlitz2/Canada-History.txt
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
written_2/travel_guides/berlitz2/Costa-History.txt
written_2/travel_guides/berlitz2/CostaBlanca-History.txt
written_2/travel_guides/berlitz2/Crete-WhereToGo.txt
written_2/travel_guides/berlitz2/CstaBlanca-WhereToGo.txt
written_2/travel_guides/berlitz2/Paris-WhereToGo.txt
written_2/travel_guides/berlitz2/Portugal-History.txt
written_2/travel_guides/berlitz2/Portugal-WhatToDo.txt
```
*Shortened output for Lab Report*

Here, the `grep -l -r` command recursively goes through all files in the directories and subdirectories of `written_2` for "Italy". It prints out the names, paths of all the files that it sees contain "Italy".

***
## Command Option 4: `grep -n`

The `grep -n` command option of grep prefixes each line of output with the line number in the file. Here, it is used in collaboration with `-r` allowing us to easily access all the file sin `written_2`. 

Source: ChatGPT prompt for `grep` command-line options

**Example 1:** `grep -n -r "Lucayans" written_2`

Terminal Symptom:

```
$ grep -n -r "Lucayans" written_2

written_2/travel_guides/berlitz2/Bahamas-History.txt:6:Centuries before the arrival of Columbus, a peaceful Amerindian people
whocalled themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through 
theCaribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the 
experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San
Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people 
Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish 
patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.

written_2/travel_guides/berlitz2/Bahamas-History.txt:7:The Spaniards never bothered to settle in the Bahamas, but the number
of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean,
Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as 
“Spanish Wells” — whichwas used to replenish the supplies of water on their ships before they began the long journey back to 
Europe with their cargoes ofSouth American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people,
were removed from the Bahamas towork — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti),
Cuba, and elsewhere in the Caribbean.
```

Here, the `grep -n -r` command recursively goes through all files in the directories and subdirectories of `writen_2` for "Lucayans". It prints out the paths and names of the files that contain "Lucayans", the lines that contain it and the line number in the file where "Lucayans" is present.

**Example 2:** `grep -n -r "flavour" written_2`

Terminal Symptom:

```
$ grep -n -r "flavour" written_2

written_2/travel_guides/berlitz1/HandRIsrael.txt:299: international meat dishes, with French flavour.
written_2/travel_guides/berlitz1/WhatToIbiza.txt:201: in interesting and varied flavours. Hierbas, anís seco, anís dulce, and
written_2/travel_guides/berlitz1/WhatToIbiza.txt:353: invention, a highly flavoured, chilled soup to which chopped cucumbers,
written_2/travel_guides/berlitz1/WhatToIbiza.txt:404: milk flavoured with cinnamon.
written_2/travel_guides/berlitz1/WhatToIstanbul.txt:138: Delight, which comes in many flavours and can be found in shops in and
written_2/travel_guides/berlitz1/WhatToIstanbul.txt:303: fillet cooked in a sauce flavoured with ground walnuts and paprika.
written_2/travel_guides/berlitz1/WhatToIstanbul.txt:308: çorbası (“wedding” soup, a mutton broth flavoured with lemon juice and
written_2/travel_guides/berlitz1/WhatToIstanbul.txt:352: The most well known is lokum (Turkish Delight), a soft jelly, flavoured
written_2/travel_guides/berlitz1/WhatToIstanbul.txt:361: zerde (a saffron-flavoured rice pudding), and tavuk gö‘sü (a
written_2/travel_guides/berlitz1/WhereToIstanbul.txt:570: lemon- and cherry-flavoured drinks.
written_2/travel_guides/berlitz1/WhereToIstanbul.txt:1222: international in flavour than Turkish.

written_2/travel_guides/berlitz2/CostaBlanca-WhatToDo.txt:81:The favourite dish of many visitors is the Andalusian “liquid salad,”
gazpacho. This chilled, highly-flavoured soup, with chopped tomatoes, peppers, cucumbers, onions, and croutons, is a rousing 
refresher on a hot summer day. Caution: gazpachos with an s is quite a different dish (see page 90).

written_2/travel_guides/berlitz2/CostaBlanca-WhatToDo.txt:111:Although wines from the north are considered to be Spain’s best, the
Costa Blanca’s vino is very drinkable and very reasonably priced. Look for Monóvar, Pinosa, and the lighter, less plentiful Ricote 
(all available in red, rosé, or white). Beware of the innocent-looking red Jumilla. Its 18 percent alcohol content can sneak up on 
you. Same peril with the strong Alicante dessert wine, ten drops of which were long reckoned to be one of nature’s surest cures.
Although the prescribed amount failed to restore France’s ageing Louis XIV to health, it might work wonders with a morning-after 
feeling. Be sure to taste the Costa Blanca’s famous Moscatel wine. It’s perfect with dessert and preserves all the sweet, 
distinctive flavour of a Muscat grape.

written_2/travel_guides/berlitz2/CstaBlanca-WhereToGo.txt:71:From Guadalest, the road leads to the small town of Callosa de 
Ensarriá, centre of the honey industry, where you can taste before you buy, often six or eight different flavours. From Callosa 
take the Parcent road, follow it for 21⁄2 km (11⁄2 miles), and make a right-hand turn at the entrance to the El Algar waterfalls,
a tumbling oasis beneath the massive Sierra Bernia formed by a tributary of the River Guadalest. Leave your car in the parking area
and walk to the 27-metre (80-foot) falls. You can swim beneath them in chilly waters, then picnic by the cool, leafy pools above.
It’s easy to get away from crowds in this pleasant spot, but if you’re in the mood for company, you’ll find lots of people in the
restaurants near the car park.
```

Here, the `grep -n -r` command recursively goes through all files in the directories and subdirectories of `writen_2` for "flavour". It prints out the paths and names of the files that contain "flavour", the lines that contain "flavour" in them and the line number in the file where "flavour" is present.

***
