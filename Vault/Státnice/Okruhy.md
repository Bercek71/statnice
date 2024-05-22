
## A. Předmět Počítačové a informační systémy
___
### Programování (FPR, UPR, OOP, SJ, C#/JAVA I a II, UTI, ZDS)

- Paradigmata programování (deklarativní a imperativní, funkcionální, strukturované a objektově orientované paradigma, specifické vlastnosti a principy jednotlivých paradigmat). ^0ee56a
- Datové typy (statická a dynamická alokace, dynamické typování, životní cyklus paměti, jednoduché, strukturované, abstraktní a generické typy, kolekce, soubory, streamy). ^0c3410
- Programovací techniky (řídící struktury, funkce, jejich parametry a návratové hodnoty, rekurze, polymorfismus, kolekce, výjimky a jejich strukturovaná obsluha, paralelismus a vlákna). ^e2dd01
- Vývoj aplikací (C#/Java, typový systém, virtuální stroj a kompilace, tvorba uživatelského rozhraní, delegáty a události, přístup k databázím, práce s textovými daty, asynchronní programování, serializace, síťová komunikace). ^7396e7
- Reprezentace čísel v počítači (číselné soustavy a převody, celá čísla, čísla s pevnou řádovou čárkou, čísla s pohyblivou řádovou čárkou vyjádřená v binárním, decimálním a hexadecimálním základu, aritmetika s čísly v různých reprezentacích, kódování znaků). ^1b393e


> [!question] __Příklad otázky__
> *Jako programátor máte vyřešit úlohu předávání dat mezi dvěma aplikacemi. Jaké formy předávání dat/komunikace mezi aplikacemi znáte, na základě čeho byste vybrala/vybral nejvhodnější formu a jak byste ji realizovala/realizoval ve vámi zvoleném programovacím jazyce?*


### Softwarové inženýrství (SWI, VIS)

- Životní cyklus vývoje software (typické fáze, jejich náplň, základní modely vývoje). ^2cc71b
- UML (typy diagramů, statický náhled na systém, dynamický náhled na systém, mapování na zdrojový kód, využití v rámci vývoje). ^14008a
- Informační systém (životní cyklus, návrh a architektura informačního systému). ^11fe2f
- Návrhové vzory a praktiky pro vývoj informačních systémů (vzory GoF, doménová logika, datové zdroje, objektově-relační chování a struktury, doménově specifické jazyky). ^43b07f

> [!question] __Příklad otázky__ 
> *Vysvětlete, v jaké situaci je vhodné použít vzor Composite, použijte UML diagram pro jeho schématické vyjádření a promítněte tento diagram do zdrojového kódu ve vámi zvoleném programovacím jazyce.*

### Databázové systémy (DS I, DS II)

- Datové modely (relační datový model: definice, normální formy, funkční závislosti; objektově- relační datový model: základní rysy).• ^0457d8
- Dotazovací jazyky (SQL: jazyk pro definici dat, jazyk pro manipulaci s daty, SELECT – spojení, poddotazy, agregační funkce; procedurální rozšíření SQL: PL/SQL, T/SQL, obecné rysy: uložené procedury, kurzory, triggery). ^66df3a
- Analýza informačního systému (konceptuální a datový model, stavová analýza, funkční analýza – minispecifikace, návrh formulářů). ^666d02
- Transakce (definice, ACID, serializovatelnost transakcí, zotavení, řízení souběhu, úroveň izolace transakcí). ^99db54
- Vykonávání dotazů v databázových systémech (fyzický návrh databáze, vykonávání dotazů, logické a fyzické operace). ^a44bb8
- Návrh a implementace datové vrstvy (objektově-relační mapování, DTO, DAO, efektivní implementace datové vrstvy). ^631b5b

> [!question] __Příklad otázky__ 
> *Jaký SQL dotaz může v transakci vracet neočekávané výsledky, pokud použijeme úroveň izolace Read Commited? Popište i relaci se kterou pracujete a napište konkrétní dotaz nad touto relací.*


### Architektury počítačů a operační systémy (APPS, OSY)

- Architektury počítačů (základní architektury počítačů, jejich popis, výhody a nevýhody, princip fungování počítače, způsoby adresování, hierarchické uspořádání pamětí). ^fa5554
- RISC procesory (základní konstrukční vlastnosti, způsoby urychlování práce procesorů, zřetězené zpracování instrukcí, predikce skoků). ^027f95
- GPU, CUDA (důvody využívání GPU, popis technologie CUDA, postup výpočtu, základní pravidla programování, postup výpočtu, práce s pamětí). ^0b33c9
- Procesy (vytváření procesů, implementace procesů v OS, tabulka procesů, stavy procesů, obsluha HW přerušení, multitasking, pseudoparalelismus, plánovací algoritmy). ^00091d
- Meziprocesní komunikace (souběh, kritická sekce, vzájemné vyloučení, základní způsoby realizace vzájemného vyloučení, semafor, monitor, fronta zpráv, sdílená paměť). ^19fd67
- Správa paměti (princip fungování virtuální pamětí, segmentace a její přínosy, správa/evidence volné paměti). ^eb409f

> [!question] __Příklad otázky__ 
> *Vysvětlete princip fungování virtuální paměti a k čemu slouží segmentace. Co tyto technologie zlepšují či přináší proti základní koncepci fungování počítače dle von Neumanna?*


### Počítačové sítě a komunikační technologie (POS, PB)

- Směrování a přepínání v počítačových sítích (topologie LAN sítí; aktivní prvky a jejich funkce – přepínač a jeho funkce, směrovač; směrovací protokoly – základní popis, třídy směrovacích protokolů, hierarchické směrování). ^c621e9
- Protokolová rodina TCP/IP (TCP/IP model a jeho vztah k referenčnímu modelu ISO‐OSI; síťové protokoly – IPv4 vs. IPv6; protokoly transportní vrstvy a princip fungování spolehlivého přenosového kanálu protokolu TCP). ^53b405
- Služby Internetu a jejich protokoly (elektronická pošta; protokol HTTP; DNS – typy záznamů, doménový strom, zóny, zabezpečení DNS; SSH). ^d4c323
- Základy kryptografie (blokové a proudové šifry včetně jejich režimů; symetrická a asymetrická kryptografie a jejich využití; hashovací funkce; infrastruktura veřejného klíče – základní pilíře, certifikační autorita, certifikát veřejného klíče). ^c62e63
- Tvorba bezpečných aplikací (obecné principy; nejčastější zranitelnosti, jejich kategorizace a popis; bezpečnost databází a webových aplikací a typické útoky na ně). ^747c1d
- Bezpečnost počítačových sítí (útoky na infrastrukturu, servery a aplikační protokoly, a jejich detekce; paketové filtry, stavový firewall; virtuální privátní sítě). ^91ccf4

>[!question] __Příklad otázky__ 
>*Proč se dnes používá pro komunikaci s webovými servery převážně HTTPS?Jakému typu útoku má bránit, jakou bezpečnostní funkci má primárně zajistit, a jaký význam pro komunikaci se HTTPS servery má certifikační autorita?*


### Počítačová grafika (ZPG, URO)
- Metody a nástroje pro realizaci grafických uživatelských rozhraní (kognitivní schopnosti člověka, mentální modely, základní pravidla designu, barevné prostory, volba barev a prezentace textu). ^d05c2c
- Standardní zobrazovací řetězec (realizace jednotlivých kroků řetězce, modelovací a zobrazovací transformace, Phongův osvětlovací model, řešení viditelnosti, identifikace těles, stručná charakteristika standardu OpenGL a jazyka GLSL). ^fab820
- Geometrické modelování (afinní a projektivní prostory, popis těles a možnosti jejich reprezentace, základní křivky používané v počítačové grafice, jejich vyjádření, vlastnosti a použití, Fergusonova kubika, Bézierova křivka). ^574e1d

>[!question] __Příklad otázky__  
>*Popište možnosti reprezentace těles a způsob jejich vykreslení pomocí standardního zobrazovacího řetězce v kontextu grafického rozhraní OpenGL.*

## B. Předmět Teoretické základy informatiky
___

### Algoritmy (ALG I, ALG II, ZSU, UTI

- Strategie algoritmického řešení problémů (strategie řešení hrubou silou, úplným prohledáváním, sniž a vyřeš, rozděl a panuj, transformuj a vyřeš, záměna paměťové a časové složitosti, dynamické programování, hladové algoritmy).
- Složitost algoritmů (asymptotická notace, korektnost algoritmů a její analýza). 
- Základní datové struktury (pole, seznam, zásobník, fronta, graf, vyhledávací strom, hašovací tabulka, halda).
- Explorativní analýza dat (data a jejich vlastnosti – numerické, kategoriální a jiné atributy, statistické vlastnosti dat, vztahy mezi atributy). 
- Metody strojového učení (shlukování, klasifikace, vyhodnocení algoritmů).

> [!question] __Příklad otázky__ 
> *Základní myšlenka strategie rozděl a panuj. Praktická ukázka použití, QuickSort a jeho časová složitost. Srovnání se strategií řešení hrubou silou, BubbleSort.*


### Teoretická informatika (ULM, ZDS, UTI, PJP)

- Logika (výroková logika a predikátová logika, syntaxe a sémantika formulí výrokové a predikátové logiky, sémantické a syntaktické dokazování, ekvivalentní úpravy, rezoluční metoda).
- Booleova algebra (Booleova funkce, minimalizace, vazba na kombinační obvody).
- Množiny, relace a funkce (operace na množinách, druhy a vlastnosti relací, relace typu, ekvivalence a uspořádání, vlastnosti funkcí, induktivní definice, a důkazy).
- Teorie formálních jazyků a automatů (formální jazyky, operace na jazycích, formální prostředky používané pro popis jazyků – automaty, gramatiky, regulární výrazy, konečné, deterministické a nedeterministické automaty, bezkontextové gramatiky, zásobníkové automaty, Chomského hierarchie).
- Vyčíslitelnost a složitost (výpočetní modely – stroje RAM, Turingovy stroje, výpočetní složitost algoritmů, algoritmicky nerozhodnutelné problémy, třídy složitosti, třídy PTIME, NPTIME a PSPACE, převody mezi problémy, NP-úplné a PSPACE-úplné problémy).
- Překladače (základní funkce a typy překladačů, fáze při překladu, formální prostředky využívané při tvorbě překladače, speciální podtřídy bezkontextových gramatik jako např. LL1 a regulární výrazy, techniky používané při implementaci jako např. rekurzivní sestup, generátory překladačů).

>[!question] __Příklad otázky__ 
>*Bezkontextové gramatiky a jejich souvislost se zásobníkovými automaty. Využití bezkontextových gramatik a zásobníkových automatů při konstrukci překladačů.*


### Matematika pro informatiku (MA I, MA II, LA, DIM)

- Diskrétní matematika (posloupnosti, rekurentní rovnice, kombinatorické výběry, diskrétní pravděpodobnost, řešení kongruencí).
- Teorie grafů (grafy, vzdálenost v grafu, míry souvislosti, stromy a kostry, barvení grafů a jejich aplikace, toky v sítích).•
- Lineární algebra (matice a maticové operace, inverzní matice, úpravy a řešení soustav lineárních rovnic, vektorové prostory a báze vektorových prostorů, lineární zobrazení, spektrální teorie).
- Diferenciální a integrální počet funkcí jedné proměnné (posloupnosti, limita a spojitost, derivace, extrémy, neurčité a určité integrály).
- Diferenciální a integrální počet funkcí více proměnných (parciální derivace, gradient, extrémy, dvojné a trojné integrály).

>[!question] __Příklad otázky__ 
>*Jako analytik máte navrhnout optimální přiřazení úkolů jednotlivým pracovním týmům. Jakým grafem budete problém modelovat? Jaké aspekty problému charakterizuje hrana, barvení hran, stupeň vrcholu? Jak při řešení využijete toky v sítích?*
