# Släktdata
se om vi kan koppla ihop Slaktdata med Wikidata

## Funderingar
1. Se vad som finns i Wikidata som kan hjälpa Släktdata
     1. Modell Arkiv Digital [T199907](https://phabricator.wikimedia.org/T199907) --> matcha NAD med Wikidata objekt och skapa kartor?
     1. Se om data i Wikidata kan använda för att länka vidare ex. med [Hub verktyget](https://hub.toolforge.org/)
        1. scbkod = 156206 --> Wikidata Property:P778 --> https://hub.toolforge.org/P778:156206 --> Wikidata "Västerlanda församling"
        2. https://hub.toolforge.org/P778:156206?lang=sv --> sv:Wikipedia
        3. [P5324](https://www.wikidata.org/wiki/Property:P5324) är Riksarkivets NAD egenskap
            1. https://hub.toolforge.org/P778:156206?property=P5324  --> kyrkboken
        2. P625 koordinat
            1. https://hub.toolforge.org/P778:156206?property=P625 --> Open Street Map koordinat kyrkan i församlingen
               1. Intressant att Open Street Map för kyrkan = [way/364562584](https://www.openstreetmap.org/way/364562584) har en koppling till kyrkan = WD [Q10717959](https://www.wikidata.org/wiki/Q10717959)
        1. Kopplingare Riksarkivet finns men borde nog kvalitetssäkras. [Tora](https://riksarkivet.se/tora) har valt att ha ett objekt för både socken och församling vilken känns lite tveksamt... men den används i projekt [SWEPOP](https://swedpop.se/data-description/)
            1. https://hub.toolforge.org/P778:156206?property=P7434 --> NAD plats-ID [P7434](https://www.wikidata.org/wiki/Property:P7434)
            2. https://hub.toolforge.org/P778:156206?property=P4820 ---> Tora [P4820](https://www.wikidata.org/wiki/Property:P4820) SPARQL      
        3. ersätter = [Property:P1365](https://www.wikidata.org/wiki/Property:P1365) --> en församling ersätter en socken
            1. https://hub.toolforge.org/P778:156206?property=P1365 --> socken
            2. https://hub.toolforge.org/P778:156206?property=P1365|P6303  --> går till [P6303](https://www.wikidata.org/wiki/Property:P6303) som är Anbytarforum
            3. https://hub.toolforge.org/P778:156206?property=P1365|P5536  --> går till [P5536](https://www.wikidata.org/wiki/Property:P5536) som är SOFI = ISOF gamla register
                1. Finns ett nytt ISOF namn register men det blev massa tjafs så jag kopplade inte dom och ingen annan verkar ha gjort det se [länk](https://www.wikidata.org/wiki/Wikidata:Property_proposal/Place#ISOF_Place_(en)_%E2%80%93_(V%C3%A4nligen_%C3%B6vers%C3%A4tt_detta_till_svenska.))
        4. ersatt av = [Property:P1366](https://www.wikidata.org/wiki/Property:P1366) --> distrikt
            1. https://hub.toolforge.org/P778:156206?property=P1366|P6192 --> går till [P6192](https://www.wikidata.org/wiki/Property:P6192) --> Hembygdsportalen

3. Alla yrken finns som textsträngar i Släktdata kan vi extrahera dom och skapa vanligaste yrkena i Kyrkböcerna och lägga till dom till Wikidata... se tankar att få fart på våra institutioner att dela struktur hur yrken för en person beskrivs [salgo60/HISCOKoder](https://github.com/salgo60/HISCOKoder)
4. jag skapar ny en koppling med [Svenskt Porträttarkiv]() där tanken är att med ett klick hämta data/bild se [salgo60/spa2Commons](https://github.com/salgo60/spa2Commons) kan vi göra något liknande? SLäktdata har ett API se test [Jupiter Notebook](https://github.com/salgo60/slaktdata/blob/main/Jupyter/Slaktdata.ipynb)
5. Släktdata har även dödsorsaker som vore trevligt att ha i Wikidata och som artiklar i Wikipedia
1. ?!?!?!?    
