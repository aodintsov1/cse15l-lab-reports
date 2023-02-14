# Researching Commands (`grep`)

## 1. `grep -f`
Command: ```grep -F Lucayans Bahamas-History.txt```

Output: ```Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.```
* It can't be seen in the code block, but this outputs the only two lines that include "Lucayans" in `Bahamas-History.txt` and highlights the word

Command: ```grep -F Luc Bahamas-History.txt```

Output: ```Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.```
* When searching for "Luc" instead of "Lucayans," the two lines that include Lucayans are outputed with "Luc" highlighted along with the word "Luccucairi," with only the "Luc" highlighted

Source: [https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/](https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/)

## 2. `grep -w`
Command: ```grep -w peace Bahamas-History.txt```

Output: ```News traveled slowly in those days. The Treaty of Versailles in 1783 formally restored the Bahamas to the British, but actual liberation came through a famous escapade that would never have happened in the age of the telegraph. Lieutenant-Colonel Andrew Deveaux, a loyalist from South Carolina, sailed from Florida with six ships, picked up men and fishing boats at Harbour Island and Eleuthera, and “invaded” Nassau. Though vastly outnumbered and outgunned, Deveaux employed elaborate ruses with his little boats to convince the Spanish defenders that his force was overpowering. The humiliating Spanish surrender is proudly recalled in Bahamian history, even though it was all unnecessary: the peace treaty had been signed the previous week. 
One of the major questions still facing the Bahamas is how to accommodate the increasing numbers of tourists while still preserving the special architectural and social heritage of the Out Islands, as well as of the major towns like Nassau. Will it be possible to enjoy the natural splendors of places like Inagua without upsetting the delicate balance of nature? At the moment, the thinking is that it’s perhaps best to leave these smaller, less developed islands in peace.```
* This outputs the two lines in the txt that include "peace," highlighting the word. What makes this different from `-F` is that it ignores times when the searched word is only part of the word so times when the text says "peaceful" are ignored

Command: ```grep -w 19 Bahamas-History.txt```

Output: (none)
* The file has several dates that start with 19 such as 1973 and 1967 but ignores them for this search because it is only looking for "19" as as whole word

Source: [https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/](https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/)

## 3. `grep -i`
Command: ```grep -i "lucayans" Bahamas-History.txt```
Output: ```Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.```
* The output for this is identical to the ```grep -F Lucayans Bahamas-History.txt``` command, yet "lucayans" is in lower case. This is because `-i` ignores matches lower and upper cases when searching for words, unlike `-F`

Command: ```grep -i "A BRIEF HISTORY" Bahamas-History.txt```

Output: ```A Brief History```
* The first line only consists of "A Brief History," as shown in the output. However, in the search field the words are written in all capitals but the line is still output because the capitals do not count when using `-i`
 
Source: [https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/](https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/)

## 4. `grep -E`
Command: ```grep -E "Brief|Lucayans" Bahamas-History.txt```

Output: ```A Brief History
Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.```
* By using `-E` and putting a "|" in between the two search words, the search looks for both of the words and outputs the lines that include one of the words

Command: ```grep -E "World|20th" Bahamas-History.txt```

Output: ```The 20th Century
Desperate for work, perhaps 20 percent of the Bahamian population left to take construction jobs in Florida between the turn of the century and World War I. During that war hundreds of Bahamians saw active service with British forces. The islands suffered food shortages and a serious bank failure, but nothing more threatening militarily than rumors of German submarines offshore.
In some respects, World War II put the Bahamas on the international map. The colony was chosen to have two of the sites Britain leased to the United States under Franklin D. Roosevelt’s “destroyers for bases” deal in 1940. Allied forces operated submarine-hunting and air-sea rescue stations on the islands; Royal Air Force pilots and Royal Navy frogmen were trained here, and much trans-Atlantic air traffic passed through the Bahamas.```
* This command searches for both "World" and "20th" and returns the lines that include the words

Source: [https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/](https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/)
