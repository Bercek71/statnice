![[Okruhy#^64a27d]]

### Diferenciální a integrální počet funkcí jedné proměnné

Diferenciální a integrální počet je základní oblastí matematiky, která se zabývá studiem změn a ploch. Obsahuje koncepty jako posloupnosti, limity, derivace, extrémy a integrály.

#### Posloupnosti

1. **Definice**:
   - Posloupnost je uspořádaná množina čísel $(a_n)$, kde $n$ je přirozené číslo.

2. **Konvergence**:
   - Posloupnost $(a_n)$ konverguje k limitě $L$, pokud pro každé $\epsilon > 0$ existuje přirozené číslo $N$, že pro všechna $n > N$ platí $|a_n - L| < \epsilon$.

**Příklad**:
$$
a_n = \frac{1}{n} \quad \text{konverguje k } 0, \text{ protože } \lim_{n \to \infty} \frac{1}{n} = 0.
$$

#### Limita a spojitost

1. **Limita funkce**:
   - Funkce $f(x)$ má limitu $L$ v bodě $a$, pokud pro každé $\epsilon > 0$ existuje $\delta > 0$, že pro všechna $x$, kde $0 < |x - a| < \delta$, platí $|f(x) - L| < \epsilon$.

2. **Spojitost**:
   - Funkce $f(x)$ je spojitá v bodě $a$, pokud:
     1. $\lim_{x \to a} f(x)$ existuje,
     2. $f(a)$ je definováno,
     3. $\lim_{x \to a} f(x) = f(a)$.

**Příklad**:
$$
\lim_{x \to 2} (3x + 1) = 7
$$
$$
\text{Funkce } f(x) = 3x + 1 \text{ je spojitá v každém bodě.}
$$

#### Derivace

1. **Definice derivace**:
   - Derivace funkce $f(x)$ v bodě $a$ je limitou:
   $$
   f'(a) = \lim_{h \to 0} \frac{f(a + h) - f(a)}{h}
   $$

2. **Pravidla derivování**:
   - **Součet a rozdíl**: $(f \pm g)' = f' \pm g'$
   - **Součin**: $(fg)' = f'g + fg'$
   - **Podíl**: $\left(\frac{f}{g}\right)' = \frac{f'g - fg'}{g^2}$
   - **Řetězové pravidlo**: $(f(g(x)))' = f'(g(x))g'(x)$

**Příklad**:
$$
f(x) = x^2 \quad \Rightarrow \quad f'(x) = 2x
$$
$$
g(x) = \sin(x) \quad \Rightarrow \quad g'(x) = \cos(x)
$$

#### Extrémy

1. **Lokální extrémy**:
   - **Lokální maximum**: $f(a) \geq f(x)$ pro všechna $x$ v okolí $a$.
   - **Lokální minimum**: $f(a) \leq f(x)$ pro všechna $x$ v okolí $a$.

2. **Kritické body**:
   - Body, kde $f'(x) = 0$ nebo $f'(x)$ neexistuje.

3. **Test druhé derivace**:
   - Pokud $f''(a) > 0$, pak $f(a)$ je lokální minimum.
   - Pokud $f''(a) < 0$, pak $f(a)$ je lokální maximum.

**Příklad**:
$$
f(x) = x^3 - 3x^2 + 4
$$
$$
f'(x) = 3x^2 - 6x = 3x(x - 2)
$$
Kritické body: $x = 0$, $x = 2$

#### Neurčité a určité integrály

1. **Neurčitý integrál**:
   - Antiderivace funkce $f(x)$:
   $$
   \int f(x) \, dx = F(x) + C \quad \text{kde } F'(x) = f(x)
   $$

2. **Určitý integrál**:
   - Definován jako limita Riemannových sum:
   $$
   \int_a^b f(x) \, dx = \lim_{n \to \infty} \sum_{i=1}^n f(x_i^*) \Delta x_i
   $$
   - Vypočítá se pomocí Newton-Leibnizovy věty:
   $$
   \int_a^b f(x) \, dx = F(b) - F(a)
   $$

**Příklad**:
$$
\int x^2 \, dx = \frac{x^3}{3} + C
$$
$$
\int_0^1 x^2 \, dx = \left[ \frac{x^3}{3} \right]_0^1 = \frac{1}{3} - 0 = \frac{1}{3}
$$

### Shrnutí

Diferenciální a integrální počet funkcí jedné proměnné se zabývá studiem posloupností, limit, spojitosti, derivací, extrémů a integrálů. Tyto koncepty jsou základem pro analýzu a pochopení chování funkcí a mají široké uplatnění v matematice, fyzice, inženýrství a dalších oborech. Pokud máš další otázky nebo potřebuješ podrobnější vysvětlení, neváhej se zeptat!