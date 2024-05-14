---
Done: true
---
![[Okruhy#^0c3410]]


Datové typy jsou základní stavební bloky programovacích jazyků, které určují, jak jsou data reprezentována a jak s nimi může program pracovat. Zde je stručný přehled různých typů:

## Statická a dynamická alokace paměti

- **Statická alokace:** Paměť pro proměnné je přidělena během kompilace a zůstává konstantní během běhu programu. Statické proměnné mají definovanou velikost a rozsah platnosti.
- **Dynamická alokace:** Paměť je přidělena a uvolněna během běhu programu pomocí funkcí jako `malloc` a `free` v jazyce C, nebo pomocí konstrukcí jako `new` a `delete` v jazyce C++.

## **Dynamické typování

- V programovacích jazycích s dynamickým typováním je typ proměnné určen až v době běhu programu, nikoli v době kompilace. Proměnné mohou měnit svůj datový typ během provádění programu.


## **Životní cyklus paměti:**

-  Životní cyklus paměti určuje, jak dlouho jsou data v paměti platná. Může se lišit v závislosti na tom, zda jsou data uložena na zásobníku (lokální proměnné funkcí) nebo na haldě (dynamicky alokované proměnné).


## **Jednoduché, strukturované, abstraktní a generické typy**

- **Jednoduché typy:** Také známé jako primitivní typy, jako například celá čísla, desetinná čísla, znaky atd.
- **Strukturované typy:** Tyto zahrnují pole, struktury a třídy, které umožňují seskupení různých datových typů do jedné entity.
- **Abstraktní typy:** Tyto typy poskytují abstrakci nad konkrétními datovými typy a implementují určitou funkcionalitu, aniž by poskytovaly podrobnosti o své vnitřní implementaci.
- **Generické typy:** Generické typy umožňují definovat typy nezávislé na konkrétním datovém typu. Jsou často používány v jazycích jako Java nebo C#.


## **Kolekce**

- Kolekce jsou datové struktury, které umožňují ukládat a manipulovat soubory dat. Mohou zahrnovat seznamy, pole, mapy, fronty atd.
- obvykle je možné nějakým způsobem kolekcemi iterovat v javě třída `Iterable`  


## **Soubory a streamy**

- **Soubory:** Umožňují ukládání dat na trvalé úložiště jako pevný disk. Programy mohou číst data ze souborů a zapisovat do nich.
- **Streamy:** Streamy jsou obecně kanály pro přenos dat. Mohou zahrnovat nejen soubory, ale také síťové připojení, standardní vstup a výstup (stdin, stdout), paměťové proudy atd. Používají se pro asynchronní a sekvenční zpracování dat. Jsou jako proud, takže obvykle co je přečteno se rovnou zpracuje a nedá se k tomu lehce znova přistoupit. 