# Lab Report 3 - Reasearching Commands

## The Grep Command

The focus of this report will be the ```grep``` command. The ```grep``` command in its original form will return a line containing a phrase inputted by the user, in a file specified by the user. There are many ways to modify the command to suit our needs. This report will look at athe ```-n```, ```-h```, ```-o```, and ```-v``` flags. For the ```-h``` and ```-o``` flag demonstrations, the ```-r``` flag will be used as well. The ```-r``` flag recursively makes the command search all files in a given directory for the provided phrase.

## -n flag 

[Source](https://en.wikibooks.org/wiki/Grep)

The ```-n``` flag adds the line number on which a match has been found within a file. This can be helpful for when you need to locate instances of a phrase and edit them in a large text file.

The following search shows the results of searching for "Paris" without the ```-n``` flag, which displays all lines in "travel_guide/berlitz1/WhereToFrance.txt" containing "Paris" without line numbers.

```
$ grep Paris travel_guides/berlitz1/WhereToFrance.txt 
        divided the country into just five regions: Paris and its vicinity
        diversity of French life: Paris and the wine country, the mountains, or
        include Paris. Ideally, divide your stay — sightseeing in the capital
        sunny village in the hills, then shopping in Paris at the end. A
        relaxing vacation, for example, might combine Paris and the
        It’s best to visit Paris in early summer and autumn, and the island
        themselves; in the summer months many Parisians flee the city and the
        Paris, you can make it to Dijon for a visit to the Burgundy vineyards
        helpful in the Paris rush hour. In fact, it’s wise to drive as little
        as possible inside Paris; the périphérique ringroad runs around the
        Paris recently created miles of cycling lanes that crisscross the
        Paris and its immediate surroundings are a magnet for
        the city to protest government policies. A vibrant city, Paris sets
        For years, ambitious French people saw Paris as the only
        this trend, but Paris retains its aura of superiority — and its lack of
        Before Paris became the national capital, it was the home
        The Paris basin is a treasury of national monuments. Roughly bounded by
        away from the troublesome mob of Paris, at Fon­taine­bleau, Chantilly,
        easy day trip by car or local train, enabling you to keep your Paris
        Paris
        The city and the people of Paris share a boundless
        clear, Paris offers golden nighttime illumination of its major
        renovation, time seems to stand still in many Paris neighborhoods.
        Paris is one of the world’s most densely populated
        The river plays a central role in all visits to Paris. It’s
        The Pont-Neuf (neuf means “new”) is in fact Paris’s oldest
        Hitler came to Paris as conqueror in 1940, this was the first place he
        of the ritziest streets in Paris (Avenue Foch is a particularly good
        the Rev­o­lu­tion and the site of the Germans’ last foot­hold in Paris
        the most ancient monument in Paris, the 23-m- (75-ft-) tall
        Car­di­nal Richelieu as his Paris residence in 1639, and originally
        armies. Parisians like it most for the flower market at its base and
        it “La Butte” (“The Mound”), Montmartre is an essential piece of Paris
        Paris’s own vineyard, the Clos de Montmartre.
        basilica, towering over Paris with its gleaming white façade and
        the 17th century and wealthy Parisians built luxurious private homes
        Historique de la Ville de Paris.
        Jew­ish quarter (or shtetl, as Paris Jews call it) around the Rue des
        The grounds of the cemeteries of Paris are beautifully
        prow, the Ile de la Cité is the ancient heart of Paris, settled by the
        Celtic “Parisii” people as early as the third century b.c. In the
        Paris swept away most of the medieval and 17th-century structures,
        modern Paris, holds echoes of the nation’s earliest kings, who dwelt
        The delicate walls of 13th-century stained glass (Paris’s oldest) and
        The site of the great cathedral of Notre-Dame de Paris has
        Notre-Dame de Paris.
        celebrities of Paris. In modern times, President Georges Pompidou lived
        the larger Paris university system and lost its independence.
        of Parisians, from early-morning joggers to children sailing boats on
        ridiculous tower,” and Verlaine rerouted his journey around Paris in
        wild until 1852, into the closest thing Paris has to a London-style
        Paris from river attack while he was away on a crusade. You can see the
        Paris rooftops as you go up the escalator. And the cosmopolitan crowd
        art of which Paris is still the world capital.
        The Musée d’Art Moderne de la Ville de Paris (11 Ave. du
        and also for sculpture of Paris’s Roman and Gothic past; Musée Guimet
        Versailles is an easy (and full) day trip from Paris, only
        early start at a Paris street market to buy a picnic; morning tour of
        plain. It’s a pleasant one-hour drive from Paris and there are regular
        Located 50 km (30 miles) north of Paris, Chantilly is
        the design for Chartres cathedral and also for Paris’s Notre-Dame.
        22 miles north of Paris on the A1 autoroute. Shuttle buses run to the
        An alternative is Disneyland Paris, 32 km (20 miles) east
        of Paris near Marne-la-Vallée.
        Some 80 km (50 miles) up the autoroute du Nord from Paris,
        approaches to Paris, Lorraine has long been a pawn in France’s
        makes it a rewarding stopover on any journey between Paris and
        des Arts Décoratifs offers interesting comparisons between Parisian and
        If you are driving from Paris, you’ll get the best out of
        architecture, of culture and learning. It is only one hour from Paris
        and the Hôtel Aubriot (at number 40), home of the Provost of Paris who
        Paris is a popular gateway to Normandy for those crossing the English
        Parish Closes (enclos paroissiaux).
        Parish Close Road
        The route we propose for visitors driving from Paris
        ­casino was designed by Charles Garnier, architect of the Paris Opera
        Across the square, the Hôtel de Paris is another monument
        terrains, all distant in geography and spirit alike from Paris and the
        Many visitors driving from Paris to the Dordogne and
        design of the Paris Opera House.
        Cathédrale Saint-André closely rival those of Notre-Dame de Paris —
```

In the following example, we are searching for "Paris" in "travel_guide/berlitz1/WhereToFrance.txt" with the flag. You can see the line numbers prior to the actual content of the line.

```
$ grep -n Paris travel_guides/berlitz1/WhereToFrance.txt 
15:        divided the country into just five regions: Paris and its vicinity
28:        diversity of French life: Paris and the wine country, the mountains, or
31:        include Paris. Ideally, divide your stay — sightseeing in the capital
33:        sunny village in the hills, then shopping in Paris at the end. A
34:        relaxing vacation, for example, might combine Paris and the
47:        It’s best to visit Paris in early summer and autumn, and the island
51:        themselves; in the summer months many Parisians flee the city and the
80:        Paris, you can make it to Dijon for a visit to the Burgundy vineyards
98:        helpful in the Paris rush hour. In fact, it’s wise to drive as little
99:        as possible inside Paris; the périphérique ringroad runs around the
106:        Paris recently created miles of cycling lanes that crisscross the
137:        Paris and its immediate surroundings are a magnet for
140:        the city to protest government policies. A vibrant city, Paris sets
142:        For years, ambitious French people saw Paris as the only
146:        this trend, but Paris retains its aura of superiority — and its lack of
148:        Before Paris became the national capital, it was the home
152:        The Paris basin is a treasury of national monuments. Roughly bounded by
158:        away from the troublesome mob of Paris, at Fon­taine­bleau, Chantilly,
161:        easy day trip by car or local train, enabling you to keep your Paris
164:        Paris
165:        The city and the people of Paris share a boundless
177:        clear, Paris offers golden nighttime illumination of its major
195:        renovation, time seems to stand still in many Paris neighborhoods.
198:        Paris is one of the world’s most densely populated
206:        The river plays a central role in all visits to Paris. It’s
219:        The Pont-Neuf (neuf means “new”) is in fact Paris’s oldest
255:        Hitler came to Paris as conqueror in 1940, this was the first place he
259:        of the ritziest streets in Paris (Avenue Foch is a particularly good
267:        the Rev­o­lu­tion and the site of the Germans’ last foot­hold in Paris
269:        the most ancient monument in Paris, the 23-m- (75-ft-) tall
291:        Car­di­nal Richelieu as his Paris residence in 1639, and originally
354:        armies. Parisians like it most for the flower market at its base and
365:        it “La Butte” (“The Mound”), Montmartre is an essential piece of Paris
390:        Paris’s own vineyard, the Clos de Montmartre.
393:        basilica, towering over Paris with its gleaming white façade and
404:        the 17th century and wealthy Parisians built luxurious private homes
424:        Historique de la Ville de Paris.
435:        Jew­ish quarter (or shtetl, as Paris Jews call it) around the Rue des
439:        The grounds of the cemeteries of Paris are beautifully
449:        prow, the Ile de la Cité is the ancient heart of Paris, settled by the
450:        Celtic “Parisii” people as early as the third century b.c. In the
453:        Paris swept away most of the medieval and 17th-century structures,
464:        modern Paris, holds echoes of the nation’s earliest kings, who dwelt
468:        The delicate walls of 13th-century stained glass (Paris’s oldest) and
486:        The site of the great cathedral of Notre-Dame de Paris has
518:        Notre-Dame de Paris.
530:        celebrities of Paris. In modern times, President Georges Pompidou lived
575:        the larger Paris university system and lost its independence.
589:        of Parisians, from early-morning joggers to children sailing boats on
666:        ridiculous tower,” and Verlaine rerouted his journey around Paris in
677:        wild until 1852, into the closest thing Paris has to a London-style
738:        Paris from river attack while he was away on a crusade. You can see the
767:        Paris rooftops as you go up the escalator. And the cosmopolitan crowd
778:        art of which Paris is still the world capital.
792:        The Musée d’Art Moderne de la Ville de Paris (11 Ave. du
833:        and also for sculpture of Paris’s Roman and Gothic past; Musée Guimet
843:        Versailles is an easy (and full) day trip from Paris, only
852:        early start at a Paris street market to buy a picnic; morning tour of
942:        plain. It’s a pleasant one-hour drive from Paris and there are regular
1001:        Located 50 km (30 miles) north of Paris, Chantilly is
1034:        the design for Chartres cathedral and also for Paris’s Notre-Dame.
1045:        22 miles north of Paris on the A1 autoroute. Shuttle buses run to the
1047:        An alternative is Disneyland Paris, 32 km (20 miles) east
1048:        of Paris near Marne-la-Vallée.
1050:        Some 80 km (50 miles) up the autoroute du Nord from Paris,
1287:        approaches to Paris, Lorraine has long been a pawn in France’s
1293:        makes it a rewarding stopover on any journey between Paris and
1405:        des Arts Décoratifs offers interesting comparisons between Parisian and
1544:        If you are driving from Paris, you’ll get the best out of
1679:        architecture, of culture and learning. It is only one hour from Paris
1730:        and the Hôtel Aubriot (at number 40), home of the Provost of Paris who
1883:        Paris is a popular gateway to Normandy for those crossing the English
2202:        Parish Closes (enclos paroissiaux).
2250:        Parish Close Road
2333:        The route we propose for visitors driving from Paris
3137:        ­casino was designed by Charles Garnier, architect of the Paris Opera
3139:        Across the square, the Hôtel de Paris is another monument
3220:        terrains, all distant in geography and spirit alike from Paris and the
3233:        Many visitors driving from Paris to the Dordogne and
3491:        design of the Paris Opera House.
3500:        Cathédrale Saint-André closely rival those of Notre-Dame de Paris —
```

In the following sesarch, we search for "Biology" without the ```-n``` flag, which does not display line numbers.

```
$ grep Biology non-fiction/OUP/Kauffman/ch1.txt 
Prolegomenon to a General Biology
As long ago as 1971, I had published my own first foray into the origin-of-life problem as a young assistant professor in the Department of Theoretical Biology at the University of Chicago. I had wondered if life must be based on template replicating nucleic acids such as DNA or RNA double helices and found myself doubting that standard assumption. Life, at its core, depends upon autocatalysis, that is, reproduction. Most catalysis in cells is carried out by protein enzymes. Might there be general laws supporting the possibility that systems of catalytic polymers such as proteins might be self-reproducing? Proteins are, as noted, linear sequences of twenty kinds of standard amino acids. Consider, then, a first copy of a protein that has the capacity to catalyze a reaction by which two fragments of a potential second copy of that same protein might be ligated to make the second copy of the whole protein. Such a protein, A, say, thirty-two amino acids long, might act on two fragments, say, fifteen amino acids and seventeen amino acids in length, and ligate the two to make a second copy of the thirty-two amino acid sequence.
```

In the following example, we are looking for "Biology" in "non-fiction/OUP/Kauffman/ch1.txt". Here, we can see that only lines 6 and 95 contain "Biology".

```
$ grep -n Biology non-fiction/OUP/Kauffman/ch1.txt
6:Prolegomenon to a General Biology
95:As long ago as 1971, I had published my own first foray into the origin-of-life problem as a young assistant professor in the Department of Theoretical Biology at the University of Chicago. I had wondered if life must be based on template replicating nucleic acids such as DNA or RNA double helices and found myself doubting that standard assumption. Life, at its core, depends upon autocatalysis, that is, reproduction. Most catalysis in cells is carried out by protein enzymes. Might there be general laws supporting the possibility that systems of catalytic polymers such as proteins might be self-reproducing? Proteins are, as noted, linear sequences of twenty kinds of standard amino acids. Consider, then, a first copy of a protein that has the capacity to catalyze a reaction by which two fragments of a potential second copy of that same protein might be ligated to make the second copy of the whole protein. Such a protein, A, say, thirty-two amino acids long, might act on two fragments, say, fifteen amino acids and seventeen amino acids in length, and ligate the two to make a second copy of the thirty-two amino acid sequence.
```

## -h flag

[Source](https://en.wikibooks.org/wiki/Grep)

The ```-h``` flag removes the file path from the output. This can be helpful for making it so that your terminal does not get cluttered if you do not need the path.

This first search shows the results of ```grep -r``` without the use of the ```-h``` flag, where you can see the path (travel_guides/berlitz2/*.txt).

```
$ grep -r Elbow
travel_guides/berlitz2/Bahamas-WhereToGo.txt:Elbow Cay, southeast of Marsh Harbour, is the most popular, and its capital, Hope Town, is one of the most charming spots in the Bahamas. Yachts at anchor clutter the nearly circular harbor beneath a candy-striped lighthouse few photographers can resist. Rising 120 ft (37 m) above sea level, the Hope Town Lighthouse can be seen from a distance of 17 miles (27 km). When it was built in 1864 it helped drastically reduce the number of shipping accidents and shipwrecks, but it was unpopular with the native people who relied on lucrative salvage activities to make a living. It is one of only three manual lighthouses in the Bahamas and has to be turned throughout the day and night by a team of dedicated lighthouse workers. Climb the 101 steps to the top for fantastic views over the whole of Elbow Cay.
travel_guides/berlitz2/Bermuda-WhatToDo.txt:With many shallow lagoons, Bermuda is a great place for windsurfing, jet skiing, pedalos, or aqua-cycling. Most large hotels will have some equipment for hire. If they don’t have what you need, contact Blue Waters Divers and Watersports, which has comprehensive facilities at three sites: Somerset Bridge, Elbow Beach, and the Marriott Castle Harbour Resort. You can reach them at P.O. Box SN 165, Southampton, SN BX, Bermuda; Tel. 234-1034; fax. 234-3561; website <www.divebermuda.com>. 
travel_guides/berlitz2/Bermuda-WhereToGo.txt:You will come first to the Elbow Beach Resort and the nearby public Bermuda Beach. The resort is one of the premier hotels on the island and sits on a long stretch of sand that is for hotel guests exclusively. South Road travels on top of the cliffs and offers beautiful views of the sand dunes and beaches below. Don’t worry about trying to take in these views while driving, for there are many stopping places along the way where you can take photographs or simply enjoy the panorama. The way to each beach is marked with a wooden sign, which leads to parking areas for bicycles and cars off the main road.
```

When the same command is run with the ```-h``` flag, there path is no longer displayed.

```
$ grep -rh Elbow
Elbow Cay, southeast of Marsh Harbour, is the most popular, and its capital, Hope Town, is one of the most charming spots in the Bahamas. Yachts at anchor clutter the nearly circular harbor beneath a candy-striped lighthouse few photographers can resist. Rising 120 ft (37 m) above sea level, the Hope Town Lighthouse can be seen from a distance of 17 miles (27 km). When it was built in 1864 it helped drastically reduce the number of shipping accidents and shipwrecks, but it was unpopular with the native people who relied on lucrative salvage activities to make a living. It is one of only three manual lighthouses in the Bahamas and has to be turned throughout the day and night by a team of dedicated lighthouse workers. Climb the 101 steps to the top for fantastic views over the whole of Elbow Cay.
With many shallow lagoons, Bermuda is a great place for windsurfing, jet skiing, pedalos, or aqua-cycling. Most large hotels will have some equipment for hire. If they don’t have what you need, contact Blue Waters Divers and Watersports, which has comprehensive facilities at three sites: Somerset Bridge, Elbow Beach, and the Marriott Castle Harbour Resort. You can reach them at P.O. Box SN 165, Southampton, SN BX, Bermuda; Tel. 234-1034; fax. 234-3561; website <www.divebermuda.com>. 
You will come first to the Elbow Beach Resort and the nearby public Bermuda Beach. The resort is one of the premier hotels on the island and sits on a long stretch of sand that is for hotel guests exclusively. South Road travels on top of the cliffs and offers beautiful views of the sand dunes and beaches below. Don’t worry about trying to take in these views while driving, for there are many stopping places along the way where you can take photographs or simply enjoy the panorama. The way to each beach is marked with a wooden sign, which leads to parking areas for bicycles and cars off the main road.
```

This first search shows the results prior to using the ```-h``` flag, which displays the path of all files containing "Volcano".

```
$ grep -r Volcano
travel_guides/berlitz1/HandRHawaii.txt:        Chalet Kilauea $$–$$$ P.O. Box 998, Volcano, HI 96785; Tel.
travel_guides/berlitz1/HandRHawaii.txt:        of bed & breakfast accommodations in the Volcano area. They have
travel_guides/berlitz1/IntroFWI.txt:        steep hills and rolling plains. Volcanoes, hummingbirds, mangroves,
travel_guides/berlitz1/WhereToFWI.txt:        Vacillating Volcano
travel_guides/berlitz1/WhereToFWI.txt:        Saint-Pierre and the Volcano
travel_guides/berlitz1/WhereToHawaii.txt:        Volcanoes National Park has active lava flows flowing to
travel_guides/berlitz2/CanaryIslands-WhereToGo.txt:The inland route south to Puerto del Rosario follows the FV-101 and a diversion, west along the FV-109 will bring you first to the Zoo Safari Calderón Hondo. There you can opt for either a half-hour camel trip or a 11⁄2 hour safari to the lunar landscape of the Volcano Calderón Hondo. Next comes the lace-making town of Lajares. And if you really want to get away from it all, continue on to El Cotillo. This tiny fishing village on the east coast also boasts some excellent beaches wonderful for windsurfing, plus a handful of local bars and some basic restaurants. Heading back south from El Cotillo, the FV-10 rejoins the FV-101 at the small town of La Oliva. This is not especially attractive but it does feature two places of interest. Just off the main road stands the Casa de los Coroneles (House of the Colonels). Its name derives from its 18th-century tenants who once ruled the island. The decaying, cream-colored building still exudes a certain haughty, if melancholy, grandeur. By contrast, the nearby Centro de Arte Canario is bright and modern, exhibiting the works of some of the finest living Canarian artists.
```

Once the ```-h``` flag is used, we can no longer see the path of the file.

```
$ grep -rh Volcano
        Chalet Kilauea $$–$$$ P.O. Box 998, Volcano, HI 96785; Tel.
        of bed & breakfast accommodations in the Volcano area. They have
        steep hills and rolling plains. Volcanoes, hummingbirds, mangroves,
        Vacillating Volcano
        Saint-Pierre and the Volcano
        Volcanoes National Park has active lava flows flowing to
The inland route south to Puerto del Rosario follows the FV-101 and a diversion, west along the FV-109 will bring you first to the Zoo Safari Calderón Hondo. There you can opt for either a half-hour camel trip or a 11⁄2 hour safari to the lunar landscape of the Volcano Calderón Hondo. Next comes the lace-making town of Lajares. And if you really want to get away from it all, continue on to El Cotillo. This tiny fishing village on the east coast also boasts some excellent beaches wonderful for windsurfing, plus a handful of local bars and some basic restaurants. Heading back south from El Cotillo, the FV-10 rejoins the FV-101 at the small town of La Oliva. This is not especially attractive but it does feature two places of interest. Just off the main road stands the Casa de los Coroneles (House of the Colonels). Its name derives from its 18th-century tenants who once ruled the island. The decaying, cream-colored building still exudes a certain haughty, if melancholy, grandeur. By contrast, the nearby Centro de Arte Canario is bright and modern, exhibiting the works of some of the finest living Canarian artists.
```

## -o flag

[Source](https://en.wikibooks.org/wiki/Grep)

The ```-o``` flag displays only the matched input and excludes the surrounding characters and lines. This can be useful for ensuring that your terminal does not get filled when you only want to check for the presence of phrase.

The following search (without ```-o```) displays the results of searching for "fortnight", which fills the terminal quickly.

```
$ grep -r fortnight
travel_guides/berlitz1/IntroIsrael.txt:        unique features. It is perfectly feasible to spend a fortnight in
travel_guides/berlitz2/Canada-WhereToGo.txt:On the estuary, the peaceful town of Annapolis Royal was once the beleaguered target of 14 British and French sieges and countless pirate raids. Formerly Port Royal, it was renamed after England’s Queen Anne and became capital of Nova Scotia until the foundation of Halifax. Fort Anne National Historic Site, focus for the belligerence, is now a pleasant park of grassy knolls and ridges, remains of the earthwork defenses. Of the original buildings, only a powder house in the southwest bastion and a storehouse in the northwest survive. The officers’ quarters of 1797 have been reconstructed to house a museum of local Indian culture and natural history. Epitome of the town’s more peaceful side, the Annapolis Royal Historic Gardens south of the city center display flora representative of the region’s inhabitants: mayflower and pines for the Micmacs; iris and the vegetables the Acadians grew, with a reconstruction of their ingenious system of dykes and a typical Acadian cottage; an English rose arbor; and Victorian flower beds. A marsh lookout gives you a good view over the estuary. In the town center, the shops and taverns on Lower St. George Street are being transformed to recapture the grace of the town’s Victorian era. Port Royal (10 km/6 miles west along Highway 1) is a fine recreation of Samuel de Champlain’s timbered Abitation, built in 1605. Furniture, utensils, and craftware, supplemented by audiovisual shows, give a vivid insight into the earliest permanent European settlement north of Florida. You can see how the French settlers, just 60 to begin with, made friendly contact with the Micmac. And hear how Champlain kept up morale throughout the long winters with a social club, L’Ordre du Bon Temps (The Order of Good Times). Each member would organize a fortnightly banquet of game and fish he had caught himself. Among the entertainments they concocted to cheer up the long cold evenings was a play, Le Théâtre de Neptune. North America’s first known full-length drama was written by the colony’s lawyer, Marc Lescarbot. His writings, along with Champlain’s journals, provided the basis for the reconstitution of their environment.
travel_guides/berlitz2/China-WhereToGo.txt:Any two of these week-long segments can be combined for a fortnight’s touring. The most popular itineraries invariably include Beijing, Xi’an, Guilin, and Shanghai, each city providing a glimpse of China past and present.
```

With the introduction of the ```-o``` flag, we can omit all unnecessary information.

```
$ grep -ro fortnight
travel_guides/berlitz1/IntroIsrael.txt:fortnight
travel_guides/berlitz2/Canada-WhereToGo.txt:fortnight
travel_guides/berlitz2/China-WhereToGo.txt:fortnight
```

The following is a search for "Genghis", returning a very lengthy output which can quickly clutter up our terminal if all we need to do is find instances of the word in files.

```
$ grep -r Genghis
travel_guides/berlitz1/HistoryIndia.txt:        Genghis Khan, accepted their welcome but made no promises. His men
travel_guides/berlitz1/HistoryIndia.txt:        distinct from those of Genghis Khan, who are referred to as “Mongols”
travel_guides/berlitz2/Beijing-History.txt:Another swarm of nomadic invaders eventually routed the Khitan, establishing the capital of the Jin Dynasty (1115–1234) on the outskirts of Beijing (which they renamed Zhongdu, or Central Capital). The Jin capital was in turn completely razed by a fresh batch of northern nomadic usurpers. They were the Mongols — led by Genghis Khan — who would leave a more lasting and extensive mark on Beijing and all of China.
travel_guides/berlitz2/Beijing-History.txt:Genghis Khan laid the groundwork, gradually uniting all China under his rule and leaving it to his famous grandson, Kublai Khan, to secure the Yuan Dynasty (1279–1368). Kublai Khan erected his own capital in 1279 on the shores of Beijing’s Beihai Lake, where some of his imperial treasures remain on display today. It was to these same shores that Marco Polo claimed to have journeyed at the end of the 13th century, where he won the support of Kublai Khan. He made Beijing, then known as Khanbaliq (Khan’s Town) or Dadu (Great Capital), the base for his extensive travels in China as emissary of the Khan. Of the 13th-century capital, Marco Polo wrote that “the whole interior of the city is laid out in squares like a chessboard with such masterly precision that no description can do justice to it” — a pattern Beijing retains to this day.
travel_guides/berlitz2/China-History.txt:But while art and scholarship continued to thrive, the political and military situation deteriorated under the Song. Foreign invaders chipped away at the fringes of the empire. Taxpayers groaned under the burden of the army and the tribute paid to foreign rivals and complained about the luxuries of palace life. Disaster was inevitable: invaders from Manchuria forced the Song to retreat to the south. And the Mongol invaders, headed by the redoubtable Genghis Khan, swept across China, bringing the whole country under foreign rule for the first time.
travel_guides/berlitz2/China-History.txt:The new era, known as the Yuan Dynasty, lasted less than a century. Creativity declined, but the new ruler of China, Kublai Khan (who was grandson of the great Genghis Khan), had an open mind and a generally humane attitude towards his new subjects. He appointed Chinese bureaucrats and scholars to help rule the country. Foreign historians generally conclude that Kublai Khan became an “almost authentic” Chinese emperor, that the conquerors changed more profoundly than the conquered.
travel_guides/berlitz2/China-WhereToGo.txt:Genghis Khan’s Mongol armies leveled Zhongdu in the 13th century, then rebuilt it under the name Dadu (“Great Capital”). By the time Marco Polo arrived, the city outshone the capitals of Europe. The Ming Dynasty transferred most of the imperial pomp south to Nanjing in the 14th century. Predictably, Dadu received yet another name, Beiping (“Northern Peace”) but had to wait more than 50 years to win back its imperial status and a fresh name. This one — Beijing (“Northern Capital”) — is still around. So, happily, are the Ming palaces and temples.
travel_guides/berlitz2/China-WhereToGo.txt:Travelers with more time can venture deeper into the wilderness grasslands, where there is a better chance of sleeping in a real yurt, not one specially furnished for foreign visitors. Other popular destinations west of Hohhot are the Genghis Khan Mausoleum in the Ordoes Highlands (actually built in 1954 and recently augmented with a reconstructed Yuan Dynasty village) and the nearby Resonant Sand Gorge and Wudang Lama Temple.
travel_guides/berlitz2/China-WhereToGo.txt:In the Southern Mountains (Nanshan), 74 km (46 miles) south of Urumqi, the Kazakhs move their families on horseback and set up their yurts on the high pastures to graze their sheep. At the end of the road, near an alpine waterfall, the Kazakhs, who once rode with Genghis and Kublai Khan across these grasslands, open their village to visitors and in July stage a six-day summer fair (nadam) with horse races and wrestling.
```

With the addition of the ```-o``` flag, we can narrow this result down to just the phrase, telling us which files contain "Genghis" as well as the number of times it is shown.

```
$ grep -ro Genghis
travel_guides/berlitz1/HistoryIndia.txt:Genghis
travel_guides/berlitz1/HistoryIndia.txt:Genghis
travel_guides/berlitz2/Beijing-History.txt:Genghis
travel_guides/berlitz2/Beijing-History.txt:Genghis
travel_guides/berlitz2/China-History.txt:Genghis
travel_guides/berlitz2/China-History.txt:Genghis
travel_guides/berlitz2/China-WhereToGo.txt:Genghis
travel_guides/berlitz2/China-WhereToGo.txt:Genghis
travel_guides/berlitz2/China-WhereToGo.txt:Genghis
```

## -v flag

[Source](https://en.wikibooks.org/wiki/Grep)

The ```-v``` flag displays every line that doesn't match with the provided input. This is helpful for when you need to alter lines without a specific word or phrase.

The following is a search for "Americans" in "non-fiction/OUP/Castro/chZ.txt".

```
$ grep Americans non-fiction/OUP/Castro/chZ.txt
A style of suit worn by African Americans, Filipino Americans, and Mexican Americans during the 1930s and 1940s. In Chicano culture this style of dress is primarily associated with the pachucos of the 1940s. The fashion at that time was to wear very baggy pants with pegged legs, long jackets with high and sharp shoulder pads, thick-soled shoes, and long watch chains dangling from the belt. An addition to the whole style common to Chicanos was a particular haircut, long with a ducktail and a wide-brimmed hat.
The word zoot was known within the urban jazz culture of Harlem, and it meant something either exaggerated in performance or in style. Many African Americans wore an extravagant style of clothing, the baggy pegged pants and jackets with padded shoulders, that later became known as the zoot suit. In the novel Invisible Man by Ralph Ellison, he describes the zoot--suiters’ style, “walking slowly, their shoulders swaying, their legs swinging from their hips in trousers that ballooned upward from cuffs fitting snug about their ankles; their coats long and hip-tight with shoulders far too broad to be those of natural western men” (1947, 380). In the late-night jazz scenes of Harlem this style was “a killer-diller coat with a drape-shape, reat-pleats and shoulders padded like a lunatic’s cell” (380). Tyler makes the point that the zoot suit was an extremely symbolic costume, which gave the wearer the look of a child in adult clothing. The broad square shoulders gave a macho look to the youth, and the finger-tipped coat was made for fun and leisure. The long baggy pants were made for dancing, especially the jitterbug, and the wide Panama hats were another sign of adulthood. “The business of fun, dancing and dating were the key characteristics displayed by Zoot-Suiters. It was an escape from drudgery and futile labor to the bliss of free-wheeling movement in the city among youths in the new youth culture” (Tyler, 23). Prominent black entertainers wore the zoot suit, such as Cab Calloway, Sammy Davis Jr., and Duke Ellington. Ellington performed at the Orpheum in Los Angeles in 1941 and 1942 with a musical called Jump for Joy in which the performers wore zoot suits, also known as Gone with the Wind suits, after the style worn by Clark Gable in the movie by the same name.
During the summer of 1943 the attention of the whole country was on Los Angeles when gangs of sailors and zoot-suiters battled with each other in the streets of the city. It is unclear if this was a race riot or a riot of patriotic sailors who attacked, beat, and stripped young Mexican Americans whom they perceived to be unpatriotic zoot-suiters. Between the third and thirteenth of June zoot-suiters were open targets. Much has been written about these riots from both literary and historical perspectives.
```

The following search displays all lines without "Americans" in the same file, which can be helpful for excluding irrelevant information.

```
$ grep -v Americans non-fiction/OUP/Castro/chZ.txt




Zoot Suit
Even though the zoot suit was worn by the young men of several different races and ethnicities, it is primarily identified with the pachucos of Los Angeles. Pachucos were mostly second-generation Mexicans, the sons of migrant laborers and working-class immigrants. Pachucos created their own subculture, an arrogant style of dressing, a bilingual secret argot, and for some individuals membership in petty criminal gangs. The zoot suit became a symbolic disguise that identified the zoot-suiter as neither a Mexican nor an American. It was not a bicultural or binational position, but rather a position between cultures, a “hanging in space” position. The overly confident, slow swagger of the pachuco, today exemplified by the cholo, made it appear in fact as if the zoot-suiter were walking on air.
During the late 1970s the zoot suit received wide recognition and popularity with the production of a successful play by Luis Valdez. In 1981 a film by the same name, Zoot Suit, was produced and directed by Luis Valdez, with performances by actors Daniel Valdez and Edward James Olmos.
See also Cholos; Pachucos
References Barker 1950; Cosgrove 1989; Ellison, 1947; Mazon 1984; Orona-Cordova 1992; Sanchez 1978; Stone 1990; Tyler 1994; Valdez 1992; Zoot Suit 1981
Zozobra
A giant, forty-foot effigy in the form of a puppet, which is burned during the annual Santa Fe Fiesta held in Santa Fe, New Mexico. The word Zozobra translates to “gloom” or “worry” or “anguished.” The Zozobra is ritualistically burned at the beginning of the fiesta, which symbolizes the end of destructiveness, gloom, and worry, setting the tone for a successful fiesta. The creation of Zozobra was introduced into the fiesta in 1926 by Will Shuster, who felt that the fiesta had become “dull and commercialized.” Throughout the years the image of Zozobra changed from a simple twenty-foot puppet to the elaborate forty-foot figure with animated eyes, arms, and mouth that he is today. In 1969 Shuster turned over the responsibility and copyright of Zozobra to the Kiwanis Club of Santa Fe. He is hung on a tall pole on a hill, outside the city, where the burning can be seen by the thousands of people who come to watch. The death of gloom is supposed to resurrect happiness.
In response to the tradition of the burning of Zozobra, a group of New Mexico Chicanos started a tradition of burning El Kookoóee, a figure known by many Chicanos as the bogeyman, during the Festival de Otoño.
See also El Kookoóee; Santa Fe Fiesta
References Cohen 1985; Grimes 1976; Weigle and White 1988
```

The following is a search for "french" in "travel_guides/berlitz1/HandRIbiza.txt".

```
$ grep french travel_guides/berlitz1/HandRIbiza.txt 
        island comes with chips (french fries).
```

The following search shows all lines without "french" in the same file.

```
$ grep -v french travel_guides/berlitz1/HandRIbiza.txt 

  
  
    
      
        Recommended Hotels
        The establishments listed below offer a cross-section of
        local restaurants, and should convince you that not everything on the
        The star rating in brackets after each entry refers to the
        offfical government rating system.
        As a basic guide, the symbols we use indicate what you can
        expect to pay for a three-course meal for two, excluding wine, tax and
        tip. Drinks will add considerably to the final bill.
        ✪less than 5,000 ptas.
        ✪✪5,000–8,000 ptas.
        ✪✪✪more than 8,000 ptas.
```