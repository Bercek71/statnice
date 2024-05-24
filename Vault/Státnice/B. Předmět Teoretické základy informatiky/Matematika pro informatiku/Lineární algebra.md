![[Okruhy#^713bea]]

### Lineární algebra

Lineární algebra je klíčová oblast matematiky, která se zabývá studiem vektorových prostorů a lineárních transformací mezi nimi. Důležitými objekty jsou matice, které reprezentují lineární zobrazení, a vektory.

#### Matice a maticové operace

1. **Matice**:
   - Obdélníkové uspořádání čísel do řádků a sloupců.
   - Matice $A$ řádu $m \times n$ má $m$ řádků a $n$ sloupců.

2. **Maticové operace**:
   - **Sčítání matic**: $A + B = [a_{ij} + b_{ij}]$
   - **Násobení skalárem**: $cA = [ca_{ij}]$
   - **Násobení matic**: $C = AB$, kde $c_{ij} = \sum_{k=1}^n a_{ik}b_{kj}$
   - **Transpozice matice**: $A^T$, kde $a_{ij}^T = a_{ji}$

**Příklad**:
$$
A = \begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix}, \quad B = \begin{pmatrix} 5 & 6 \\ 7 & 8 \end{pmatrix}
$$
$$
A + B = \begin{pmatrix} 6 & 8 \\ 10 & 12 \end{pmatrix}
$$
$$
A \times B = \begin{pmatrix} 1 \times 5 + 2 \times 7 & 1 \times 6 + 2 \times 8 \\ 3 \times 5 + 4 \times 7 & 3 \times 6 + 4 \times 8 \end{pmatrix} = \begin{pmatrix} 19 & 22 \\ 43 & 50 \end{pmatrix}
$$

#### Inverzní matice

Inverzní matice $A^{-1}$ matice $A$ je taková, že $A A^{-1} = I$, kde $I$ je jednotková matice.

1. **Existence inverzní matice**:
   - Matice $A$ má inverzní matici, pokud je čtvercová a její determinant $\det(A) \neq 0$.

2. **Výpočet inverzní matice** (pro 2x2 matici):
   - $A = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$
   - Inverzní matice $A^{-1} = \frac{1}{ad - bc} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}$

**Příklad**:
$$
A = \begin{pmatrix} 4 & 7 \\ 2 & 6 \end{pmatrix}
$$
$$
\det(A) = 4 \times 6 - 7 \times 2 = 24 - 14 = 10
$$
$$
A^{-1} = \frac{1}{10} \begin{pmatrix} 6 & -7 \\ -2 & 4 \end{pmatrix} = \begin{pmatrix} 0.6 & -0.7 \\ -0.2 & 0.4 \end{pmatrix}
$$

#### Úpravy a řešení soustav lineárních rovnic

Soustava lineárních rovnic lze řešit pomocí maticových operací.

1. **Gaussova eliminace**:
   - Postupné úpravy řádků matice, aby se převedla na horní trojúhelníkový tvar.
   - Následná zpětná substituce.

2. **Gauss-Jordanova eliminace**:
   - Další úpravy vedoucí k redukované řádkové echelonové formě, která umožňuje přímé čtení řešení.

**Příklad**:
Řešte soustavu:
$$
\begin{cases}
2x + 3y = 8 \\
4x + 5y = 18
\end{cases}
$$
Maticová reprezentace:
$$
\begin{pmatrix}
2 & 3 & | & 8 \\
4 & 5 & | & 18
\end{pmatrix}
$$
Gaussova eliminace:
$$
\begin{pmatrix}
2 & 3 & | & 8 \\
0 & -1 & | & -2
\end{pmatrix}
$$
Zpětná substituce:
$$
y = 2, \quad x = 1
$$

#### Vektorové prostory a báze vektorových prostorů

1. **Vektorový prostor**:
   - Množina vektorů s definovanými operacemi sčítání a násobení skalárem, které splňují určité axiomy.

2. **Báze vektorového prostoru**:
   - Množina lineárně nezávislých vektorů, které generují celý prostor.
   - Každý vektor v prostoru lze vyjádřit jako lineární kombinaci bázových vektorů.

**Příklad**:
Vektorový prostor $\mathbb{R}^2$:
$$
\text{Báze: } \left\{ \begin{pmatrix} 1 \\ 0 \end{pmatrix}, \begin{pmatrix} 0 \\ 1 \end{pmatrix} \right\}
$$

#### Lineární zobrazení

1. **Lineární zobrazení (transformace)**:
   - Zobrazení $T: V \rightarrow W$, kde $V$ a $W$ jsou vektorové prostory, které zachovává operace sčítání a násobení skalárem.
   - $T(av + bw) = aT(v) + bT(w)$

2. **Matice lineárního zobrazení**:
   - Pokud máme báze $\{v_1, v_2, \ldots, v_n\}$ pro $V$ a $\{w_1, w_2, \ldots, w_m\}$ pro $W$, pak matice $A$ lineárního zobrazení $T$ je definována tak, že $T(v_j) = \sum_{i} a_{ij} w_i$.

**Příklad**:
Lineární zobrazení $T: \mathbb{R}^2 \rightarrow \mathbb{R}^2$, kde $T(x, y) = (x + y, x - y)$:
$$
\text{Matice zobrazení: } A = \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}
$$

#### Spektrální teorie

1. **Vlastní čísla a vlastní vektory**:
   - **Vlastní číslo** $\lambda$ a vlastní vektor $v$ splňují rovnici $Av = \lambda v$.
   - Matice $A$ má vlastní čísla $\lambda$, pokud existuje nenulový vektor $v$, pro který platí $Av = \lambda v$.

2. **Spektrální rozklad**:
   - Čtvercovou matici $A$ lze rozložit na součin $A = PDP^{-1}$, kde $D$ je diagonální matice vlastních čísel a $P$ je matice vlastních vektorů.

**Příklad**:
Matice $A = \begin{pmatrix} 4 & 1 \\ 2 & 3 \end{pmatrix}$:
$$
\text{Charakteristická rovnice: } \det(A - \lambda I) = 0 \implies \det \begin{pmatrix} 4 - \lambda & 1 \\ 2 & 3 - \lambda \end{pmatrix} = (\lambda - 5)(\lambda - 2) = 0
$$
$$
\text{Vlastní čísla: } \lambda_1 = 5, \lambda_2 = 2
$$
$$
\text{Vlastní vektory: } v_1 = \begin{pmatrix} 1 \\ 2 \end{pmatrix}, v_2 = \begin{pmatrix} -1 \\ 1 \end{pmatrix}
$$
$$
\text{Spektrální rozklad: } A = PDP^{-1}, \quad P = \begin{pmatrix} 1 & -1 \\ 2 & 1 \end{pmatrix}, \quad D = \begin{pmatrix} 5 & 0 \\ 0 & 2 \end{pmatrix}
$$

### Shrnutí

Lineární algebra poskytuje základní nástroje a metody pro práci s vektorovými prost

ory a lineárními transformacemi. Matice a maticové operace, řešení soustav lineárních rovnic, vektorové prostory, lineární zobrazení a spektrální teorie jsou klíčovými koncepty této oblasti. Tyto nástroje mají široké uplatnění v různých oblastech matematiky, fyziky, informatiky a inženýrství. Pokud máš další otázky nebo potřebuješ podrobnější vysvětlení, neváhej se zeptat!