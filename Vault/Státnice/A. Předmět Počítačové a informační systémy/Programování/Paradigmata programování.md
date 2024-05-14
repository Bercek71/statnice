---
Done: true
---
![[Okruhy#^0ee56a]]

> [!note] **Paradigmata programování** 
> jsou vzorce, nebo modely myšlení při programování. Podle programovacích paradigmat třídíme programovací jazyky

## Deklarativní paradigma

> [!quote] [Wiki](https://cs.wikipedia.org/wiki/Deklarativn%C3%AD_programov%C3%A1n%C3%AD)  
> *__Deklarativní paradigma__ je založeno na myšlence programování aplikací pomocí definic **co se má udělat**, a ne **jak se to má udělat**. Opakem tohoto principu je imperativní programování popisující jednotlivé úkony pomocí algoritmů Zjednodušeně to lze popsat tak, že imperativní programy obsahují algoritmy, kterými se dosáhne chtěný cíl, zatímco deklarativní jazyky specifikují cíl a algoritmizace je ponechána programu (interpretu) daného jazyka.* 
> 
   

Důraz na **co se má udělat**, například:
```sql
SELECT * 
FROM table 
WHERE name = "Karel"
```
U jazyka **SQL** není důležité jak se věci stanou, který algoritmus se použije na vyhledání, ale popisuje pouze co se má stát. SQL je doménově specifický jazyk, neboli jazyk pro řešení konkrétního problému. Tyto jazyky jsou obvykle turingovsky neúplné (není univerzální, nedokáže vyřešit stejné problémy jako turingův stroj).  

- **Specifické vlastnosti:** Programátor popisuje požadovaný výsledek, aniž by podrobně specifikoval, jak má být dosažen.
- **Principy:** Důraz je kladen na popis problému a jeho vztahů, místo na specifikaci postupů. Typickými příklady jsou SQL dotazy nebo deklarativní programování v rámci některých funkcionálních jazyků.

## Imperativní paradigma

Pomocí imperativního programovacího paradigmatu vysvětlujeme počítači, **jak** má věci udělat, tedy postup krok po kroku, jak dosáhnout tíženého výsledku. Základními kameny jsou:
- přiřazení hodnot proměnným (a = 20)
- podmínky (if-else)
- cykly (for, while)
```python
#Příklad
items = [1, 2, 3, 4];
result = 0
for i in items:
	result += i
print(result)
```

Imperativní paradigma je velmi rozšířené a je používáno v mnoha programovacích jazycích, včetně jazyků jako je **C, Java, Python** a mnoho dalších. Jeho hlavní výhodou je přímá kontrola nad tím, jak jsou operace vykonávány, což může být výhodné pro některé typy aplikací, jako jsou systémové programy nebo aplikace s vysokým výkonem.


- **Specifické vlastnosti:** V tomto paradigmatu programátor přímo specifikuje kroky, které počítač musí provést k dosažení požadovaného výsledku.
- **Principy:** Důraz je kladen na manipulaci s proměnnými, přiřazování hodnot, řízení toku programu pomocí podmínek a smyček.

## Strukturované paradigma

Strukturované programování je paradigmatický přístup k psaní programů, který zdůrazňuje používání strukturovaných metod pro návrh a organizaci kódu. Tento přístup se snaží minimalizovat používání nekontrolovaných skoků (např. goto příkazů) a upřednostňuje použití strukturovaných kontrolních struktur, jako jsou podmínky, smyčky a podprogramy.

Zde je několik klíčových prvků strukturovaného programování:

1. **Seřaditelnost (Sequencing)**: Programy jsou psány jako sekvence instrukcí, které jsou vykonávány jeden po druhém, od začátku do konce.
    
2. **Podmíněné zpracování (Conditional Execution)**: Použití podmínek umožňuje programu rozhodnout, které části kódu vykonat na základě aktuálních podmínek.
    
3. **Cykly (Loops)**: Cykly umožňují opakování určitých částí kódu, dokud je splněna určitá podmínka.
    
4. **Strukturované podprogramy (Structured Subroutines)**: Podprogramy nebo funkce jsou používány k rozdělení kódu na menší, snadno spravovatelné části. Tyto podprogramy jsou volány z hlavního programu, což zlepšuje modularitu a znovupoužitelnost kódu.
    
5. **Návraty (Returns)**: Strukturované programování preferuje jednoznačné ukončení podprogramů pomocí návratových instrukcí, což zvyšuje jasnost a přehlednost kódu.
    
6. **Rekurze (Recursion)**: Rekurze, tj. schopnost funkce volat sama sebe, je také součástí strukturovaného programování a může být použita pro řešení určitých problémů.
    
Tento přístup k programování má za cíl zlepšit čitelnost, údržbu a laditelnost kódu tím, že zavádí jasně definované struktury a omezuje nekontrolované skoky, což usnadňuje pochopení a správu programu. Příklady mohou být **Python, C, C++, ADA, Fortran.**

- **Specifické vlastnosti:** Důraz je kladen na strukturované programování, které zahrnuje používání podmínek, smyček a podprogramů pro zlepšení čitelnosti a údržby kódu.
- **Principy:** Hlavním cílem je zlepšit přehlednost a snadnou údržbu kódu pomocí strukturovaných konstrukcí.

```c
// Příklad: Součet prvků v poli pomocí cyklu for
#include <stdio.h>

int main() {
    int numbers[] = {1, 2, 3, 4, 5};
    int sum = 0;
    for (int i = 0; i < 5; i++) {
        sum += numbers[i];
    }
    printf("Součet prvků v poli je: %d\n", sum);
    return 0;
}

```


## Objektově orientované paradigma

Objektově orientované programování (OOP) je paradigmatický přístup k psaní programů, který se zaměřuje na modelování reálného světa pomocí objektů a interakcí mezi nimi. Toto paradigma organizuje kód do objektů, které kombinují data a metody (funkce), které s těmito daty pracují. Zde jsou klíčové prvky objektově orientovaného paradigmatu:

1. **Objekty**: Objekty jsou základní stavební jednotkou objektově orientovaného programování. Každý objekt má svůj stav (data) a chování (metody).
    
2. **Třídy**: Třídy jsou šablony pro vytváření objektů. Definují atributy (data) a metody (funkce), které budou mít objekty dané třídy.
    
3. **Dědičnost (Inheritance)**: Dědičnost umožňuje vytvářet nové třídy (potomky) na základě již existujících tříd (rodičů), přičemž potomci zdědí vlastnosti a chování svých rodičů.
    
4. **Polymorfizmus**: Polymorfizmus umožňuje jedné metodě nebo funkci pracovat s různými typy objektů. To znamená, že stejný kód může být použit s různými typy objektů, což zvyšuje flexibilitu a znovupoužitelnost kódu.
    
5. **Zapouzdření (Encapsulation)**: Zapouzdření umožňuje skrýt vnitřní implementaci objektů a umožňuje přístup k nim pouze prostřednictvím definovaných rozhraní. To pomáhá chránit data objektů a zajišťuje konzistenci a bezpečnost programu.
    

Objektově orientované programování usiluje o vytváření modulárního, snadno udržovatelného a znovupoužitelného kódu tím, že organizuje kód do samostatných a dobře definovaných objektů. Tento přístup se často používá pro větší a komplexnější projekty, kde je důležitá rozsáhlost a organizace kódu. Některé jazyky, jako je Java, C++, Python a C#, mají silnou podporu pro objektově orientované programování.

- **Specifické vlastnosti:** Modeluje programování kolem objektů, které kombinují data a metody pro manipulaci s těmito daty.
- **Principy:** Důraz je kladen na zapouzdření, dědičnost a polymorfismus. Objekty jsou základními stavebními jednotkami programu, které komunikují pomocí zpráv.

```java
// Příklad: Třída reprezentující automobil s vlastnostmi a metodami
public class Car {
    private String brand;
    private String model;
    private int year;

    public Car(String brand, String model, int year) {
        this.brand = brand;
        this.model = model;
        this.year = year;
    }

    public void drive() {
        System.out.println("Jedu autem " + brand + " " + model + " " + year);
    }
    
    public static void main(String[] args) {
        Car myCar = new Car("Toyota", "Corolla", 2022);
        myCar.drive();
    }
}

```

## Funkcionální paradigma

Funkcionální paradigma programování se zaměřuje na vytváření programů pomocí funkcí a vyhýbá se používání stavových proměnných. Zde jsou specifické vlastnosti a principy funkcionálního paradigmatu:

- **Specifické vlastnosti:**
    
    - Funkce jsou považovány za základní stavební kameny programu.
    - Stav programu je minimalizován a měněn pouze při volání funkcí a předávání argumentů.
    - Vedlejší efekty jsou minimalizovány nebo eliminovány.
    - Rekurze je běžně používána pro opakování operací.
- **Principy:**
    
    - **Čistotu funkcí:** Funkce nemají vedlejší efekty, což znamená, že volání funkce s určitými vstupy vždy vrací stejný výstup, a nemění stav programu.
    - **Imutabilitu dat:** Data jsou obvykle neměnná (imutabilní), což znamená, že se nemohou po vytvoření změnit. Namísto toho se vytvářejí nová data na základě stávajících dat.
    - **Vyhodnocování výrazů:** Výrazy jsou vyhodnocovány na základě jejich hodnot a ne na základě stavu programu.
    - **Funkcionální kompozice:** Funkce jsou skládány do větších funkcí pomocí operací jako je kompozice a aplikace.
    - **Lazy vyhodnocování:** V některých funkcionálních jazycích se výrazy nevyhodnocují okamžitě, ale až když jsou potřeba.

Funkcionální paradigma se často používá pro paralelní a distribuované programování, zpracování dat a matematické výpočty, ale lze ji využít pro různé typy aplikací. Jazyky, které podporují funkcionální programování, zahrnují Haskell, Lisp, Scala, F#, Clojure a mnoho dalších.

```haskell
-- Příklad: Funkce na výpočet faktoriálu
factorial :: Integer -> Integer
factorial 0 = 1
factorial n = n * factorial (n - 1)
```
