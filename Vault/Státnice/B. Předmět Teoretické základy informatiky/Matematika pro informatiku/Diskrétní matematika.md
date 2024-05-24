![[Okruhy#^b093cf]]
### Diskrétní matematika

Diskrétní matematika je oblast matematiky, která se zabývá studiem diskrétních objektů a struktur. Tato oblast zahrnuje témata jako posloupnosti, rekurentní rovnice, kombinatorické výběry, diskrétní pravděpodobnost a řešení kongruencí.

#### Posloupnosti

Posloupnost je uspořádaná množina čísel, které následují jeden po druhém podle určitého pravidla.

- **Aritmetická posloupnost**:
  - Každý člen posloupnosti se liší od předchozího člena o konstantní rozdíl $d$.
  - $a_n = a_1 + (n-1)d$

- **Geometrická posloupnost**:
  - Každý člen posloupnosti se liší od předchozího člena o konstantní násobek $r$.
  - $a_n = a_1 \cdot r^{(n-1)}$

**Příklad**:
- Aritmetická posloupnost: $2, 5, 8, 11, \ldots$ (zde $d = 3$)
- Geometrická posloupnost: $3, 6, 12, 24, \ldots$ (zde $r = 2$)

#### Rekurentní rovnice

Rekurentní rovnice je rovnice, která definuje člen posloupnosti pomocí předchozích členů.

- **Lineární rekurentní rovnice s konstantními koeficienty**:
  - Obecná forma: $a_n = c_1 a_{n-1} + c_2 a_{n-2} + \ldots + c_k a_{n-k} + f(n)$
  - Homogenní rovnice: $a_n = c_1 a_{n-1} + c_2 a_{n-2} + \ldots + c_k a_{n-k}$

**Příklad**:
- Fibonacciho posloupnost: $F_n = F_{n-1} + F_{n-2}$ s počátečními podmínkami $F_0 = 0$, $F_1 = 1$

#### Kombinatorické výběry

Kombinatorika se zabývá výběrem a uspořádáním prvků v množině.

- **Permutace**:
  - Uspořádaný výběr prvků.
  - Počet permutací $n$ prvků: $n!$

- **Kombinace**:
  - Neuspořádaný výběr $k$ prvků z $n$ prvků.
  - Počet kombinací: $\binom{n}{k} = \frac{n!}{k!(n-k)!}$

**Příklad**:
- Počet způsobů, jak vybrat 3 karty z balíčku 52 karet: $\binom{52}{3} = \frac{52!}{3!(52-3)!}$

#### Diskrétní pravděpodobnost

Diskrétní pravděpodobnost se zabývá pravděpodobnostmi událostí v diskrétním vzorkovacím prostoru.

- **Pravděpodobnostní prostor**: $(\Omega, \mathcal{F}, P)$
  - $\Omega$: Množina všech možných výsledků (vzorkovací prostor).
  - $\mathcal{F}$: Množina všech podmnožin $\Omega$ (událostí).
  - $P$: Pravděpodobnostní funkce přiřazující pravděpodobnosti událostem.

- **Pravděpodobnost události $A$**:
  $$
  P(A) = \frac{|A|}{|\Omega|}
  $$

**Příklad**:
- Pravděpodobnost, že padne sudé číslo při hodu kostkou: $\Omega = \{1, 2, 3, 4, 5, 6\}$, $A = \{2, 4, 6\}$
  $$
  P(A) = \frac{3}{6} = \frac{1}{2}
  $$

#### Řešení kongruencí

Kongruence se zabývá rovnostmi v modulo aritmetice.

- **Definice kongruence**:
  $$
  a \equiv b \ (\text{mod} \ n) \Leftrightarrow n \mid (a - b)
  $$

- **Lineární kongruence**:
  - Řešení rovnice $ax \equiv b \ (\text{mod} \ n)$.

**Postup řešení**:
1. Najdeme největšího společného dělitele (NSD) $d$ pro $a$ a $n$.
2. Pokud $d \mid b$, existuje řešení. Pokud $d \nmid b$, neexistuje řešení.
3. Najdeme jedno řešení pomocí rozšířeného Euklidova algoritmu.
4. Všechny řešení jsou tvaru $x = x_0 + k\frac{n}{d}$, kde $k \in \mathbb{Z}$.

**Příklad**:
- Řešení $3x \equiv 6 \ (\text{mod} \ 9)$:
  - NSD(3, 9) = 3, a protože 3 dělí 6, existuje řešení.
  - Rozšířený Euklidův algoritmus dává jedno řešení $x_0 = 2$.
  - Všechna řešení jsou tvaru $x = 2 + k\frac{9}{3} = 2 + 3k$.

### Shrnutí

Diskrétní matematika pokrývá širokou škálu témat, která jsou klíčová pro studium informatiky a teoretické matematiky. Posloupnosti a rekurentní rovnice pomáhají modelovat různé procesy, kombinatorické výběry umožňují analýzu výběrů a uspořádání prvků, diskrétní pravděpodobnost se zabývá pravděpodobnostmi událostí v diskrétních prostorech a kongruence se zabývá řešením rovnic v modulo aritmetice. Tyto koncepty jsou základními nástroji pro analýzu a řešení problémů v mnoha oblastech vědy a techniky. Pokud máš další otázky nebo potřebuješ podrobnější vysvětlení, neváhej se zeptat!