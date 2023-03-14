# Lab Report 5 - Revisiting Report 3

## Overview - The less command

In our last encounter with Lab Report 3, we visited the ```grep``` command, taking a look at the ```-n```, ```-h```, ```-o,``` and ```-v``` flags. In this lab report, we will be a taking a look at several flags for the ```less``` command. More specifically, we will be looking at the ```-X```, ```-I```, ```-p```, and ```-F``` flags. For convenience, each command will be run in the ```docsearch/written_2``` directory.

## ```-X``` flag

[Source](https://linuxize.com/post/less-command-in-linux/)

Normally, when you exit ```less```, the text that was shown on your screen will be removed. The ```-X``` flag makes it so that the text remains on your screen after exiting less. This can be helpful if you need to keep a specific portion of a file in your terminal for later use.

In the following example, we use ```less non-fiction/OUP/Berk/ch1.txt```, and the following is shown:

```
In my three decades of teaching university courses in child development, I have come to know thousands of students, many of whom were parents or who became parents soon after completing my class. I also served on boards of directors and advisory committees for child-care centers, preschools, elementary schools, and parent organizations. And my research continually drew me into classrooms, where for countless hours I observed and recorded preschool and school-age children’s activities, social interactions, and solitary behaviors, in hopes of answering central questions about how they learn.
As a byproduct of those experiences, parents repeatedly approached me with concerns about how to foster their child’s development in the early years. Their fervent questions, at times riddled with doubt and anxiety, revealed that creating optimum learning environments for young children at home—and ensuring their access to development-enhancing experiences in child care, preschool, and school—have become mounting parental challenges.    
Consider the following problematic situations that parents recently raised with me:

•Bob and Sharon, parents of a 4-year-old: Our daughter, Lydia, could recite her ABCs and count from 1 to 20 by age 2 1/2. When we looked for a preschool, many programs appeared to do little more than let children play, so we chose one with lots of emphasis on academics. To me, Lydia’s preschool seems like great preparation for kindergarten and ﬁrst grade, but each morning, Lydia hates to go. Why is Lydia, who’s always been an upbeat, curious child, so unhappy?
•Angela, mother of a 4-year-old and 6-year-old: My husband and I have demanding careers and need to bring work home in the evenings. I’ve read that it’s the quality of time we spend with our children that’s important, not the quantity. We try hard to give Victor and Jeannine our undivided attention, but they’re often whiny, demanding, and quarrelsome. Many times we end up sending them to their rooms or letting them watch TV, just to get some peace after a long day. What’s the best way to create quality parent–child time?
```

When we exit ```less``` however, we only see the following in the terminal:

```
less non-fiction/OUP/Berk/ch1.txt
```

This changes when we add the ```-X``` flag. The output above still displays in ```less```, but exiting now shows:

```
less -X non-fiction/OUP/Berk/ch1.txt




In my three decades of teaching university courses in child development, I have come to know thousands of students, many of whom were parents or who became parents soon after completing my class. I also served on boards of directors and advisory committees for child-care centers, preschools, elementary schools, and parent organizations. And my research continually drew me into classrooms, where for countless hours I observed and recorded preschool and school-age children’s activities, social interactions, and solitary behaviors, in hopes of answering central questions about how they learn.
As a byproduct of those experiences, parents repeatedly approached me with concerns about how to foster their child’s development in the early years. Their fervent questions, at times riddled with doubt and anxiety, revealed that creating optimum learning environments for young children at home—and ensuring their access to development-enhancing experiences in child care, preschool, and school—have become mounting parental challenges.    
Consider the following problematic situations that parents recently raised with me:

•Bob and Sharon, parents of a 4-year-old: Our daughter, Lydia, could recite her ABCs and count from 1 to 20 by age 2 1/2. When we looked for a preschool, many programs appeared to do little more than let children play, so we chose one with lots of emphasis on academics. To me, Lydia’s preschool seems like great preparation for kindergarten and ﬁrst grade, but each morning, Lydia hates to go. Why is Lydia, who’s always been an upbeat, curious child, so unhappy?
•Angela, mother of a 4-year-old and 6-year-old: My husband and I have demanding careers and need to bring work home in the evenings. I’ve read that it’s the quality of time we spend with our children that’s important, not the quantity. We try hard to give Victor and Jeannine our undivided attention, but they’re often whiny, demanding, and quarrelsome. Many times we end up sending them to their rooms or letting them watch TV, just to get some peace after a long day. What’s the best way to create quality parent–child time?
```

In the following example, we use ```less travel_guides/berlitz1/HistoryMadrid.txt```, displaying: 

```
A BRIEF HISTORY
        Though prehistoric remains from the Paleolithic, Neolithic,
        and Bronze Ages have been unearthed in the Manzanares Valley, prior to
        Madrid’s sudden elevation to capital city in 1561 its history was
        rather undistinguished.
        Over a period of many centuries crucial in Spanish history,
        Madrid’s significance was negligible. The Romans built their most
        advanced outpost on the Iberian peninsula, but left nothing of
        consequence in Madrid. Armies of North African nomads, intent on
        disseminating Islam, invaded the peninsula in a.d. 711. Within 10
        years, they had overrun most of Spain. If Madrid played any role in
        these pivotal events, no record of it remains.
        The first solid references to this obscure settlement on the
        Castilian plateau, guarded by the looming Guadarrama mountain range,
        appear in the 9th century. The Arabic name for “place of many springs,”
        variously recorded as Magerit, Mayrit or Magrit, eventually evolved
        into Madrid. The hamlet entered historical chronicles for its military
```

When we exit, however, the same thing happens as in the first example. All this text is gone:

```
less travel_guides/berlitz1/HistoryMadrid.txt
```

When adding ```-X```, we are able to retain all of this information: 

```
less -X travel_guides/berlitz1/HistoryMadrid.txt





        A BRIEF HISTORY
        Though prehistoric remains from the Paleolithic, Neolithic,
        and Bronze Ages have been unearthed in the Manzanares Valley, prior to
        Madrid’s sudden elevation to capital city in 1561 its history was
        rather undistinguished.
        Over a period of many centuries crucial in Spanish history,
        Madrid’s significance was negligible. The Romans built their most
        advanced outpost on the Iberian peninsula, but left nothing of
        consequence in Madrid. Armies of North African nomads, intent on
        disseminating Islam, invaded the peninsula in a.d. 711. Within 10
        years, they had overrun most of Spain. If Madrid played any role in
        these pivotal events, no record of it remains.
        The first solid references to this obscure settlement on the
        Castilian plateau, guarded by the looming Guadarrama mountain range,
        appear in the 9th century. The Arabic name for “place of many springs,”
        variously recorded as Magerit, Mayrit or Magrit, eventually evolved
        into Madrid. The hamlet entered historical chronicles for its military
```

## ```-I``` flag

[Source](https://linuxopsys.com/topics/less-command-in-linux)

Once inside ```less```, you have the option of searching for text using ```/[text]```. The ```-I``` flag of the ```less``` command makes the search ignore cases. This can be helpful if you are looking for a particular phrase but are unsure of or do not care about its case.

For this example, we will be running ```less travel_guides/berlitz1/HandRHawaii.txt```:

```
Oahu (Including Honolulu)
        Aston Waikiki Sunset $$$ 229 Paoakalani Avenue, Honolulu, HI
        96815; Tel. (808) 922-2700 or (800) 336-5599; fax (808) 922-8785;
        <www.aston-hotels.com>. One of Aston’s many condominium resort
        properties, this modern high-rise has large rooms with complete
        kitchens. Lanais afford views of the Diamond Head end of Waikiki Beach.
        410 rooms.
        Halekulani $$$$ 2199 Kalia Road, Honolulu, HI 96815; Tel.
        (808) 923-2311 or (800) 367-2343; fax (808) 926-8004;
        <www.halekulani.com>. Very large rooms, most facing the ocean,
        and luxurious bathrooms with robes, make this a “House Befitting
        Heaven,” the meaning of its Hawaiian name. With plenty of beachfront, a
        top French restaurant (La Mer), and the serene House Without A Key
        outdoor lounge for sunset drinks, Halekulani is a complete resort. 454
        rooms.
        Hilton Hawaiian Village $$$–$$$$ 2005 Kalia Road, Honolulu,
        HI 96815; Tel. (808) 949-4321 or (800) 445-8667; fax (808) 947-7898;
```

When searching for "kalia" (```/kalia```), we are met with the following despite there being several instances of "Kalia" present in the text.

```
Pattern not found  (press RETURN)
```

When we run the command with the ```-I``` flag and search for "kalia", we get the same output (with some additional lines and the top moved so that the first instance of kalia is at the top), but all instances of "Kalia", regardless of case highlighted instead of a notification of no pattern found.


In the following example, we will run ```less non-fiction/OUP/Berk/ch2.txt```, which results in the following:

```
Talia and Jim’s fear of helping 7-year-old Anselmo with his homework, lest they create a dependent, immature child, is a peculiarly Western—and profoundly American—preoccupation. American middle-class parents typically regard young children as dependent beings who must be urged toward independence. In response to researchers’ queries, they frequently say that babies should be trained to be self-reliant from the ﬁrst few months.1 Consequently, they place a high value on children’s learning and doing on their own. Repeatedly relying on others for assistance is construed as weakness, uncertainty, and lack of capacity. In keeping with this view, many American parents worry that if their children seek help, they may become dependent.
A similar view permeates traditional classrooms, where an individualistic value system prevails. Children must “do their own work.” In the most intensely individualistic of these settings, conferring with your neighbor is worse than dependency; it is cheating, and teachers go so far as to set up barriers between pupils, such as upright books and cardboard screens, to prevent it.
This emphasis on independent accomplishment is not broadly accepted around the world. Indeed, adults in some non-Western cultures regard American parents as rather merciless in pushing their young children toward independence—for example, when they insist that infants sleep alone rather than with their parents, or when they take pleasure in the earliest possible mastery of motor skills, such as crawling and walking, long before the child has acquired the reasoning powers to avoid steep staircases and busy roadways.2
Diverse non-Western peoples and American ethnic minorities stress interdependence—that children must feel intimately linked to others to become competent and self-reliant. Chinese, Japanese, Vietnamese, Guatemalan-Mayan, eastern Kentucky Appalachian, and many other cultural groups regard newborn infants as psychologically separate beings whose most important task is to develop an interdependent relationship with their community—an emotional and social foundation that is crucial for survival and learning.3 Witness the following conclusion by a researcher who compared American with Japanese infant rearing practices: “An American mother–infant relationship consists of two individuals . . . a Japanese mother–infant relationship c
```

When searching for "Permeates" with ```/Permeates```, we are met with: 

```
Pattern not found  (press RETURN)
```

When ```less``` is modified with ```-I```, we are met with a similar situation to the first example, where the top is shifted so that the first instance of "Permeates" (not case sensitive) is at the top of the terminal (resulting in a similar output to the code block above), and with all instances of "Permeates" highlighted.

## ```-p flag```

[Source](https://www.educba.com/less-command-in-linux/)

The ```-p``` flag alters the initial output that you recieve so that the first line shown contains the first instance of a given string. This can be useful for skipping over sections of text to find something specific.

In this example, we will run ```less travel_guides/berlitz2/Portugal-History.txt```, which shows the beginning of the file:

```
A Brief History
T he early history of Portugal is closely related to that of the entire Iberian peninsula. Prehistoric cultures flourished first in the north and in today’s Alentejo region of south-central Portugal. The south was visited by a number of peoples who came primarily to trade, including the Phoenicians, the Mycenaean Greeks, and the Carthaginians. The Phoenicians established a trading post at Lisbon around 1200 b.c, calling it either Alis Ubbo or Olissipo. When Celtic peoples crossed the Pyrenees in the first millennium b.c., they intermarried with the existing Iberian population and built a series of hilltop fort communities or citânias, the finest example of which is at Briteiros (see page 73).
The Carthaginians, under Hannibal, recruited locals to fight as mercenaries against Rome. The Romans eventually defeated the Carthaginians and invaded the Iberian peninsula. Their occupation was fiercely opposed by a confederation of Celts, known as the Lusitani, living in central Portugal. The Lusitanian leader, Viriathus, kept the Roman forces at bay until he was assassinated in 139 b.c.
The Romans cultivated grapes, wheat, and olives; built roads; and bequeathed the Latin foundations of the Portuguese language and a strong base of Christian belief. Julius Caesar founded many cities, including Ebora (Évora), where the remains of a Roman temple survive (see page 90), and Pax Julia (Beja).
The Moors and the Reconquest
In a.d. 711 a great Muslim invasion fleet from North Africa crossed the Strait of Gibraltar. In a matter of only a few years, the Moors had conquered almost all of Iberia, except for the small Christian kingdom of Asturias in northern Spain. Lisbon became a thriving outpost under Muslim occupation.
The Moors failed to penetrate much further north than Aveiro about halfway up the Atlantic Coast. They settled in the Alentejo, along the Tagus river, and in the Algarve (which they named al-Gharb, or “Western Land”). By the mid-ninth century, al-Gharb had become a Moorish kingdom, with a capi
```

When we add ```-p "Atlantic Ocean"```, we skip to the first instance of "Atlantic Ocean" and ignore everything prior to this line:

```
With Portugal facing the Atlantic Ocean , rather than the Mediterranean Sea, it remained cut off from most trade routes. However, as the Ottoman Turks in the 15th century dominated the Mediterranean and shipbuilding technology improved, longer Atlantic journeys became a serious prospect. Peace with Spain in 1411 prompted Portugal to seek overseas conquests.
Prince Henry retired to what was known as the “end-of-the-world,” the Sagres peninsula in the Algarve (see page 101). There he established a school of navigation that attracted astronomers, cartographers, and other leading scientists of the day. Henry established expeditions that ultimately succeeded in redefining Europeans’ very understanding of the world. During Henry’s lifetime, Portuguese caravels sailed far beyond the westernmost point of Africa. With the colonization of Madeira and the Azores, the foundations were laid for the future Portuguese empire. The Portuguese also sailed down the west coast of Africa, going beyond Cape Bojador in 1434, a feat theretofore considered to be impossible.
Henry died in 1460, but Portugal’s discovery voyages continued. The king who ruled over the golden age of exploration — and exploitation — was Manuel I “The Fortunate,” who reigned from 1495–1521. The many important discoveries that were made during his reign would assure his position as Europe’s richest ruler: He could well afford to erect monuments as elegant as the Tower of Belém and as impressive as the Jerónimos Monastery in Lisbon.

The architecture that eased Portugal from the Gothic into the Renaissance still bears his name: the Manueline style is whimsically flamboyant and decorative, and rife with references to the sea.
The most significant expedition under Manuel’s flag was Vasco da Gama’s legendary sea voyage from Lisbon in the summer of 1497 — immortalized in The Lusiads (1572), the epic poem by Portugal’s national poet, Luís de Camões (1524–1580). Rounding what is now known as the Cape of Good Hope, da Gama found what Columbus had been searching for in 1492 (although in the wrong direction): the sea-route to the lucrative spices of the East. The Portuguese thus ended the Venetian monopoly on Eastern trade and began attracting merchants from all over Europe to Lisbon.
Portugal and Spain, the planet’s foremost maritime powers, agreed to divide the world between them by means of the 1494 Treaty of Tordesillas. This accorded everything lying more than 370 leagues west of the Cape Verde Islands to Spain, while everything lying to the east went to Portugal, thus giving Portugal a free hand in exploiting the Orient. In 1500, Portuguese explorer Pedro Álvares Cabral accidentally reached Brazil.
Trading posts were set up all along the west and east coasts of Africa, in the Middle East (Hormuz), southern India (Goa), Malaysia (Malacca), and
```

In the following example, we will run ```less non-fiction/OUP/Fletcher/ch10.txt```, resulting in:

```
A specter is haunting Europe,” Karl Marx and Frederick Engels wrote in 1848, as the first sentence of The Communist Manifesto. The specter they had in mind eventually became a political movement that came to dominate nearly half the world in the twentieth century. Behind this movement, however, lay an even more powerful idea that Marx had inspired—a Marxist conception of reality. The marketplace of economic relationships is not what it seems to be. Workers enter into seemingly voluntary contracts with employers, but underlying this system of apparent cooperation is a vast system of exploitation. Those who hold capital reap profits off the backs of those whom they hire as their laborers. This generates a dynamic of history that should, according to the theory, eventually produce a revolution by the exploited class of laborers. This theory failed to recognize the just contribution of capital in generating the opportunity to work, and the political incarnation of Marxism turned out to be historically more transient than expected. Nonetheless, the insight remains with us that relationships of employment—indeed all forms of relationship—require more than nominal consent to be legitimate. Behind the appearance of voluntary interaction there lurks the ever-present possibility of unjust exploitation.
The Marxist challenge was but the beginning of a continuing critique of the idea of freedom, so revered at the close of the eighteenth century. Behind the nominal appearance of freedom lies a structure of influence, a set of conditions that influences people to make the choices they do. Sometimes these influences are morally desirable. Peer group and family pressure can lead people to finish their university degree or to stay in difficult marriages or to remain loyal when tempted to act in self-interest. Looking back, individuals who make these choices under social influence are often grateful for the external inducement to do the right thing. Yet, economic and social conditions can also lead people to enter into socially and economically oppressive relationships, abusive marriages, and postures of dependence on drugs and alcohol. They can be induced to undress and prostrate themselves on stages in front of booths with one-way windows. The fact that people are influenced by others or their economic and emotional needs is, in itself, morally neutral, but the results can vary widely.
```

When adding ```-p "Paradox", we can skip the first paragraph to when "Paradox" is first mentioned:

```
The Paradox of Freedom

This is the paradox of freedom in modern times. We still believe that freedom is the great contribution of American democracy to the culture of the West. “Freedom” was our rallying cry in the decades-long battle against the political enemy that Ronald Reagan labeled the “evil empire.” Although Martin Luther King, Jr. dreamed of a society committed to the proposition that would realize the American vision of equality under law, the word that would sound from the mountaintops would not be “equality” but “freedom.” “Let freedom ring,” King reminds us in the memorable refrain of his dream. In his choice of words, King harks back to Lincoln, who recognized our commitment to the proposition that all men are created equal but hoped that the emancipation would generate “a new birth of freedom.”
We may be willing to die in the name of freedom, but we can no longer pretend that we live in the uncomplicated moral world of the eighteenth century. In a post-Marxist world, we know that freedom requires more than the experience of choosing. We cannot escape our recognition that nominal freedom leads, sometimes, to exploitation and oppression.
The late eighteenth century was indeed a marvelously simplistic time. Adam Smith could write, in the same year as the Declaration of Independence, of the wonders of a free market, based on the voluntary cooperation of producers and consumers, and its invisible hand that would produce the maximum possible welfare for humankind.1 Immanuel Kant could glorify freedom in his theory of law, published in 1795, a theory based on the absolute right to enter into any contract that one chooses to make.2 And, of course, the great monuments to the eighteenth-century understanding of freedom are the Constitution and the Bill of Rights. These documents are revered because they are designed to protect the individual sphere of freedom from a presumptively aggressive and overreaching central government. The basic freedoms protected in the first Ten Amendments, ratified in 1791, include freedom of speech and the press, freedom of religion, the right to bear arms, the right to privacy against state intrusion in one’s home and papers, and a plethora of rights designed to protect suspects of crime against the federal government’s power to investigate and prosecute. All of these freedoms or rights are understood to be a matter of opposition of the individual against the government. They imagine a dyadic conception of government—the individual pitted against the state.
The significant feature of our basic freedoms—apart from the franchise and those that arise in the criminal process—is that we can imagine enjoying
```

## ```-F``` flag

Sometimes, opening ```less``` can cause more work if everything fits on one screen since you have to exit ```less```. A solution to this is the ```F``` flag, with will exit ``less``` and keep the contents in the terminal if the contents fit your terminal size.

For this example, we will run ```less travel_guides/berlitz1/HandRHongKong.txt```, which will display the following within ```less```:

```
Recommended Hotels
        Hong Kong has some of the most luxurious hotels in the
        world, with representatives from all the major international chains.
        Hotels listed below have full air-conditioning, offer 24-hour or
        limited room service, and a wide range of facilities. Hong Kong hotels
        have excellent business services and conference facilities; many have
        shopping malls.
        Reservations are strongly recommended, particularly in
        summer and at Christmas. If you do arrive without making advance
        arrangements, the Hong Kong Hotel Reservation Center at the
        International Airport will be happy to arrange accommodations for you
        on your arrival.
        As a basic guide, the symbols below have been used to
        indicate high-season rates in Hong Kong dollars, based on double
        occupancy, with bath or shower. Unless otherwise noted, hotels take all
        major credit cards. A 10% service charge and 5% government tax will be
        added to the bill.
        $$$$above HK$2,500
        $$$HK$l,600 to HK$2,500
        $$HK$950 to HK$1,600
        $below HK$950
```

This does provide the the entirety of the content within the file, but now you must exit ```less``` with ```:q```. Once you do exit, the contents are not kept in the terminal.

Running the same command with ```-F``` produces the following: 

```
less -F travel_guides/berlitz1/HandRHongKong.txt

  
  
    
      
        Recommended Hotels
        Hong Kong has some of the most luxurious hotels in the
        world, with representatives from all the major international chains.
        Hotels listed below have full air-conditioning, offer 24-hour or
        limited room service, and a wide range of facilities. Hong Kong hotels
        have excellent business services and conference facilities; many have
        shopping malls.
        Reservations are strongly recommended, particularly in
        summer and at Christmas. If you do arrive without making advance
        arrangements, the Hong Kong Hotel Reservation Center at the
        International Airport will be happy to arrange accommodations for you
        on your arrival.
        As a basic guide, the symbols below have been used to
        indicate high-season rates in Hong Kong dollars, based on double
        occupancy, with bath or shower. Unless otherwise noted, hotels take all
        major credit cards. A 10% service charge and 5% government tax will be
        added to the bill.
        $$$$above HK$2,500
        $$$HK$l,600 to HK$2,500
        $$HK$950 to HK$1,600
        $below HK$950
```

Not only are we not in ```less```, but the contents are also printed to the terminal.

For the next example, we will run ```less travel_guides/berlitz1/HandRLisbon.txt```:

```
Recommended Hotels
        Hotel prices in Lisbon have risen in recent years to match
        most western European destinations, even surpassing popular cities like
        Barcelona at the top levels. Many hotels offer special packages (such
        as summer or weekend reductions).
        Central Lisbon covers the area from the waterfront, Bairro
        Alto, Lapa, and Avenida da Liberdade. North Lisbon refers to the area
        around and beyond Praça Marquês de Pombal. Pousadas, found beyond
        Lisbon, are government-owned hotels and inns; the ones listed occupy
        historic buildings, and their restaurants are usually among the town’s
        best.
        The price indication given is for a double room, with
        breakfast, including service and taxes (currently 5 percent of room
        price) in high season (generally April–October).
        $$$$$over 40,000 esc
        $$$$30,000–40,000 esc
        $$$20,000–30,000 esc
        $$12,000–20,000 esc
        $ below 12,000 esc
```

Similarly to the first example, all of the text is displayed within ```less```; however, we are still in ```less```, requiring us to exit and creating unnecessary work.

By adding the ```-F``` flag, we instead get the contents within the terminal because of how short it is:

```
less -F travel_guides/berlitz1/HandRLisbon.txt





        Recommended Hotels
        Hotel prices in Lisbon have risen in recent years to match
        most western European destinations, even surpassing popular cities like
        Barcelona at the top levels. Many hotels offer special packages (such
        as summer or weekend reductions).
        Central Lisbon covers the area from the waterfront, Bairro
        Alto, Lapa, and Avenida da Liberdade. North Lisbon refers to the area
        around and beyond Praça Marquês de Pombal. Pousadas, found beyond
        Lisbon, are government-owned hotels and inns; the ones listed occupy
        historic buildings, and their restaurants are usually among the town’s
        best.
        The price indication given is for a double room, with
        breakfast, including service and taxes (currently 5 percent of room
        price) in high season (generally April–October).
        $$$$$over 40,000 esc
        $$$$30,000–40,000 esc
        $$$20,000–30,000 esc
        $$12,000–20,000 esc
        $ below 12,000 esc
```

## Conclusion

Now you are able to manpiulate the ```less``` command to better suit your needs!