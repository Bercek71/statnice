![[Okruhy#^a44bb8]]

### Vykonávání dotazů v databázových systémech

Vykonávání dotazů v databázových systémech je komplexní proces, který zahrnuje několik klíčových komponent, jako je fyzický návrh databáze, logické a fyzické operace a optimalizace dotazů. Tyto komponenty společně zajišťují, že dotazy jsou vykonávány efektivně a rychle.

#### Fyzický návrh databáze

Fyzický návrh databáze se zaměřuje na optimální uspořádání dat na úložném médiu. Tento návrh zahrnuje výběr vhodných datových struktur, indexů a strategií ukládání, které zlepšují výkon dotazů.

1. **Tabulky typu Halda (Heap Tables)**:
   - Záznamy jsou ukládány v pořadí, v jakém jsou vkládány, bez specifického uspořádání.
   - Výhody: Rychlé vkládání dat (O(1)).
   - Nevýhody: Pomalejší vyhledávání (O(n)).

2. **Indexované tabulky**:
   - Indexy umožňují rychlé vyhledávání záznamů na základě hodnot v jedné nebo více sloupcích.
   - Typy indexů:
     - **Jednoduché indexy**: Indexy na jednom sloupci.
     - **Složené indexy**: Indexy na více sloupcích.
   - Indexy jsou často implementovány pomocí stromových struktur, jako je B-strom nebo B+-strom.
   - Výhody: Rychlejší vyhledávání (O(log n)).
   - Nevýhody: Vyšší režie při vkládání, aktualizaci a mazání dat.

3. **Clustering**:
   - Záznamy jsou fyzicky uspořádány na disku podle jednoho nebo více sloupců.
   - Výhody: Rychlejší dotazy, které potřebují přistupovat k rozsahu hodnot.
   - Nevýhody: Vyšší režie při vkládání a aktualizaci dat.

4. **Particionování**:
   - Tabulky jsou rozděleny na menší části (partice), které mohou být uloženy a spravovány samostatně.
   - Výhody: Lepší výkon při práci s velmi velkými tabulkami.
   - Nevýhody: Komplexnější správa databáze.

#### Vykonávání dotazů

Vykonávání dotazů zahrnuje několik kroků, které zahrnují překládání SQL dotazů do interní reprezentace, optimalizaci dotazů a vykonání dotazů pomocí logických a fyzických operací.

**1. Překlad dotazu:**
   - SQL dotaz je přeložen do interní reprezentace, často ve formě dotazovacího stromu nebo grafu, který reprezentuje jednotlivé operace dotazu.

**2. Optimalizace dotazu:**
   - Optimalizátor dotazu přetváří dotaz na ekvivalentní, ale efektivnější verzi.
   - Transformace zahrnují například přesun filtrů, použití indexů a eliminaci nepotřebných operací.

**3. Generování plánu dotazu:**
   - Optimalizátor vytváří množinu možných plánů vykonání dotazu a vybírá nejlevnější plán na základě odhadovaných nákladů (např. I/O operace, CPU čas).

**Příklad: Plán dotazu**
```plaintext
SELECT * FROM Student WHERE jméno = 'Jan Novák';
```

1. **Překlad dotazu:**
   - Dotaz je přeložen do interního dotazovacího stromu.

2. **Optimalizace dotazu:**
   - Optimalizátor zjistí, zda existuje index na sloupci `jméno`, který může být použit pro rychlejší vyhledávání.

3. **Generování plánu dotazu:**
   - Možné plány:
     - Full Table Scan: Procházení celé tabulky `Student`.
     - Index Scan: Použití indexu na sloupci `jméno` (pokud existuje).
   - Výběr plánu: Index Scan, pokud existuje vhodný index, jinak Full Table Scan.

#### Logické a fyzické operace

**Logické operace:**
   - Logické operace jsou vysokou úrovní operací, které jsou nezávislé na fyzické implementaci dat. Příklady zahrnují selekci, projekci, joiny, agregace atd.

1. **Selekt (Selection)**:
   - Výběr řádků, které splňují danou podmínku.
   - `σ_{podmínka}(Tabulka)`

2. **Projekce (Projection)**:
   - Výběr specifických sloupců z tabulky.
   - `π_{sloupce}(Tabulka)`

3. **Spojení (Join)**:
   - Kombinace řádků ze dvou tabulek na základě společného atributu.
   - `Tabulka1 ⋈_{podmínka} Tabulka2`

4. **Agregace (Aggregation)**:
   - Výpočet agregačních funkcí, jako je SUM, COUNT, AVG.
   - `γ_{agregace}(Tabulka)`

**Fyzické operace:**
   - Fyzické operace jsou implementace logických operací na úrovni úložiště. Příklady zahrnují sekvenční scan, index scan, nested loop join, sort merge join, hash join atd.

1. **Sekvenční scan (Sequential Scan)**:
   - Prochází všechny záznamy v tabulce.

2. **Index scan (Index Scan)**:
   - Používá index k nalezení specifických záznamů.

3. **Nested Loop Join**:
   - Provádí join pro každou dvojici záznamů z obou tabulek.

4. **Sort Merge Join**:
   - Seřadí obě tabulky podle společného atributu a poté je spojí.

5. **Hash Join**:
   - Používá hash tabulky k urychlení spojení.

#### Shrnutí

Vykonávání dotazů v databázových systémech zahrnuje fyzický návrh databáze, překlad a optimalizaci dotazů a provádění logických a fyzických operací. Tento proces zajišťuje efektivní a rychlé zpracování dotazů, minimalizaci nákladů na I/O a CPU a optimální využití dostupných zdrojů.