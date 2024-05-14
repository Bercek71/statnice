---
Done: true
---
![[Okruhy#^e2dd01]]

## Řídící struktury

Řídící struktury jsou základními stavebními kameny algoritmů v programování. Pomáhají programu provádět různé akce podle určitých podmínek. Existují tři hlavní typy řídících struktur:

- **Podmíněné struktury**: Nejčastější formou podmíněných struktur je `if-else`. Tato struktura umožňuje provádět kód v závislosti na pravdivosti určité podmínky. Alternativně můžete použít `switch-case`, který umožňuje vyhodnotit výraz a provést odpovídající kód na základě jeho hodnoty.
    
- **Cykly**: Cykly umožňují opakovat část kódu několikrát. Nejběžnější cykly jsou `for`, `while` a `do-while`. Cyklus `for` se používá, když je známo, kolikrát se má kód opakovat. `While` cyklus se používá, když není známo, kolikrát se má kód opakovat, ale podmínka musí být splněna. Cyklus `do-while` je podobný cyklu `while`, ale garantuje, že se kód vykoná alespoň jednou, než se podmínka ověří.
    
- **Skoky**: Skoky umožňují přeskočit určitou část kódu. Příklady skoků zahrnují `break`, který ukončuje cyklus, `continue`, který přeskočí zbytek aktuální iterace cyklu, a `return`, který okamžitě ukončuje funkci a vrací hodnotu.
    

## Funkce

Funkce jsou bloky kódu, které provádějí určitou činnost a mohou být volány z jiných částí programu. Funkce mohou mít parametry, které jsou vstupními hodnotami, a mohou vracet hodnotu jako svůj výstup. Funkce mohou být buď vestavěné (např. funkce pro práci s řetězci, matematické funkce atd.) nebo uživatelsky definované.

## Rekurze

Rekurze je technika, kde funkce volá sama sebe. Tento přístup se často používá k řešení problémů, které mají podobnou strukturu, jako například problémy na základě rozdělení a panování. Každé rekurzivní volání snižuje velikost problému, dokud není dosažena podmínka ukončení, která zabrání nekonečné rekurzi.

## Polymorfismus

Polymorfismus umožňuje používat objekty s rozdílnou implementací pomocí stejného rozhraní. Statický polymorfismus je dosažen přetížením funkcí nebo operátorů, zatímco dynamický polymorfismus je dosažen pomocí dědičnosti a virtuálních funkcí, což umožňuje objektům různých tříd používat stejné metody.

## Kolekce

Kolekce jsou datové struktury, které umožňují ukládat a manipulovat s více prvky dat. Běžné typy kolekcí zahrnují pole, seznamy, spojové seznamy, fronty, zásobníky, mapy a mnoho dalších. Každý typ kolekce má své vlastnosti a vhodné použití podle konkrétních potřeb.

## Výjimky a jejich strukturovaná obsluha

Výjimky jsou neočekávané situace, které mohou nastat během běhu programu. Jsou způsobeny chybami v kódu nebo vnějšími faktory, jako je chybný vstup od uživatele nebo nedostupnost sítě. Strukturovaná obsluha výjimek umožňuje programátorům zachytit a řídit tyto situace pomocí bloků `try-catch`, což umožňuje programu pokračovat ve správném chodu i při výskytu chyb.

## Paralelismus a vlákna

Paralelismus je technika, která umožňuje programu provádět několik úloh současně. Vlákna jsou jednotky výpočtu, které mohou být prováděny nezávisle. Paralelní programování může zlepšit výkon a využití systémových prostředků, ale vyžaduje pečlivou správu sdílených zdrojů a synchronizaci mezi vlákny. Používání knihoven a frameworků pro paralelní programování může usnadnit tuto složitou práci a umožnit programátorům využívat výhody paralelismu efektivně.