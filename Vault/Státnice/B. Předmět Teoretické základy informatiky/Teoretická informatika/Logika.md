![[Okruhy#^7a4280]]

### Logika

Logika je základní disciplína v matematice a informatice, která se zabývá studiem správného usuzování. Zahrnuje formální systémy, které modelují strukturu výroků a argumentů. Dvě základní oblasti logiky jsou výroková logika a predikátová logika.

#### Výroková logika (Propositional Logic)

**Výroková logika** se zabývá výroky, které mohou být pravdivé nebo nepravdivé, a logickými operátory, které kombinují výroky do složitějších formulí.

##### Syntaxe výrokové logiky

- **Výroky**: Základní jednotky, které mohou být pravdivé nebo nepravdivé (např. \($p, q, r$\)).
- **Logické operátory**:
  - **Negace (\($\neg$\))**: Mění pravdivostní hodnotu výroku (\(\neg p\)).
  - **Konjunkce (\($\land$\))**: Pravdivá, pokud jsou oba výroky pravdivé (\(p \land q\)).
  - **Disjunkce (\($\lor$\))**: Pravdivá, pokud alespoň jeden z výroků je pravdivý (\(p \lor q\)).
  - **Implikace (\($\rightarrow$\))**: Pravdivá, pokud je první výrok nepravdivý nebo druhý výrok pravdivý (\($p \rightarrow q$\)).
  - **Ekvivalence (\(\leftrightarrow\))**: Pravdivá, pokud oba výroky mají stejnou pravdivostní hodnotu (\($p \leftrightarrow q$\)).

##### Sémantika výrokové logiky

- **Pravdivostní tabulky**: Nástroj pro určení pravdivostní hodnoty složitých formulí na základě pravdivostních hodnot jednotlivých výroků.

**Příklad pravdivostní tabulky pro \(p \land q\):**

| \($p$\) | \($q$\) | \($p \land q$\) |
| ------- | ------- | --------------- |
| T       | T       | T               |
| T       | F       | F               |
| F       | T       | F               |
| F       | F       | F               |

#### Predikátová logika (Predicate Logic)

**Predikátová logika** je rozšířením výrokové logiky, která zahrnuje kvantifikátory a predikáty, což umožňuje vyjadřovat obecné výroky o objektech a jejich vlastnostech.

##### Syntaxe predikátové logiky

- **Predikáty**: Funkce, které vrací pravdivostní hodnotu na základě vstupních argumentů (např. \($P(x)$\), \($Q(x, y)$\)).
- **Kvantifikátory**:
  - **Univerzální kvantifikátor (\(\forall\))**: Výrok platí pro všechny prvky (\($\forall x \, P(x)$\)).
  - **Existenční kvantifikátor (\(\exists\))**: Výrok platí pro alespoň jeden prvek (\($\exists x \, P(x)$\)).

##### Sémantika predikátové logiky

- **Interpretace**: Určení domény, ze které pocházejí proměnné, a přiřazení významu predikátům.

**Příklad:**
- Doména \(D\) je množina všech lidí.
- \(P(x)\) znamená "x je student".
- \(\forall x \, P(x)\) znamená "všichni jsou studenti".

#### Sémantické a syntaktické dokazování

**Sémantické dokazování**:
- Založeno na pravdivostních tabulkách nebo modelech.
- Výroková logika: Použití pravdivostních tabulek pro ověření tautologie.
- Predikátová logika: Hledání modelu, který splňuje formuli.

**Syntaktické dokazování**:
- Použití formálních pravidel odvozování.
- **Výroková logika**: Axiomy a pravidla odvozování (např. modus ponens).
- **Predikátová logika**: Dodatečná pravidla pro kvantifikátory.

**Modus ponens**:
$$ \frac{A \rightarrow B, \, A}{B}$$

#### Ekvivalentní úpravy

- **De Morganovy zákony**:
  $$
  \neg (A \land B) \equiv \neg A \lor \neg B \\
  \neg (A \lor B) \equiv \neg A \land \neg B
  $$

- **Distributivita**:
  $$
  A \land (B \lor C) \equiv (A \land B) \lor (A \land C) \\
  A \lor (B \land C) \equiv (A \lor B) \land (A \lor C)
  $$

- **Dvojitá negace**:
  $$
  \neg (\neg A) \equiv A
  $$

#### Rezoluční metoda

Rezoluční metoda je automatizovaná metoda dokazování pro výrokovou i predikátovou logiku, která je založena na odvozování kontradikcí.

**Výroková logika**:
- Převeď formuli do konjunktivní normální formy (CNF).
- Použij rezoluční pravidlo pro odvozování nových klauzulí, dokud se nedosáhne prázdné klauzule (kontradikce).

**Rezoluční pravidlo**:
$\frac{A \lor B, \, \neg A \lor C}{B \lor C}$

**Příklad rezoluce ve výrokové logice**:
1. Formule: \($(p \lor q) \land (\neg p \lor r) \land (\neg q \lor \neg r)$\)
2. Klauzule:
   $$
   \begin{align*}
   &C_1: p \lor q \\
   &C_2: \neg p \lor r \\
   &C_3: \neg q \lor \neg r
   \end{align*}
   $$
3. Rezoluce mezi \($C_1$\) a ($C_2$):
   $$
   \begin{align*}
   &C_4: q \lor r \\
   \end{align*}
   $$
4. Rezoluce mezi \($C_3$\) a \($C_4$\):
   $$
   \begin{align*}
   &C_5: \neg r \lor r \\
   \end{align*}
   $$
5. Rezoluce mezi \($C_5$\):
   $$
   \begin{align*}
   &C_6: \emptyset \quad \text{(prázdná klauzule)}
   \end{align*}
   $$

Prázdná klauzule indikuje, že původní formule je nesplnitelná, což znamená, že její negace je tautologií.

### Shrnutí

Logika, zahrnující výrokovou a predikátovou logiku, poskytuje základy pro formální dokazování a usuzování. Syntaktické a sémantické metody dokazování umožňují ověřovat pravdivost výroků, zatímco ekvivalentní úpravy a rezoluční metoda poskytují nástroje pro efektivní práci s logickými formulacemi. Pokud máš další otázky nebo potřebuješ podrobnější vysvětlení, neváhej se zeptat!