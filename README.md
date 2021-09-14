# Släktdata - [www.slaktdata.org](https://www.slaktdata.org/)
se om vi kan koppla ihop Släktdata med [Wikidata](https://www.wikidata.org) ([video](https://www.youtube.com/watch?v=m_9_23jXPoE)). Släktdata är kyrkböcker som skrivs av - en rad per person i boken ([json](
https://www.slaktdata.org/?p=getregbyid&sldid=156206_F7_710)). Osäkert hur koppling till plats syns. Vore dock enormt intressant att 
* koppla plats till ISOF platsregister och till [Riksarkivet Toras](https://riksarkivet.se/tora) register
* koppla plats och person till [Hembyggsföreningens nya web](https://www.hembygd.se/shf/plats/1442)
  * i Wikidata har vi kopplat ihop oss med Bygdeband se [salgo60/WikidataBygdeband](https://github.com/salgo60/WikidataBygdeband) den nya Hembyggdsförenings web:en kan hantera plats ex. [plats/438644](https://www.hembygd.se/hallasockenforening/plats/438644) och person [plats/438644/person/84878](https://www.hembygd.se/hallasockenforening/plats/438644/person/84878) rel. enkelt 
* yrken skulle kunna "normaliseras" och dom vanligaste finnas i Wikidata och som artiklar i svenska Wikipedia se [Kategori:Historiska_yrken](https://sv.wikipedia.org/wiki/Kategori:Historiska_yrken)
* dödsorsaker skulle kunna "normaliseras" och finns i Wikidata/Wikipedia se [Kategori:Dödsorsaker](https://sv.wikipedia.org/wiki/Kategori:D%C3%B6dsorsaker) 

## Funderingar
1. Se vad som finns i Wikidata som kan hjälpa Släktdata
     1. Modell Arkiv Digital [T199907](https://phabricator.wikimedia.org/T199907) --> matcha NAD med Wikidata objekt och skapa kartor? se [FB där Arkiv Digital](https://www.facebook.com/arkivdigital/posts/3000089753350216) berättar om den nya funktionalitetem
     1. Se om data i Wikidata kan användas för att länka vidare ex. med [Hub verktyget](https://hub.toolforge.org/)
        1. scbkod = 156206 --> Wikidata Property:P778 --> https://hub.toolforge.org/P778:156206 --> Wikidata "Västerlanda församling"
        2. https://hub.toolforge.org/P778:156206?lang=sv --> sv:Wikipedia
        3. [P5324](https://www.wikidata.org/wiki/Property:P5324) är Riksarkivets NAD egenskap
            1. https://hub.toolforge.org/P778:156206?property=P5324  --> kyrkboken
        2. P625 koordinat
            1. https://hub.toolforge.org/P778:156206?property=P625 --> Open Street Map koordinat kyrkan i församlingen
               1. Intressant att Open Street Map för kyrkan = [way/364562584](https://www.openstreetmap.org/way/364562584) har en koppling till kyrkan = WD [Q10717959](https://www.wikidata.org/wiki/Q10717959)
        1. Kopplingar Riksarkivet finns men borde nog kvalitetssäkras. [Tora](https://riksarkivet.se/tora) har valt att ha ett objekt för både socken och församling vilket känns lite tveksamt... men den används i projekt [SWEPOP](https://swedpop.se/data-description/)
            1. https://hub.toolforge.org/P778:156206?property=P7434 --> NAD plats-ID [P7434](https://www.wikidata.org/wiki/Property:P7434)
            2. https://hub.toolforge.org/P778:156206?property=P4820 ---> Tora [P4820](https://www.wikidata.org/wiki/Property:P4820) SPARQL      
        3. ersätter = [Property:P1365](https://www.wikidata.org/wiki/Property:P1365) --> en församling ersätter en socken
            1. https://hub.toolforge.org/P778:156206?property=P1365 --> socken
            2. https://hub.toolforge.org/P778:156206?property=P1365|P6303  --> går till [P6303](https://www.wikidata.org/wiki/Property:P6303) som är Anbytarforum
            3. https://hub.toolforge.org/P778:156206?property=P1365|P5536  --> går till [P5536](https://www.wikidata.org/wiki/Property:P5536) som är SOFI = ISOF gamla register
                1. Finns ett nytt ISOF namnregister men det blev massa tjafs så jag kopplade inte dom och ingen annan verkar ha gjort det se [länk](https://www.wikidata.org/wiki/Wikidata:Property_proposal/Place#ISOF_Place_(en)_%E2%80%93_(V%C3%A4nligen_%C3%B6vers%C3%A4tt_detta_till_svenska.))
        4. ersatt av = [Property:P1366](https://www.wikidata.org/wiki/Property:P1366) --> distrikt
            1. https://hub.toolforge.org/P778:156206?property=P1366|P6192 --> går till [P6192](https://www.wikidata.org/wiki/Property:P6192) --> Hembygdsportalen

3. Alla yrken finns som textsträngar i Släktdata kan vi extrahera dom och skapa vanligaste yrkena i Kyrkböcerna och lägga till dom till Wikidata... se tankar att få fart på våra institutioner att dela struktur hur yrken för en person beskrivs [salgo60/HISCOKoder](https://github.com/salgo60/HISCOKoder)
4. jag skapar nu en koppling med [Svenskt Porträttarkiv](https://portrattarkiv.se/about) där tanken är att med ett klick hämta data/bild se [salgo60/spa2Commons](https://github.com/salgo60/spa2Commons) kan vi göra något liknande? Släktdata har ett API se test [Jupiter Notebook](https://github.com/salgo60/slaktdata/blob/main/Jupyter/Slaktdata.ipynb)
5. Släktdata har även dödsorsaker som vore trevligt att ha i Wikidata och som artiklar i Wikipedia
   6. Dödsorsaker finns även i [SWEPUB](https://swedpop.se/wp-content/uploads/2021/07/Principles-of-Coding-Cause-of-Death.pdf)  
7. TORA projektet har en kartdel se [toramaptest.riksarkivet.se/view](http://toramaptest.riksarkivet.se/view) 
    1. I Wikidata har vi inte kopplat Tora fullt ut se 590 kopplade objekt på en [karta](http://tinyurl.com/y88mgl2k) 
8. [Svensk Porträttarkiv](https://portrattarkiv.se/about) finns kopplat till några 1000 personer via [P4819](https://www.wikidata.org/wiki/Property:P4819) till Wikidata se [karta](https://query.wikidata.org/embed.html#%23%20Query%20Find%20in%20WikiData%20people%20with%20Svenskt%20Portr%C3%A4ttArkiv%20%0A%23%20Show%20Wikitree%20ID%2C%20Find%20A%20Grave%20ID%20and%20if%20picture%20of%20the%20grave%20exist%0A%23%20version%202%20Google%20map%20link%0A%23defaultView%3AMap%0Aselect%20distinct%20%20%28Sample%28%3FSPA%29%20AS%20%3FSPA%29%20%3Farticle%20%3Fperson%20%3FpersonLabel%20%20%3FpersonDescription%20%20%28Sample%28%3Fpic%29%20as%20%3Fpic%29%20%3Fcoord%20%3Fcoord2%20%3Fcoord3%20%3FSBL%20%3FGeni%20%7B%0A%7B%0A%20%20%20%3Fperson%20wdt%3AP4819%20%3FSPAID%09%09%09%09%09%09%23%20Svenskt%20Portr%C3%A4ttarkiv%0A%20%20%20OPTIONAL%7B%3Fperson%20wdt%3AP3217%20%3FSBLID%7D%20.%09%09%20%20%20%20%23%20SBL%0A%20%20%20OPTIONAL%7B%3Fperson%20wdt%3AP2600%20%3FGeniID%7D%20.%20%20%20%20%20%20%20%20%23%20Geni%0A%20%0A%20%20%20OPTIONAL%7B%20%3Fperson%20wdt%3AP18%20%3Fpic%20.%7D%20%09%09%09%09%09%23%20If%20we%20have%20an%20illustration%0A%20%20%20OPTIONAL%7B%20%3Fperson%20wdt%3AP1442%20%3FpicGrave%20.%7D%20%09%09%09%23%20If%20we%20have%20a%20picture%20of%20the%20grave%0A%20%20%20BIND%20%28URI%28CONCAT%28%22https%3A%2F%2Fsok.riksarkivet.se%2Fsbl%2FPresentation.aspx%3Fid%3D%22%2C%3FSBLID%29%29%20AS%20%3FSBL%29%0A%20%20%20BIND%20%28URI%28CONCAT%28%22https%3A%2F%2Fportrattarkiv.se%2Fdetails%2F%22%2C%3FSPAID%29%29%20AS%20%3FSPA%29%0A%20%20%20OPTIONAL%20%7B%20%20%3Fperson%20wdt%3AP19%20%3Floc%20.%20%09%09%09%23%20P19%20Place%20of%20Birth%0A%20%20%20%20%3Floc%20wdt%3AP625%20%3Fcoord%20%7D%20.%20%20%20%20%09%09%09%09%23%20Get%20coordinates%20from%20Place%20of%20Birth%0A%20%20%20OPTIONAL%20%7B%20%20%3Fperson%20wdt%3AP20%20%3Floc2%20.%20%09%09%09%23%20P19%20Place%20of%20Death%0A%20%20%20%20%3Floc2%20wdt%3AP625%20%3Fcoord2%20%7D%20.%20%20%20%20%09%09%09%09%23%20Get%20coordinates%20from%20Place%20of%20Death%0A%20%20%20OPTIONAL%20%7B%20%20%3Fperson%20wdt%3AP119%20%3Floc3%20.%20%09%09%09%23%20P19%20Place%20of%20Burial%0A%20%20%20%20%3Floc3%20wdt%3AP625%20%3Fcoord3%20%7D%20.%20%20%20%20%09%09%09%09%23%20Get%20coordinates%20from%20Place%20of%20Burial%0A%0A%20%20%20BIND%20%28URI%28CONCAT%28%22https%3A%2F%2Fwww.geni.com%2Fpeople%2F%22%2C%3FGeniID%29%29%20AS%20%3FGeni%29%0A%0A%20%20%20OPTIONAL%20%7B%0A%20%20%20%20%20%20%3Farticle%20schema%3Aabout%20%3Fperson%20.%0A%20%20%20%20%20%20%3Farticle%20schema%3AinLanguage%20%22sv%22%20.%0A%20%20%20%20%20%20%3Farticle%20schema%3AisPartOf%20%3Chttps%3A%2F%2Fsv.wikipedia.org%2F%3E%20.%0A%20%20%20%20%7D%0A%20%20%20OPTIONAL%20%7B%0A%20%20%20%20%20%20%3Farticle%20schema%3Aabout%20%3Fperson%20.%0A%20%20%20%20%20%20%3Farticle%20schema%3AinLanguage%20%22en%22%20.%0A%20%20%20%20%20%20%3Farticle%20schema%3AisPartOf%20%3Chttps%3A%2F%2Fsv.wikipedia.org%2F%3E%20.%0A%20%20%20%20%7D%0A%0A%20%20%20OPTIONAL%20%7B%20%3Fperson%20wdt%3AP106%20%3Fgroup%20.%7D%20%09%09%09%23%20Occupation%20in%20Layer%0A%0A%7D%20%20%20%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22sv%22%2C%22en%22%7D%0A%20%7D%0Agroup%20by%20%3Farticle%20%3Fperson%20%3FpersonLabel%20%20%3FpersonDescription%20%3Fcoord%20%3Fcoord2%20%3Fcoord3%20%3FSBL%20%3FGeni%0AOrder%20by%20%3FpersonLabel) / [blogpost](http://minancestry.blogspot.com/2018/02/svenskt-portrattarkiv_10.html). Jag har nu utvecklat ett Scriopt för att förenkla uppladdning av bilder till Wikicommons se [POC](https://github.com/salgo60/spa2Commons) <-> [bilder uppladdade idag](https://commons.wikimedia.org/w/index.php?title=Special:Search&limit=500&offset=0&ns0=1&ns6=1&ns12=1&ns14=1&ns100=1&ns106=1&search=haswbstatement%3AP4819)
9. ISOF har jag besökt och skissat på detta med namn och dialekter men vi saknar en bra dialog se tankar [T235881](https://phabricator.wikimedia.org/T235881) / [T235738](https://phabricator.wikimedia.org/T235738)
09. Jag nämde projektet [Stadens ansikte](https://stockholmia.stockholm.se/forskning/projekt/stadens-ansikten/?fbclid=IwAR3IPyyBwZa2mQKvrsJ5WQpzcGXvFIPREiCUtTdqJL9cJNDLdf5wtwCKvlY). Jag har bara pratat kort med dom men känns som dom borde koppla er se det jag skrev [T268374](https://phabricator.wikimedia.org/T268374)
10. ?!?!?!?    
11. 
