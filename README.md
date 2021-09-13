# Släktdata
se om vi kan koppla ihop Slaktdata med Wikidata

## Funderingar
1. Se vad som finns i Wikidata som kan hjälpa Släktdata
     1. Modell Arkiv Digital [T199907](https://phabricator.wikimedia.org/T199907) --> matcha NAD med Wikidata objekt och skapa kartor?
     1. Se om data i Wikidata kan använda för att länka vidare ex. med [Hub verktyget](https://hub.toolforge.org/)
        1. scbkod = 156206 --> Wikidata Property:P778 --> https://hub.toolforge.org/P778:156206 --> Wikidata
        2. https://hub.toolforge.org/P778:156206?lang=sv --> sv:Wikipedia
        3. [P5324](https://www.wikidata.org/wiki/Property:P5324) är Riksarkivets NAD egenskap
            1. https://hub.toolforge.org/P778:156206?property=P5324  --> kyrkboken
        2. P625 koordinat
            1. https://hub.toolforge.org/P778:156206?property=P625 --> Open Street Map koordinat kyrkan i församlingen
        1. ersätter = [Property:P1365](https://www.wikidata.org/wiki/Property:P1365) --> en församling ersätter en socken
            1. https://hub.toolforge.org/P778:156206?property=P1365 --> socken
            2. https://hub.toolforge.org/P778:156206?property=P1365|P6303  --> går till [P6303](https://www.wikidata.org/wiki/Property:P6303) som är Anbytarforum
3. Alla yrken finns som textsträngar kan vi extrahera dom och skapa vanligaste yrkena i Kyrkböcerna och lägga till dom till Wikidata... se tankar att få fart på våra institutioner att dela struktur hur yrken för en person beskrivs [salgo60/HISCOKoder](https://github.com/salgo60/HISCOKoder)
4. jag skapar ny en koppling med [Svenskt Porträttarkiv]() där tanken är att med ett klick hämta data/bild se [salgo60/spa2Commons](https://github.com/salgo60/spa2Commons) kan vi göra något liknande? SLäktdata har ett API se test [Jupiter Notebook](https://github.com/salgo60/slaktdata/blob/main/Jupyter/Slaktdata.ipynb)
    
