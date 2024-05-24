![[Okruhy#^106d26]]

### Diferenciální a integrální počet funkcí více proměnných

Diferenciální a integrální počet funkcí více proměnných rozšiřuje koncepty známé z funkcí jedné proměnné na funkce více proměnných. Zahrnuje parciální derivace, gradient, extrémy a dvojné a trojné integrály.

#### Parciální derivace

1. **Definice**:
   - Parciální derivace funkce $f(x, y)$ vzhledem k $x$ je limitou:
   $$
   \frac{\partial f}{\partial x} = \lim_{h \to 0} \frac{f(x + h, y) - f(x, y)}{h}
   $$
   - Podobně pro parciální derivaci vzhledem k $y$:
   $$
   \frac{\partial f}{\partial y} = \lim_{h \to 0} \frac{f(x, y + h) - f(x, y)}{h}
   $$

**Příklad**:
$$
f(x, y) = x^2 y + y^3
$$
$$
\frac{\partial f}{\partial x} = 2xy
$$
$$
\frac{\partial f}{\partial y} = x^2 + 3y^2
$$

#### Gradient

1. **Definice**:
   - Gradient funkce $f(x, y)$ je vektor obsahující všechny parciální derivace:
   $$
   \nabla f = \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y} \right)
   $$
   - Pro funkci $f(x, y, z)$ je gradient:
   $$
   \nabla f = \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}, \frac{\partial f}{\partial z} \right)
   $$

**Příklad**:
$$
f(x, y) = x^2 + y^2
$$
$$
\nabla f = \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y} \right) = (2x, 2y)
$$

#### Extrémy

1. **Kritické body**:
   - Body, kde gradient $\nabla f = 0$ nebo neexistuje.
   - Kritické body se testují na lokální extrémy pomocí druhých derivací.

2. **Test druhých derivací**:
   - Pro funkci $f(x, y)$ najdeme Hessovu matici $H$:
   $$
   H = \begin{pmatrix}
   \frac{\partial^2 f}{\partial x^2} & \frac{\partial^2 f}{\partial x \partial y} \\
   \frac{\partial^2 f}{\partial y \partial x} & \frac{\partial^2 f}{\partial y^2}
   \end{pmatrix}
   $$
   - Určíme determinant Hessovy matice $D = \det(H)$:
     - Pokud $D > 0$ a $\frac{\partial^2 f}{\partial x^2} > 0$, $f$ má lokální minimum.
     - Pokud $D > 0$ a $\frac{\partial^2 f}{\partial x^2} < 0$, $f$ má lokální maximum.
     - Pokud $D < 0$, $f$ má sedlový bod.

**Příklad**:
$$
f(x, y) = x^2 + y^2
$$
$$
\nabla f = (2x, 2y) \quad \text{dává kritický bod } (0, 0)
$$
$$
H = \begin{pmatrix}
2 & 0 \\
0 & 2
\end{pmatrix}
$$
$$
D = 2 \cdot 2 - 0 = 4 > 0 \quad \text{a} \quad \frac{\partial^2 f}{\partial x^2} = 2 > 0 \quad \Rightarrow \quad \text{lokální minimum}
$$

#### Dvojné a trojné integrály

1. **Dvojné integrály**:
   - Integrál funkce $f(x, y)$ přes oblast $D$ v rovině:
   $$
   \iint_D f(x, y) \, dA
   $$
   - Lze vyjádřit jako iterovaný integrál:
   $$
   \iint_D f(x, y) \, dA = \int_{a}^{b} \int_{c}^{d} f(x, y) \, dy \, dx
   $$

**Příklad**:
$$
f(x, y) = x + y \quad \text{přes obdélník} \quad D = [0, 1] \times [0, 1]
$$
$$
\iint_D (x + y) \, dA = \int_0^1 \int_0^1 (x + y) \, dy \, dx
$$
$$
= \int_0^1 \left[ xy + \frac{y^2}{2} \right]_0^1 \, dx
$$
$$
= \int_0^1 \left( x + \frac{1}{2} \right) \, dx
$$
$$
= \left[ \frac{x^2}{2} + \frac{x}{2} \right]_0^1
$$
$$
= \frac{1}{2} + \frac{1}{2} = 1
$$

2. **Trojné integrály**:
   - Integrál funkce $f(x, y, z)$ přes oblast $E$ v prostoru:
   $$
   \iiint_E f(x, y, z) \, dV
   $$
   - Lze vyjádřit jako iterovaný integrál:
   $$
   \iiint_E f(x, y, z) \, dV = \int_{a}^{b} \int_{c}^{d} \int_{e}^{f} f(x, y, z) \, dz \, dy \, dx
   $$

**Příklad**:
$$
f(x, y, z) = x + y + z \quad \text{přes krychli} \quad E = [0, 1] \times [0, 1] \times [0, 1]
$$
$$
\iiint_E (x + y + z) \, dV = \int_0^1 \int_0^1 \int_0^1 (x + y + z) \, dz \, dy \, dx
$$
$$
= \int_0^1 \int_0^1 \left[ xz + yz + \frac{z^2}{2} \right]_0^1 \, dy \, dx
$$
$$
= \int_0^1 \int_0^1 \left( x + y + \frac{1}{2} \right) \, dy \, dx
$$
$$
= \int_0^1 \left[ xy + \frac{y^2}{2} + \frac{y}{2} \right]_0^1 \, dx
$$
$$
= \int_0^1 \left( x + \frac{1}{2} + \frac{1}{2} \right) \, dx
$$
$$
= \int_0^1 \left( x + 1 \right) \, dx
$$
$$
= \left[ \frac{x^2}{2} + x \right]_0^1
$$
$$
= \frac{1}{2} + 1 = \frac{3}{2}
$$

### Shrnutí

Diferenciální a integrální počet funkcí více proměnných zahrnuje koncepty jako parciální derivace, gradient, extrémy, dvojné a trojné integrály. Tyto nástroje jsou klíčové pro analýzu funkcí, které závisí na více proměnných, a mají široké uplatnění v mnoha oblastech vědy a techniky. Pokud máš další otázky nebo potřebuješ podrobnější vysvětlení, neváhej se zeptat!