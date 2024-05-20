> [!note] Podívat se jak se kreslí
> 

![[Okruhy#^14008a]]

Unified Modeling Language (UML) je standardizovaný jazyk pro specifikaci, vizualizaci, konstrukci a dokumentaci softwarových systémů. UML zahrnuje různé typy diagramů, které poskytují různé pohledy na systém, a je využíván v různých fázích vývoje softwaru. UML lze rozdělit na statické a dynamické diagramy.

### Typy diagramů UML

1. **Statické diagramy**:
   - **Třídní diagram (Class Diagram)**: Zobrazuje statickou strukturu systému pomocí tříd, jejich vlastností, metod a vztahů mezi třídami (dědičnost, asociace, agregace, kompozice).
   - **Objektový diagram (Object Diagram)**: Ukazuje instance tříd v konkrétním okamžiku a jejich vztahy, což pomáhá pochopit strukturu objektů v systému.
   - **Komponentový diagram (Component Diagram)**: Zobrazuje fyzickou architekturu systému a vztahy mezi komponentami (moduly, knihovny, služby).
   - **Nasazovací diagram (Deployment Diagram)**: Ukazuje fyzické nasazení softwarových komponent na hardware (servery, síťové uzly).
   - **Balíčkový diagram (Package Diagram)**: Zobrazuje rozdělení systému do balíčků a závislosti mezi nimi.
   - **Profilový diagram (Profile Diagram)**: Rozšiřuje UML pro konkrétní domény nebo platformy, umožňuje definovat stereotypy a značky.

2. **Dynamické diagramy**:
   - **Sekvenční diagram (Sequence Diagram)**: Zobrazuje interakce mezi objekty v časové posloupnosti, ukazuje zprávy posílané mezi objekty.
   - **Komunikační diagram (Communication Diagram)**: Ukazuje interakce mezi objekty zaměřením na strukturální organizaci, místo časové posloupnosti.
   - **Diagram aktivit (Activity Diagram)**: Modeluje tok činností nebo pracovní postupy v systému, podobný vývojovým diagramům.
   - **Diagram stavů (State Diagram)**: Ukazuje stavy objektu a přechody mezi těmito stavy, obvykle pro modelování chování objektů s komplexním životním cyklem.
   - **Diagram případů užití (Use Case Diagram)**: Zobrazuje funkční požadavky systému pomocí případů užití, aktérů a jejich interakcí.
   - **Časový diagram (Timing Diagram)**: Ukazuje změny stavů nebo podmínek objektů v závislosti na čase, často používaný v reálném čase a embedded systémech.
   - **Interakční přehledový diagram (Interaction Overview Diagram)**: Kombinuje prvky z aktivitních a interakčních diagramů, poskytuje vysokou úroveň přehledu nad interakcemi v systému.

### Statický náhled na systém

Statické diagramy, jako jsou třídové, objektové, komponentové a nasazovací diagramy, poskytují pohled na strukturu systému, jeho architekturu a rozložení komponent. Tyto diagramy jsou užitečné pro:

- **Návrh systému**: Pomáhají při definování tříd a jejich vztahů, při rozdělování systému do modulů a při plánování nasazení.
- **Dokumentace**: Poskytují jasnou a strukturovanou dokumentaci systému, kterou lze použít pro údržbu a další vývoj.
- **Komunikace**: Usnadňují komunikaci mezi členy týmu, zákazníky a dalšími zainteresovanými stranami.

### Dynamický náhled na systém

Dynamické diagramy, jako jsou sekvenční, komunikační, aktivitní, stavové a časové diagramy, modelují chování systému, interakce mezi objekty a toky činností. Tyto diagramy jsou užitečné pro:

- **Analýzu požadavků**: Pomáhají pochopit, jak bude systém reagovat na různé vstupy a jak budou probíhat interakce mezi uživateli a systémem.
- **Návrh chování**: Pomáhají při definování, jak budou jednotlivé komponenty spolupracovat a jak budou zpracovávat různé scénáře.
- **Testování**: Umožňují modelovat testovací scénáře a ověřovat chování systému vůči požadavkům.

### Mapování na zdrojový kód

UML diagramy mohou být mapovány na zdrojový kód následujícími způsoby:

- **Třídové diagramy**: Přímé mapování na definice tříd, atributů a metod ve zdrojovém kódu.
- **Sekvenční a komunikační diagramy**: Můžou být použity k vytvoření skeletonu metod a jejich volání.
- **Diagramy aktivit a stavů**: Mohou být mapovány na implementaci pracovních postupů a stavových automatů v kódu.
- **Komponentové a nasazovací diagramy**: Pomáhají při organizaci kódu do modulů a při přípravě nasazovacích skriptů a konfigurace.

### Využití UML v rámci vývoje

UML je široce využíváno v různých fázích vývoje softwaru:

- **Požadavky**: Diagramy případů užití pomáhají specifikovat a analyzovat požadavky.
- **Návrh**: Statické a dynamické diagramy jsou využívány pro návrh architektury a chování systému.
- **Implementace**: UML diagramy slouží jako základ pro psaní zdrojového kódu a organizaci kódové báze.
- **Testování**: Diagramy aktivit a sekvenční diagramy pomáhají při tvorbě testovacích scénářů.
- **Údržba a dokumentace**: UML poskytuje srozumitelnou a aktualizovanou dokumentaci, která usnadňuje údržbu a další vývoj softwaru.

UML tedy poskytuje všestranný nástroj pro modelování softwarových systémů, který podporuje celý životní cyklus vývoje softwaru od analýzy požadavků po údržbu a dokumentaci.