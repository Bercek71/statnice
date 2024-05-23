![[Okruhy#^e5c690]]

Překladače jsou nástroje, které převádějí zdrojový kód napsaný v jednom programovacím jazyce do jiného jazyka, obvykle do strojového kódu. Překladače hrají klíčovou roli v softwarovém vývoji, protože umožňují programátorům psát kód ve vyšších programovacích jazycích.

#### Základní funkce a typy překladačů

1. **Základní funkce překladačů**:
   - **Lexikální analýza**: Převod vstupního řetězce na sekvenci tokenů.
   - **Syntaktická analýza**: Kontrola, zda sekvence tokenů splňuje gramatická pravidla jazyka a vytvoření syntaktického stromu.
   - **Sémantická analýza**: Kontrola sémantických pravidel (typová kontrola, deklarace proměnných).
   - **Optimalizace**: Zlepšení výkonu nebo efektivity kódu.
   - **Generování kódu**: Převod syntaktického stromu do cílového kódu.
   - **Sestavení (Assembly)**: Převod symbolického strojového kódu do binárního formátu.

2. **Typy překladačů**:
   - **Jednopassové**: Překladače, které projdou zdrojový kód pouze jednou.
   - **Vícepásové**: Překladače, které procházejí zdrojový kód vícekrát pro různé fáze analýzy a optimalizace.
   - **Interprety**: Převádějí a vykonávají kód řádek po řádku namísto generování celého strojového kódu předem.
   - **Just-in-time (JIT) překladače**: Kombinují překlad a interpretaci, překládají části kódu těsně před jejich spuštěním.

#### Fáze při překladu

1. **Lexikální analýza (Lexical Analysis)**:
   - Vstup: Zdrojový kód.
   - Výstup: Sekvence tokenů.
   - Nástroje: Regulární výrazy, lexikální analyzátory (např. Lex).

2. **Syntaktická analýza (Syntax Analysis)**:
   - Vstup: Sekvence tokenů.
   - Výstup: Syntaktický strom (Parse Tree).
   - Nástroje: Bezkontextové gramatiky, syntaktické analyzátory (např. yacc, Bison).

3. **Sémantická analýza (Semantic Analysis)**:
   - Vstup: Syntaktický strom.
   - Výstup: Dekorovaný syntaktický strom s typovými informacemi a dalšími atributy.
   - Nástroje: Typové systémy, sémantická pravidla.

4. **Optimalizace (Optimization)**:
   - Vstup: Mezikód nebo syntaktický strom.
   - Výstup: Optimalizovaný mezikód nebo syntaktický strom.
   - Typy optimalizace: Lokální, globální, smyčkové, meziprocedurální.

5. **Generování kódu (Code Generation)**:
   - Vstup: Optimalizovaný mezikód nebo syntaktický strom.
   - Výstup: Cílový kód (strojový kód nebo bytecode).
   - Nástroje: Generátory kódu, assembly.

6. **Sestavení (Assembly)**:
   - Vstup: Symbolický strojový kód.
   - Výstup: Binární strojový kód.
   - Nástroje: Assembleri.

#### Formální prostředky využívané při tvorbě překladače

1. **Regulární výrazy**:
   - Používají se pro definici lexikálních jednotek (tokenů).
   - Příklady: Identifikátory, klíčová slova, operátory.

2. **Bezkontextové gramatiky (CFG)**:
   - Používají se pro definici syntaktických struktur jazyka.
   - Produkční pravidla mají tvar $A \rightarrow \alpha$, kde $A$ je neterminál a $\alpha$ je řetězec terminálů a neterminálů.

3. **Speciální podtřídy bezkontextových gramatik**:
   - **LL(1) gramatiky**: Bezkontextové gramatiky, které mohou být parsovány shora dolů s jedním tokenem pohledu dopředu.
   - **LR(1) gramatiky**: Bezkontextové gramatiky, které mohou být parsovány zdola nahoru s jedním tokenem pohledu dopředu.

#### Techniky používané při implementaci

1. **Rekurzivní sestup (Recursive Descent)**:
   - Syntaktická analýza shora dolů pomocí rekurzivních funkcí.
   - Každé produkční pravidlo gramatiky je reprezentováno funkcí.
   - Příklad:
     ```python
     def expression():
         term()
         while next_token == '+' or next_token == '-':
             match(next_token)
             term()

     def term():
         factor()
         while next_token == '*' or next_token == '/':
             match(next_token)
             factor()
     ```

2. **Generátory překladačů**:
   - Nástroje, které automaticky generují lexikální a syntaktické analyzátory z formálních specifikací.
   - **Lex/Yacc**: Tradiční nástroje pro generování lexikálních a syntaktických analyzátorů.
   - **Flex/Bison**: Modern

ní verze Lex a Yacc.

**Příklad použití Flex a Bison**:

- **Lexikální analýza pomocí Flex**:
  ```flex
  %{
  #include "y.tab.h"
  %}

  %%
  [0-9]+      { yylval = atoi(yytext); return NUMBER; }
  [a-zA-Z][a-zA-Z0-9]*  { return IDENTIFIER; }
  "+"         { return PLUS; }
  "-"         { return MINUS; }
  "*"         { return TIMES; }
  "/"         { return DIVIDE; }
  "="         { return ASSIGN; }
  ";"         { return SEMICOLON; }
  [ \t\n]     ;  // Ignore whitespace
  .           { return yytext[0]; }

  %%
  ```

- **Syntaktická analýza pomocí Bison**:
  ```bison
  %{
  #include <stdio.h>
  #include <stdlib.h>
  void yyerror(const char *s);
  %}

  %token NUMBER IDENTIFIER
  %token PLUS MINUS TIMES DIVIDE ASSIGN SEMICOLON

  %%
  program:
      statement_list
      ;

  statement_list:
      statement_list statement
      | statement
      ;

  statement:
      IDENTIFIER ASSIGN expression SEMICOLON
      ;

  expression:
      expression PLUS term
      | expression MINUS term
      | term
      ;

  term:
      term TIMES factor
      | term DIVIDE factor
      | factor
      ;

  factor:
      NUMBER
      | IDENTIFIER
      | '(' expression ')'
      ;

  %%

  int main() {
      yyparse();
      return 0;
  }

  void yyerror(const char *s) {
      fprintf(stderr, "Error: %s\n", s);
  }
  ```

### Shrnutí

Překladače jsou klíčové nástroje pro převod zdrojového kódu do strojového kódu. Proces překladu se skládá z několika fází, včetně lexikální analýzy, syntaktické analýzy, sémantické analýzy, optimalizace, generování kódu a sestavení. Formální prostředky jako regulární výrazy a bezkontextové gramatiky jsou zásadní pro konstrukci lexikálních a syntaktických analyzátorů. Speciální techniky, jako je rekurzivní sestup a použití generátorů překladačů, usnadňují implementaci překladačů. Pokud máš další otázky nebo potřebuješ podrobnější vysvětlení, neváhej se zeptat!