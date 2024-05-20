> [!note] Podívat se na prezentace od kudělky

![[Okruhy#^11fe2f]]

Informační systém je soubor vzájemně propojených komponent, které shromažďují, ukládají, zpracovávají a poskytují informace pro podporu rozhodování, koordinaci, kontrolu, analýzu a vizualizaci v organizaci. Životní cyklus informačního systému zahrnuje několik fází od jeho plánování a vývoje až po údržbu a zlepšování. Návrh a architektura informačního systému jsou klíčové pro zajištění jeho efektivnosti a spolehlivosti.

### Životní cyklus informačního systému

Životní cyklus informačního systému lze rozdělit do několika hlavních fází:

1. **Plánování**:
   - **Náplň**: Identifikace potřeb a cílů organizace, analýza stávajícího systému, stanovení požadavků na nový systém, zvažování alternativ a provádění studie proveditelnosti.
   - **Výstupy**: Plán projektu, specifikace požadavků, studie proveditelnosti, rozpočet a časový plán.

2. **Analýza požadavků**:
   - **Náplň**: Shromažďování a analýza požadavků od uživatelů a dalších zainteresovaných stran, vytváření detailních specifikací a modelů procesů.
   - **Výstupy**: Dokumentace požadavků (např. SRS - Software Requirements Specification), modely procesů, případně prototypy.

3. **Návrh systému**:
   - **Náplň**: Vytváření architektonického návrhu systému, návrh databáze, uživatelského rozhraní a definování technických specifikací. Návrh zahrnuje jak logickou, tak fyzickou architekturu systému.
   - **Výstupy**: Architektonické diagramy, ER diagramy (Entity-Relationship diagramy), návrh databáze, návrhy uživatelského rozhraní.

4. **Implementace**:
   - **Náplň**: Kódování, integrace a testování jednotlivých modulů systému. Programátoři píší zdrojový kód a provádějí jednotkové a integrační testy.
   - **Výstupy**: Zdrojový kód, binární soubory, průběžné verze systému.

5. **Testování**:
   - **Náplň**: Systematické testování systému pro zajištění, že splňuje požadavky a funguje podle specifikací. Zahrnuje různé typy testů (jednotkové, integrační, systémové, akceptační).
   - **Výstupy**: Testovací plány, testovací skripty, zprávy o chybách, výsledky testů.

6. **Nasazení**:
   - **Náplň**: Instalace a konfigurace systému v produkčním prostředí, migrace dat, školení uživatelů a příprava podpůrné dokumentace.
   - **Výstupy**: Nasazený systém, uživatelské příručky, školení materiály.

7. **Údržba a podpora**:
   - **Náplň**: Pravidelná údržba systému, opravy chyb, aktualizace softwaru, zlepšování funkcionalit a poskytování technické podpory uživatelům.
   - **Výstupy**: Opravy chyb, aktualizace, servisní balíčky, záznamy o údržbě.

### Návrh a architektura informačního systému

Návrh a architektura informačního systému zahrnují několik klíčových aspektů:

1. **Logická architektura**:
   - Zahrnuje návrh logické struktury systému, jako jsou třídy, objekty, entity a jejich vztahy. Tato část zahrnuje tvorbu ER diagramů, třídových diagramů a dalších UML diagramů pro modelování struktury systému.

2. **Fyzická architektura**:
   - Zaměřuje se na fyzické komponenty systému, jako jsou servery, databázové systémy, síťová infrastruktura a další hardware. Tato část zahrnuje nasazovací diagramy a diagramy komponent, které ukazují, jak budou fyzické části systému propojeny a jak budou komunikovat.

3. **Architektura aplikace**:
   - Určuje strukturu softwarových komponent a jejich interakce. To zahrnuje definování vrstev architektury (např. prezentační vrstva, aplikační vrstva, databázová vrstva), návrh rozhraní a protokolů pro komunikaci mezi komponentami.

4. **Datová architektura**:
   - Zahrnuje návrh databázových struktur, schémat a způsobů ukládání a přístupu k datům. To zahrnuje normalizaci databází, definování datových modelů a plánování zálohování a obnovy dat.

5. **Bezpečnostní architektura**:
   - Zahrnuje návrh bezpečnostních opatření pro ochranu dat a systémů. To zahrnuje autentizaci, autorizaci, šifrování, zálohování a další bezpečnostní mechanismy.

### Využití návrhu a architektury v rámci vývoje

- **Plánování a analýza**: Logická a fyzická architektura pomáhají v raných fázích projektu při plánování a analýze požadavků. Poskytují přehled o struktuře a komponentách systému, což usnadňuje rozhodování.
- **Návrh a implementace**: Detailní návrhy a modely usnadňují programátorům implementaci systému podle specifikací. Zajišťují, že všechny části systému budou správně integrovány.
- **Testování**: Architektura systému je základem pro vytváření testovacích plánů a scénářů. Pomáhá identifikovat kritické komponenty a závislosti, které je třeba otestovat.
- **Nasazení a údržba**: Fyzická a bezpečnostní architektura jsou klíčové při nasazení systému a jeho údržbě. Zajišťují, že systém bude spolehlivý, bezpečný a snadno udržovatelný.

Informační systém a jeho životní cyklus tedy zahrnují pečlivé plánování, návrh, implementaci, testování, nasazení a údržbu. Kvalitní návrh a architektura jsou klíčové pro úspěšný vývoj a provoz informačního systému, který splňuje potřeby a požadavky organizace.
___

# Informační systém (životní cyklus, návrh a architektura informačního systému)

#### Životní cyklus informačního systému

Životní cyklus informačního systému (IS) se skládá z několika fází, které zajišťují systematický přístup k vývoji a nasazení IS. Tyto fáze jsou:

1. **Vize**:
   - **Náplň**: Identifikace potřeb organizace a definování hlavních cílů IS. Tento krok zahrnuje strategické rozhodnutí, co by měl systém řešit a proč je potřeba.
   - **Výstupy**: Dokument popisující systém z pohledu zákazníka.

2. **Analýza**:
   - **Náplň**: Shromažďování a analýza požadavků uživatelů a dalších zainteresovaných stran. Vytváření use-case modelů a specifikace funkčních požadavků.
   - **Výstupy**: Funkční specifikace, use-case diagramy, diagramy aktivit.

3. **Logický návrh**:
   - **Náplň**: Vytváření modelu domény, který zahrnuje třídní diagramy, vztahy a interakce mezi třídami.
   - **Výstupy**: Návrh doménového modelu (statický diagram tříd, sekvenční diagramy, použité vzory).

4. **Technologický návrh**:
   - **Náplň**: Definování technologických platforem, databázových struktur a rozhraní. Rozhodování o architektuře systému a volbě technologií.
   - **Výstupy**: Technická specifikace, modely komponent a jejich rozhraní.

5. **Vývoj**:
   - **Náplň**: Kódování a integrace jednotlivých komponent podle návrhu. Implementace funkcionalit a propojení systému.
   - **Výstupy**: Zdrojový kód, binární soubory, průběžné verze systému.

6. **Nasazení a provoz**:
   - **Náplň**: Instalace systému v produkčním prostředí, migrace dat, školení uživatelů a spuštění systému. Průběžná údržba a aktualizace systému.
   - **Výstupy**: Nasazený systém, uživatelské příručky, záznamy o údržbě.

#### Návrh a architektura informačního systému

Návrh a architektura IS zahrnují několik klíčových aspektů:

1. **Architektura**:
   - **Definice**: Architektura IS zahrnuje organizaci komponent systému, jejich vzájemné vztahy a vztahy k okolí systému. Zahrnuje také principy návrhu a vývoje systému.
   - **Pohledy na architekturu**:
     - **Doménový pohled**: Z pohledu zákazníka, zahrnuje skupinu souvisejících "věcí" a procesů.
     - **Vývojářský pohled**: Globální struktura systému, chování částí a jejich propojení.
     - **Datový pohled**: Přístup k datům a toky dat v systému.
     - **Fyzický pohled**: Fyzické rozmístění komponent.

2. **Statická vs. dynamická architektura**:
   - **Statická architektura**: Pevná struktura systému, která se nemění za běhu.
   - **Dynamická architektura**: Podporuje vznik a zánik komponent za běhu systému podle předem definovaných pravidel.
   - **Mobilní architektura**: Rozšiřuje dynamickou architekturu o mobilní prvky, které se mohou přesouvat.

3. **Komponenty**:
   - **Definice**: Komponenta je softwarový balík, služba nebo modul, který zajišťuje určitou funkčnost a má definované rozhraní.
   - **Příklady**: Modul pro věrnostní program, databázová služba.

4. **Návrh vs. nasazení**:
   - **Návrh**: Popisuje logickou strukturu systému, jak funguje a s čím pracuje.
   - **Nasazení**: Popisuje, kde systém běží (HW, SW platforma).

5. **Proces návrhu architektury**:
   - **Kroky**:
     1. Identifikace požadavků.
     2. Dekompozice systému do komponent.
     3. Přidělení požadavků k jednotlivým komponentám.
     4. Ověření, že všechny požadavky byly přiděleny.

#### Využití návrhu a architektury v rámci vývoje

- **Plánování a analýza**: Architektura a návrh poskytují základní přehled, který usnadňuje rozhodování a plánování.
- **Návrh a implementace**: Umožňují strukturovaný přístup k implementaci a zajišťují správnou integraci všech částí systému.
- **Testování**: Architektonické modely jsou základem pro vytváření testovacích plánů a scénářů.
- **Nasazení a údržba**: Fyzická a bezpečnostní architektura zajišťují spolehlivost a bezpečnost systému, což je klíčové pro jeho údržbu a provoz.

Na základě prezentací z přednášek a vypracovaných otázek můžeme shrnout, že kvalitní návrh a architektura jsou nezbytné pro úspěšný vývoj a provoz informačního systému, který splňuje požadavky a potřeby organizace.