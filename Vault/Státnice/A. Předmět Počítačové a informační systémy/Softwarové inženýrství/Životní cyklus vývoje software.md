![[Okruhy#^2cc71b]]

Životní cyklus vývoje softwaru zahrnuje několik fází, které představují strukturovaný přístup k vytváření softwarového produktu. Tyto fáze jsou navrženy tak, aby zajistily systematický a efektivní vývoj softwaru, minimalizovaly rizika a zajistily, že konečný produkt splňuje požadavky zákazníka. Typické fáze životního cyklu vývoje softwaru zahrnují:

1. **Požadavky a analýza**:
   - **Náplň**: Shromažďování a analýza požadavků od zákazníků a dalších zainteresovaných stran. Tento proces zahrnuje pochopení potřeb a očekávání, definování funkcionalit a stanovení rozsahu projektu.
   - **Výstupy**: Dokumenty specifikující požadavky (např. SRS - Software Requirements Specification), modely procesů a případně prototypy.

2. **Návrh**:
   - **Náplň**: Vytvoření architektonického návrhu systému, který zahrnuje rozdělení systému na moduly, definování databázových struktur, návrh uživatelského rozhraní a určení technologií.
   - **Výstupy**: Architektonické a detailní návrhy, UML diagramy, specifikace rozhraní a datové modely.

3. **Implementace**:
   - **Náplň**: Kódování podle návrhových specifikací. Programátoři píší zdrojový kód, integrují různé moduly a testují jednotlivé komponenty.
   - **Výstupy**: Zdrojový kód, binární soubory a průběžné verze softwaru.

4. **Testování**:
   - **Náplň**: Verifikace a validace softwaru. Testování zahrnuje jednotkové testy, integrační testy, systémové testy a akceptační testy. Cílem je najít a opravit chyby, zajistit kvalitu a ověřit, že software splňuje požadavky.
   - **Výstupy**: Testovací plány, testovací skripty, zprávy o chybách a výsledky testů.

5. **Nasazení**:
   - **Náplň**: Instalace a konfigurace softwaru v produkčním prostředí. Zahrnuje také migraci dat a případné školení uživatelů.
   - **Výstupy**: Instalovaný software, dokumentace k nasazení, uživatelské příručky.

6. **Údržba**:
   - **Náplň**: Oprava chyb, aktualizace softwaru, přidávání nových funkcionalit a zajištění podpory pro uživatele. Údržba také zahrnuje monitorování výkonu systému a zálohování dat.
   - **Výstupy**: Opravy chyb, aktualizace, servisní balíčky.

## Základní modely vývoje softwaru

Existuje několik základních modelů vývoje softwaru, které se liší svým přístupem k organizaci a řízení jednotlivých fází životního cyklu:

1. **Vodopádový model**:
   - Sekvenční model, kde každá fáze musí být dokončena před přechodem na další. Je vhodný pro projekty s dobře definovanými požadavky, které se během vývoje nemění.
   - Výhody: Jednoduchost, snadná kontrola a sledování pokroku.
   - Nevýhody: Nízká flexibilita, obtížné řešení změn v požadavcích.

2. **Iterativní a inkrementální model**:
   - Vývoj probíhá v opakovaných cyklech (iteracích), kde každá iterace zahrnuje analýzu, návrh, implementaci a testování části systému. Každá iterace přidává inkrement nové funkčnosti.
   - Výhody: Flexibilita, možnost průběžného zlepšování a rychlejší dodání funkčního softwaru.
   - Nevýhody: Možnost vzniku technického dluhu, potřeba dobrého řízení iterací.

3. **Agilní modely (např. Scrum, Kanban)**:
   - Zaměřují se na flexibilitu, průběžnou zpětnou vazbu a časté dodávání funkčního softwaru. Týmy pracují v krátkých cyklech (sprintech) a pravidelně vyhodnocují a přizpůsobují svůj postup.
   - Výhody: Vysoká adaptabilita na změny, důraz na spolupráci a kvalitu.
   - Nevýhody: Potřeba zkušeného týmu, možné problémy se škálováním na velké projekty.

4. **Spirálový model**:
   - Kombinuje prvky vodopádového a iterativního modelu, klade důraz na analýzu rizik. Vývoj probíhá ve spirálách, kde každá spirála zahrnuje plánování, analýzu rizik, vývoj a hodnocení.
   - Výhody: Řízení rizik, flexibilita a možnost postupného zlepšování.
   - Nevýhody: Složitost, vyšší náklady na řízení.

5. **V-model**:
   - Rozšíření vodopádového modelu, kde testovací fáze jsou naplánovány paralelně s odpovídajícími vývojovými fázemi. Každá fáze má své testovací aktivity.
   - Výhody: Jasné propojení mezi vývojovými a testovacími fázemi, důraz na kvalitu.
   - Nevýhody: Podobné jako u vodopádového modelu, nízká flexibilita.

Každý model má své výhody a nevýhody a je vhodný pro různé typy projektů v závislosti na jejich specifikách, požadavcích a rizicích.