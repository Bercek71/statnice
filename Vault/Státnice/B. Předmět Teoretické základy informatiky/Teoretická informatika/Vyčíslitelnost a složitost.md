![[Okruhy#^6407da]]

### Vyčíslitelnost a složitost

Vyčíslitelnost a složitost se zabývají studiem toho, co lze vypočítat a jak efektivně lze tyto výpočty provádět. To zahrnuje modely výpočtů, výpočetní složitost algoritmů, algoritmicky nerozhodnutelné problémy a klasifikaci problémů do různých tříd složitosti.

#### Výpočetní modely

1. **Stroje RAM**:
   - **Registr Access Machine (RAM)**: Teoretický model počítače, který se skládá z centrální procesorové jednotky (CPU) a paměti organizované jako pole registrů.
   - Instrukce v RAM zahrnují načítání, ukládání, aritmetické a logické operace, skoky a podmíněné skoky.
   - RAM model se používá pro analýzu algoritmů s ohledem na skutečné počítače.

2. **Turingovy stroje**:
   - Turingův stroj je teoretický model výpočtu, který se skládá z pásky (paměti), řídicí jednotky s konečným počtem stavů a hlavy, která může číst a zapisovat symboly na pásku a pohybovat se doleva nebo doprava.
   - Turingovy stroje se používají k definici algoritmické vyčíslitelnosti a jako základ pro teorii výpočetní složitosti.

#### Výpočetní složitost algoritmů

Výpočetní složitost se zabývá zdroji (časem a prostorem), které jsou potřebné k provedení algoritmů.

1. **Časová složitost**:
   - Měří, jak se počet kroků algoritmu zvyšuje s velikostí vstupu.
   - Často se používá asymptotická notace, jako je $O(n)$, $O(n^2)$, $O(\log n)$, apod.

2. **Prostorová složitost**:
   - Měří množství paměti, kterou algoritmus potřebuje vzhledem k velikosti vstupu.
   - Podobně jako časová složitost se používají asymptotické notace.

#### Algoritmicky nerozhodnutelné problémy

Některé problémy nelze algoritmicky rozhodnout. To znamená, že neexistuje algoritmus, který by mohl správně odpovědět na všechny možné vstupy za konečný čas.

- **Problém zastavení (Halting Problem)**: Zjištění, zda daný Turingův stroj zastaví na daném vstupu.
  - Alan Turing dokázal, že problém zastavení je nerozhodnutelný.

#### Třídy složitosti

Třídy složitosti kategorizují problémy podle zdrojů, které jsou potřebné k jejich řešení.

1. **PTIME (P)**:
   - Třída problémů, které lze vyřešit deterministickým Turingovým strojem v polynomiálním čase.
   - Příklady: Třídění, hledání nejkratší cesty v grafu.

2. **NPTIME (NP)**:
   - Třída problémů, pro které lze řešení ověřit deterministickým Turingovým strojem v polynomiálním čase.
   - NP-problémy mohou být vyřešeny nedeterministickým Turingovým strojem v polynomiálním čase.
   - Příklady: Problém splnitelnosti (SAT), problém obchodního cestujícího (TSP).

3. **PSPACE**:
   - Třída problémů, které lze vyřešit deterministickým Turingovým strojem v polynomiálním prostoru.
   - Příklady: Quantified Boolean Formula (QBF).

#### Převody mezi problémy

Převody mezi problémy hrají klíčovou roli v teorii složitosti, protože umožňují ukázat, že řešení jednoho problému lze převést na řešení jiného problému.

- **Redukce**: Převod jednoho problému na jiný tak, aby řešení druhého problému poskytlo řešení prvního problému.

#### NP-úplné a PSPACE-úplné problémy

1. **NP-úplné problémy (NP-complete)**:
   - Problémy v NP, na které se všechny ostatní NP-problémy mohou polynomialně redukovat.
   - Pokud existuje polynomiální algoritmus pro jeden NP-úplný problém, pak existuje polynomiální algoritmus pro všechny NP-problémy.
   - Příklady: SAT, TSP (Hamiltonian Path).

2. **PSPACE-úplné problémy (PSPACE-complete)**:
   - Problémy v PSPACE, na které se všechny ostatní PSPACE-problémy mohou polynomialně redukovat.
   - Příklady: QBF, Generalized Geography.

### Shrnutí

Vyčíslitelnost a složitost se zabývají tím, co lze vypočítat a jak efektivně lze tyto výpočty provádět. Různé modely výpočtů, jako jsou Turingovy stroje a RAM, poskytují základy pro analýzu algoritmů. Třídy složitosti, jako jsou P, NP a PSPACE, klasifikují problémy podle zdrojů potřebných k jejich řešení. Algoritmicky nerozhodnutelné problémy ukazují limity toho, co lze algoritmicky vyřešit, a převody mezi problémy jsou klíčové pro porozumění vztahům mezi různými problémy. Pokud máš další otázky nebo potřebuješ podrobnější vysvětlení, neváhej se zeptat!