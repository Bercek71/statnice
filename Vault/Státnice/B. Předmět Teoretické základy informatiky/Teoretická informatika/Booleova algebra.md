![[Okruhy#^0af8eb]]

### Booleova algebra

Booleova algebra je matematický systém, který se zabývá manipulací s logickými proměnnými a logickými operacemi. Je základem digitální logiky a návrhu kombinačních obvodů v elektronice a počítačové technice.

#### Booleova funkce

Booleova funkce je funkce, která bere logické proměnné (obvykle reprezentované jako 0 nebo 1) a vrací logickou hodnotu (0 nebo 1). Booleovy funkce jsou definovány pomocí základních logických operací:

1. **Negace (NOT)**: $$\neg A$$
   - Inverze logické hodnoty.
   - Pravdivostní tabulka:
   
| $$A$$ | $$\neg A$$ |
| ------- | ------------ |
| 0       | 1            |
| 1       | 0            |

2. **Konjunkce (AND)**: $$A \land B$$
   - Výsledek je pravdivý, pokud jsou obě proměnné pravdivé.
   - Pravdivostní tabulka:

| $$A$$ | $$B$$ | $$A \land B$$ |
| ------- | ------- | --------------- |
| 0       | 0       | 0               |
| 0       | 1       | 0               |
| 1       | 0       | 0               |
| 1       | 1       | 1               |

3. **Disjunkce (OR)**: $$A \lor B$$
   - Výsledek je pravdivý, pokud je alespoň jedna proměnná pravdivá.
   - Pravdivostní tabulka:

| $$A$$ | $$B$$ | $$A \lor B$$ |
| ------- | ------- | -------------- |
| 0       | 0       | 0              |
| 0       | 1       | 1              |
| 1       | 0       | 1              |
| 1       | 1       | 1              |

4. **Implikace (IMPLIES)**: $A \rightarrow B$
   - Výsledek je nepravdivý pouze tehdy, když $A$ je pravdivé a $B$ je nepravdivé.
   - Pravdivostní tabulka:

| $$A$$ | $$B$$ | $$A \rightarrow B$$ |
| ------- | ------- | --------------------- |
| 0       | 0       | 1                     |
| 0       | 1       | 1                     |
| 1       | 0       | 0                     |
| 1       | 1       | 1                     |

5. **Ekvivalence (EQUIVALENT)**: $A \leftrightarrow B$
   - Výsledek je pravdivý, pokud obě proměnné mají stejnou hodnotu.
   - Pravdivostní tabulka:

| $$A$$ | $$B$$ | $$A \leftrightarrow B$$ |
| ------- | ------- | ------------------------- |
| 0       | 0       | 1                         |
| 0       | 1       | 0                         |
| 1       | 0       | 0                         |
| 1       | 1       | 1                         |

#### Minimalizace Booleových funkcí

Minimalizace Booleových funkcí znamená nalezení co nejjednoduššího výrazu, který je ekvivalentní původnímu výrazu. To se obvykle provádí za účelem snížení složitosti logických obvodů.

**Metody minimalizace:**

1. **Algebraické úpravy:**
   - Použití základních zákonů Booleovy algebry (např. asociativní, komutativní, distributivní zákony) pro zjednodušení výrazu.
   - Příklad: $A \land (A \lor B) \equiv A$

2. **Karnaughova mapa (K-map):**
   - Grafická metoda pro vizualizaci a minimalizaci Booleových funkcí až pro čtyři proměnné.
   - Každá buňka K-map odpovídá jedné kombinaci vstupních proměnných a obsahuje výstupní hodnotu Booleovy funkce.
   - Seskupováním sousedních buněk s hodnotou 1 se hledají minimální logické výrazy.

**Příklad K-mapy pro funkci $F(A, B, C) = \sum(1, 3, 7)$:**

$$
\begin{array}{c|cc}
    AB \backslash C & 0 & 1 \\
    \hline
    00 & 0 & 0 \\
    01 & 1 & 0 \\
    11 & 0 & 1 \\
    10 & 0 & 0 \\
\end{array}
$$

Minimalizace: $F(A, B, C) = \overline{A}BC + AB\overline{C}$

#### Vazba na kombinační obvody

Kombinační obvody jsou digitální logické obvody, jejichž výstup je závislý pouze na aktuálních hodnotách vstupů. Kombinační obvody neobsahují žádné paměťové prvky, a tedy nemají žádný stav.

**Základní kombinační obvody:**

1. **AND brána**:
   - Realizuje konjunkci.
   - Schéma: 
   ```
       A ---|&|--- výstup
       B ---| |
   ```

2. **OR brána**:
   - Realizuje disjunkci.
   - Schéma:
   ```
       A ---|≥1|--- výstup
       B ---|   |
   ```

3. **NOT brána**:
   - Realizuje negaci.
   - Schéma:
   ```
       A ---|>--- výstup
   ```

4. **NAND brána**:
   - Realizuje negovanou konjunkci ($\neg (A \land B)$).
   - Schéma:
   ```
       A ---|&|---|>--- výstup
       B ---| |
   ```

5. **NOR brána**:
   - Realizuje negovanou disjunkci ($\neg (A \lor B)$).
   - Schéma:
   ```
       A ---|≥1|---|>--- výstup
       B ---|   |
   ```

6. **XOR brána**:
   - Realizuje exkluzivní disjunkci ($A \oplus B$).
   - Schéma:
   ```
       A ---|=1|--- výstup
       B ---|   |
   ```

**Realizace kombinačních obvodů:**

- **Dekodér**: Převádí binární vstup na jediný aktivní výstup.
- **Multiplexor (MUX)**: Selektuje jeden z několika vstupů a směruje jej na výstup.
- **Demultiplexor (DEMUX)**: Směruje vstup na jeden z několika výstupů na základě selektoru.

**Příklad realizace Booleovy funkce pomocí kombinačního obvodu:**

Předpokládejme Booleovu funkci $F(A, B, C) = \overline{A}BC + AB\overline{C}$.

1. Krok 1: Implementace jednotlivých částí:
   - NOT brány pro $\overline{A}$ a $\overline{C}$.
   - AND brány pro $\overline{A}BC$ a $AB\overline{C}$.

2. Krok 2: Kombinace výsledků pomocí OR brány:
   ```
      A -----|>o----|&|-------
               |     | & |      |
               |     B-| |------|≥1|-- výstup
               |        | & |      |
      B -------|      C-|         |
               |             AB-| |------|≥1|-- výstup
      C -------|>o----|>o----|&|-------
   ```

Tento obvod realizuje minimalizovanou funkci $F(A, B, C)$ a využívá kombinaci základních logických bran.

### Shrnutí

Booleova algebra poskytuje základní nástroje pro návrh a analýzu logických obvodů. Minimalizace Booleových funkcí je klíčová pro efektivní realizaci kombinačních obvodů, které se hojně používají v digitálních systémech. Pokud máš další otázky nebo potřebuješ podrobnější vysvětlení, neváhej se zeptat!