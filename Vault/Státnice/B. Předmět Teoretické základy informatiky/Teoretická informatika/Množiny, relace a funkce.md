![[Okruhy#^918ba6]]

### Množiny, relace a funkce

Množiny, relace a funkce jsou základními pojmy v matematice, které mají široké uplatnění v mnoha oblastech včetně informatiky.

#### Množiny

Množina je základní pojem, který označuje soubor dobře definovaných a odlišných objektů, které nazýváme prvky.

**Operace na množinách:**
- **Sjednocení ($\cup$)**: Množina všech prvků, které jsou v alespoň jedné z množin $A$ nebo $B$.
  $$
  A \cup B = \{x \mid x \in A \text{ nebo } x \in B\}
  $$
- **Průnik ($\cap$)**: Množina všech prvků, které jsou současně v množinách $A$ i $B$.
  $$
  A \cap B = \{x \mid x \in A \text{ a } x \in B\}
  $$
- **Rozdíl ($\setminus$)**: Množina všech prvků, které jsou v množině $A$, ale nejsou v množině $B$.
  $$
  A \setminus B = \{x \mid x \in A \text{ a } x \notin B\}
  $$
- **Doplněk ($A'$)**: Množina všech prvků, které nejsou v množině $A$.
  $$
  A' = \{x \mid x \notin A\}
  $$

**Příklady množinových operací:**

- **Sjednocení**:
  $$
  A = \{1, 2, 3\}, \quad B = \{3, 4, 5\} \\
  A \cup B = \{1, 2, 3, 4, 5\}
  $$
- **Průnik**:
  $$
  A = \{1, 2, 3\}, \quad B = \{3, 4, 5\} \\
  A \cap B = \{3\}
  $$
- **Rozdíl**:
  $$
  A = \{1, 2, 3\}, \quad B = \{3, 4, 5\} \\
  A \setminus B = \{1, 2\}
  $$

#### Relace

Relace je podmnožina kartézského součinu dvou množin. Pokud $R \subseteq A \times B$, říkáme, že $R$ je relace z $A$ do $B$.

**Druhy a vlastnosti relací:**

1. **Reflexivní relace**: Pro každé $a \in A$, $(a, a) \in R$.
2. **Symetrická relace**: Pro každé $a, b \in A$, pokud $(a, b) \in R$, pak $(b, a) \in R$.
3. **Antisymetrická relace**: Pro každé $a, b \in A$, pokud $(a, b) \in R$ a $(b, a) \in R$, pak $a = b$.
4. **Transitivní relace**: Pro každé $a, b, c \in A$, pokud $(a, b) \in R$ a $(b, c) \in R$, pak $(a, c) \in R$.

**Relace typu, ekvivalence a uspořádání:**

- **Ekvivalence**: Relace, která je reflexivní, symetrická a transitivní. Ekvivalence rozděluje množinu na disjunktní ekvivalenční třídy.
- **Částečné uspořádání**: Relace, která je reflexivní, antisymetrická a transitivní.
- **Totální uspořádání**: Částečné uspořádání, ve kterém jsou všechny prvky porovnatelné.

**Příklady:**

- **Ekvivalence**: Relace "být ve stejné třídě modula n" na množině celých čísel.
  $$
  a \equiv b \ (\text{mod} \ n) \Leftrightarrow n \mid (a - b)
  $$
- **Částečné uspořádání**: Relace "být předkem" na množině uzlů stromu.
- **Totální uspořádání**: Relace "menší nebo rovno" na množině reálných čísel.

#### Funkce

Funkce je speciální druh relace, kde každý prvek z první množiny (definiční obor) je spojen právě s jedním prvkem z druhé množiny (obor hodnot).

**Vlastnosti funkcí:**

1. **Injektivní (jednoznačná)**: Každý prvek z oboru hodnot je obrazem nejvýše jednoho prvku z definičního oboru.
2. **Surjektivní (na)**: Každý prvek z oboru hodnot je obrazem alespoň jednoho prvku z definičního oboru.
3. **Bijektivní (prostá na)**: Funkce je současně injektivní a surjektivní.

**Příklady funkcí:**

- **Injektivní**: $f(x) = 2x$ na $\mathbb{R}$.
- **Surjektivní**: $g(x) = x^2$ na $\mathbb{R}^+$.
- **Bijektivní**: $h(x) = x + 1$ na $\mathbb{R}$.

#### Induktivní definice a důkazy

Induktivní definice a důkazy jsou nástroje pro definování a dokazování vlastností objektů, které mají rekurzivní nebo iterativní strukturu.

**Induktivní definice:**

- **Přirozená čísla**: 0 je přirozené číslo. Pokud $n$ je přirozené číslo, pak $n + 1$ je také přirozené číslo.
- **Seznamy**: Prázdný seznam je seznam. Pokud $L$ je seznam a $a$ je prvek, pak $a :: L$ je seznam (kde $::$ je operátor přidání prvku na začátek seznamu).

**Induktivní důkaz:**

Induktivní důkaz má dvě části:
1. **Základní krok**: Ukážeme, že tvrzení platí pro základní případ (např. pro $n = 0$).
2. **Induktivní krok**: Ukážeme, že pokud tvrzení platí pro $n$, pak platí i pro $n + 1$.

**Příklad induktivního důkazu:**

Tvrzení: Součet prvních $n$ přirozených čísel je $\frac{n(n+1)}{2}$.

**Základní krok**: Pro $n = 0$:
$$
0 = \frac{0(0+1)}{2} = 0
$$

**Induktivní krok**: Předpokládejme, že tvrzení platí pro nějaké $n$, tedy:
$$
1 + 2 + \dots + n = \frac{n(n+1)}{2}
$$
Dokážeme, že platí i pro $n + 1$:
$$
1 + 2 + \dots + n + (n+1) = \frac{n(n+1)}{2} + (n+1)
$$
$$
= \frac{n(n+1) + 2(n+1)}{2} = \frac{(n+1)(n+2)}{2}
$$

Tím jsme ukázali, že tvrzení platí pro $n + 1$, pokud platí pro $n$.

### Shrnutí

Množiny, relace a funkce jsou základními pojmy, které tvoří základ pro mnoho matematických a informatických konceptů. Operace na množinách, vlastnosti relací a funkcí, stejně jako techniky induktivního důkazování, jsou klíčovými nástroji pro práci s těmito strukturami. Pokud máš další otázky nebo potřebuješ podrobnější vysvětlení, neváhej se zeptat!