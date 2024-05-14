---
Done: true
---
![[Okruhy#^1b393e]]
## Číselné soustavy
___

### Binární soustava

- Binární soustava je základem pro reprezentaci čísel v počítačích.
- Každé číslo se reprezentuje pomocí kombinace bitů, kde každý bit může být buď 0 nebo 1.
- Hodnota každého bitu je mocninou čísla 2, přičemž nejnižší bit má nejnižší hodnotu a každý další bit má hodnotu dvojnásobku předchozího bitu.
- Například: Binární číslo 1011 znamená $1\cdot2^3 + 0\cdot2^2 + 1\cdot2^1 + 1\cdot2^0 = 11$ v desítkové soustavě.

### Decimální soustava

- Standardní číselná soustava, kterou používáme v každodenním životě.
- Má základ 10, což znamená, že používáme deset symbolů (0 až 9).
- Každá pozice v čísle má hodnotu mocniny čísla 10.
- Například: Číslo 123 znamená $1\cdot10^2 + 2^\cdot10^1 + 3\cdot10^0 = 123$.

### Hexadecimální soustava:

- Používá 16 symbolů, včetně číslic 0 až 9 a písmen A-F.
- Je často používána pro zjednodušení a zkrácení dlouhých binárních řetězců.
- Každý symbol má hodnotu mocniny čísla 16.
- Například: Číslo A1 v hexadecimální soustavě znamená $10\cdot16^1 + 1\cdot16^0 = 161$ v desítkové soustavě.

## Převody mezi soustavami
___
### Binární na desítkovou:

- Každému bitu přiřadíte hodnotu na základě jeho pozice (mocniny čísla 2) a následně sečtete všechny hodnoty.

### Desítkovou na binární:

- Číslo postupně dělíte 2 a zaznamenáváte zbytek až do doby, kdy dělení nedá nulu.

### Binární na hexadecimální a zpět:

- Binární číslo se rozdělí do skupin po čtyřech bitů, každá skupina se převede na odpovídající hexadecimální symbol.

### Hexadecimální na binární a zpět:

- Každý hexadecimální symbol se převede na ekvivalentní binární číslo a naopak.

## Aritmetika s čísly
___
### Sčítání:

- Provádí se podobně jako sčítání v desítkové soustavě, počínaje nejnižšími řády a přenesením případného přetečení na vyšší řády.

### Odčítání:

- Používá se doplňkový kód a postupuje se obdobně jako u sčítání, přičemž lze využít přenosu při odečítání.

### Násobení a dělení:

- Provádí se postupným posouváním jednoho z operandů vlevo (násobení) nebo vpravo (dělení) a přičítáním (násobení) nebo odečítáním (dělení).

- [ ] Naučit se tyto operace

## BCD (Binary Coded Decimal)
___
- Je to způsob kódování desítkových čísel pomocí binárních číslic.
- Každá desítková číslice (0 až 9) je kódována čtyřbitovým binárním číslem (0000 až 1001).
- Například: Číslo 25 je kódováno jako 0010 (pro 2) a 0101 (pro 5).

## Dvojkový doplněk (Two's Complement)
___

- Dvojkový doplněk je způsob reprezentace záporných čísel v binární soustavě.
- Pro kladná čísla se používá klasická binární reprezentace.
- Pro záporná čísla se používá doplněk k jedničce.
- To znamená, že k zápornému číslu se přičte jeho absolutní hodnota představovaná v binární podobě.
- Například: Pro číslo -5, binární reprezentace čísla 5 je 0101, takže dvojkový doplněk čísla -5 je 1011.

## Čísla s plovoucí desetinnou čárkou
___
- Čísla s plovoucí desetinnou čárkou jsou reprezentována v počítači pomocí tzv. formátu s plovoucí řádovou čárkou (floating-point format).
- Nejčastěji používaným standardem pro reprezentaci čísel s plovoucí desetinnou čárkou je standard IEEE 754.
- Tento standard definuje formát, který zahrnuje znaménko, exponent a mantisu.
- Mantisa představuje samotné číslo, exponent určuje, kam se čárka posune, a znaménko označuje, zda je číslo kladné nebo záporné.
- Při provádění aritmetických operací s čísly v tomto formátu se používají speciální algoritmy, které zohledňují rozdíly v řádové velikosti a přesností reprezentace čísel s různými počty bitů pro mantisu a exponent.

- [ ] Naučit se to počítat
## Kódování znaků
___

- Znaky, jako jsou písmena, číslice a speciální symboly, jsou v počítači reprezentovány pomocí kódů.
- ASCII (American Standard Code for Information Interchange) je jedním z nejčastějších kódování znaků, které přiřazuje každému znaku sedmibitový kód.
- Unicode je rozšíření ASCII, které podporuje mnohem širší rozsah znaků a používá 16-bitové nebo 32-bitové kódy.
### Unicode

- Unicode je standard, který přiřazuje jedinečný číselný identifikátor každému znaku a symbolu používanému v počítačových systémech.
- Pro reprezentaci znaků používá 16-bitové (UTF-16) nebo 32-bitové (UTF-32) kódování.
- Při použití UTF-16 jsou běžné znaky kódovány jedním 16-bitovým kódem, ale pro méně časté znaky jsou potřeba dva 16-bitové kódy.

- [ ] Naučit se převádět