![[Okruhy#^0457d8]]

#### Relační datový model

**Definice:**
Relační datový model představuje data v podobě tabulek (relací), kde každý řádek tabulky (entita) reprezentuje jeden záznam a každý sloupec (atribut) reprezentuje typ dat. Relační model je založen na teorii množin a predikátové logice.

**Relace:**
Relace je tabulka, která obsahuje data ve formě dvourozměrné matice. Je tvořena řádky a sloupci, kde každý řádek reprezentuje jeden záznam a každý sloupec reprezentuje atribut záznamu.

- **Relační schéma**: Definuje strukturu relace, tedy jména sloupců a jejich datové typy. Např. pro relaci `Student` můžeme mít schéma `Student(id: INTEGER, jméno: VARCHAR, datum_narození: DATE)`.
- **Relační instance**: Konkrétní data uložená v relaci v daném okamžiku.

**Vlastnosti relací:**
1. **Jedinečnost řádků**: Každý řádek v relaci musí být jedinečný. To znamená, že nemůže být více řádků se stejnými hodnotami ve všech sloupcích.
2. **Neuspořádanost řádků a sloupců**: Pořadí řádků a sloupců v relaci nemá význam, což znamená, že přeskupení řádků nebo sloupců nemění logický význam relace.
3. **Atomické hodnoty**: Každá hodnota v relaci musí být atomická, což znamená, že nemůže být dále dělitelná.

**Normální formy:**
Normální formy jsou pravidla pro strukturování databázových tabulek tak, aby se minimalizovala redundance a eliminovaly anomálie při aktualizaci.

1. **První normální forma (1NF):**
   - Každá tabulka má jedinečný název.
   - Každý atribut má jedinečný název.
   - Všechny hodnoty atributů jsou atomické (nedělitelné).

2. **Druhá normální forma (2NF):**
   - Splňuje požadavky 1NF.
   - Každý neklíčový atribut je plně závislý na primárním klíči (žádné parciální závislosti).

3. **Třetí normální forma (3NF):**
   - Splňuje požadavky 2NF.
   - Žádný neklíčový atribut není tranzitivně závislý na primárním klíči (všechny neklíčové atributy závisí přímo na primárním klíči).

4. **Boyce-Coddova normální forma (BCNF):**
   - Splňuje požadavky 3NF.
   - Každý determinant je kandidátní klíč.

**Funkční závislosti:**
Funkční závislost mezi dvěma množinami atributů \(A\) a \(B\) v tabulce znamená, že pro každý řádek, pokud dva řádky mají stejné hodnoty atributů v \(A\), musí mít stejné hodnoty atributů v \(B\). Formálně: \(A \rightarrow B\).

- **Triviální funkční závislost**: Pokud \(B\) je podmnožinou \(A\), pak \(A \rightarrow B\) je triviální funkční závislost.
- **Nettriviální funkční závislost**: Pokud \(B\) není podmnožinou \(A\), pak \(A \rightarrow B\) je netriviální funkční závislost.

**Příklady funkčních závislostí:**
- V tabulce `Student` s atributy `id`, `jméno`, `datum_narození`, funkční závislost `id -> jméno, datum_narození` znamená, že pro každý student s daným `id` existuje jedno `jméno` a jedno `datum_narození`.

#### Objektově-relační datový model

**Základní rysy:**
Objektově-relační datový model (ORDM) rozšiřuje relační model o prvky objektově orientovaného programování, což umožňuje lepší modelování složitých datových struktur a jejich vztahů.

1. **Strukturované datové typy:**
   - Umožňují definovat složené typy s atributy a metodami.
   - Např.: `CREATE TYPE student_type UNDER person_type (...);`
   - **Příklad použití**: Vytvoření datového typu `Address` s atributy `street`, `city`, `zipcode` a metodami pro formátování adresy.

2. **Dědičnost:**
   - Datové typy mohou být organizovány do hierarchií s podporou dědičnosti.
   - Např.: `CREATE TYPE student_type UNDER person_type (...);`
   - **Příklad použití**: Definování typu `UndergraduateStudent` a `GraduateStudent` jako podtypy typu `Student`.

3. **Ukazatele a reference:**
   - Umožňují vytvářet vazby mezi tabulkami pomocí ukazatelů.
   - Např.: `Manager REF person_type;`
   - **Příklad použití**: Modelování vztahu mezi zaměstnanci a jejich nadřízenými pomocí reference `manager REF Employee`.

4. **Kolekce dat:**
   - Umožňují ukládání kolekcí dat (asociativní pole, zahnízděné tabulky, pole).
   - Např.: `TYPE jmeno IS TABLE OF element_type INDEX BY PLS_INTEGER | VARCHAR2(sizevarchar);`
   - **Příklad použití**: Ukládání seznamu telefonních čísel pro každého zákazníka v databázi.

5. **Procedury a triggery:**
   - Kód jako funkce, procedury a triggery je uložený v SŘBD a může být vykonáván na serveru.
   - Např.: `CREATE TRIGGER ...`
   - **Příklad použití**: Definování triggeru, který automaticky aktualizuje stav skladu při vložení nové objednávky.

**Výhody objektově-relačního modelu:**
- **Lepší modelování reálného světa**: Schopnost modelovat složité struktury a vztahy pomocí dědičnosti a složených typů.
- **Zvýšená flexibilita**: Možnost definovat vlastní datové typy a metody.
- **Výkonnostní výhody**: Eliminace potřeby přenášet velké objemy dat mezi klientem a serverem díky funkcím a triggerům běžícím na serveru.

**Nevýhody objektově-relačního modelu:**
- **Složitost**: Vyšší složitost návrhu a údržby databáze.
- **Kompatibilita**: Možné problémy s kompatibilitou mezi různými SŘBD implementacemi objektově-relačních rozšíření.

Tímto způsobem jsou objektově-relační databáze schopny poskytovat vyšší flexibilitu a lepší modelování reálných světů než tradiční relační databáze.