![[Okruhy#^fab820]]

Zobrazovací řetězec zahrnuje všechny kroky, které se podílejí na přeměně 3D modelu na 2D obraz, který je vykreslen na obrazovce. Tento proces zahrnuje několik kroků, jako jsou modelovací a zobrazovací transformace, osvětlovací modely, řešení viditelnosti a identifikace těles. 

#### Realizace jednotlivých kroků řetězce

1. **Modelování**: Vytváření 3D modelů objektů, které budou zobrazeny.
2. **Transformace**: Převod objektů z lokálních souřadnic (modelovací transformace) do světových souřadnic a následně do zobrazovacích souřadnic (projekční transformace).
3. **Osvětlení**: Aplikace osvětlovacího modelu, jako je Phongův model, k určení barvy a intenzity světla na povrchu objektů.
4. **Viditelnost**: Určení, které části objektů jsou viditelné z pohledu kamery (např. odstraňování skrytých ploch).
5. **Rasterizace**: Převod 3D objektů na 2D obrazovkové souřadnice a vykreslení jednotlivých pixelů.
6. **Post-processing**: Aplikace dodatečných efektů, jako je anti-aliasing, stíny a textury.

#### Modelovací a zobrazovací transformace

1. **Modelovací transformace**: Převod objektů z lokálních souřadnic do světových souřadnic. Tento krok zahrnuje posun, rotaci a změnu měřítka objektů.

    \[
    \mathbf{V}_{world} = \mathbf{T} \cdot \mathbf{R} \cdot \mathbf{S} \cdot \mathbf{V}_{local}
    \]

    kde \(\mathbf{T}\) je matice posunu, \(\mathbf{R}\) je matice rotace a \(\mathbf{S}\) je matice změny měřítka.

2. **Zobrazovací (projekční) transformace**: Převod světových souřadnic do zobrazovacích souřadnic, které určují, jak objekty budou vypadat na obrazovce. Existují dva typy projekcí: ortogonální a perspektivní.

    \[
    \mathbf{V}_{clip} = \mathbf{P} \cdot \mathbf{V}_{world}
    \]

    kde \(\mathbf{P}\) je projekční matice.

#### Phongův osvětlovací model

Phongův osvětlovací model je jedním z nejpoužívanějších modelů pro simulaci osvětlení v počítačové grafice. Model kombinuje tři složky osvětlení:

1. **Ambientní osvětlení**: Rovnoměrné osvětlení, které ovlivňuje všechny povrchy stejně.

    \[
    I_a = k_a \cdot I_{a_{light}}
    \]

    kde \(k_a\) je ambientní reflexe materiálu a \(I_{a_{light}}\) je ambientní intenzita světla.

2. **Difúzní osvětlení**: Osvětlení, které závisí na úhlu dopadu světla na povrch. 

    \[
    I_d = k_d \cdot I_{d_{light}} \cdot (\mathbf{L} \cdot \mathbf{N})
    \]

    kde \(k_d\) je difúzní reflexe materiálu, \(I_{d_{light}}\) je intenzita difúzního světla, \(\mathbf{L}\) je vektor ke světlu a \(\mathbf{N}\) je normálový vektor povrchu.

3. **Speculární osvětlení**: Osvětlení, které vytváří lesklé skvrny na povrchu a závisí na úhlu mezi pozorovatelem a odraženým světlem.

    \[
    I_s = k_s \cdot I_{s_{light}} \cdot (\mathbf{R} \cdot \mathbf{V})^n
    \]

    kde \(k_s\) je spekulární reflexe materiálu, \(I_{s_{light}}\) je intenzita spekulárního světla, \(\mathbf{R}\) je odražený vektor, \(\mathbf{V}\) je vektor k pozorovateli a \(n\) je exponent materiálu určující lesklost.

Celková intenzita světla na povrchu je pak součtem těchto složek:

\[
I = I_a + I_d + I_s
\]

#### Řešení viditelnosti

Řešení viditelnosti je proces určení, které části objektů jsou viditelné a které jsou zakryty jinými objekty. Metody zahrnují:

1. **Z-buffering**: Každý pixel na obrazovce má uloženou hodnotu hloubky. Při rasterizaci nového pixelu se porovná jeho hloubka s hodnotou v Z-bufferu a uloží se pouze pokud je blíže ke kameře.

2. **Painters Algorithm**: Objekty jsou vykreslovány v pořadí od nejvzdálenějších k nejbližším, takže bližší objekty překryjí vzdálenější.

#### Identifikace těles

Identifikace těles je proces rozpoznání a rozlišení jednotlivých objektů ve scéně. Metody zahrnují:

1. **Bounding Boxes**: Obklopující rámy, které zjednodušují výpočty kolizí a viditelnosti.
2. **Hierarchical Models**: Struktury jako hierarchie kostí pro animace nebo hierarchické bounding boxes pro složitější objekty.

#### Standard OpenGL a jazyk GLSL

1. **OpenGL**: OpenGL (Open Graphics Library) je široce používaný standard pro vykreslování 2D a 3D grafiky. Poskytuje API pro práci s grafickým hardwarem a je nezávislý na platformě. OpenGL zahrnuje funkce pro zpracování geometrie, textur, osvětlení a dalších grafických prvků.

    - **Kreslení základních tvarů**: Funkce jako `glBegin()`, `glEnd()`, `glVertex3f()` pro specifikaci vrcholů.
    - **Transformace**: Funkce jako `glTranslatef()`, `glRotatef()`, `glScalef()` pro manipulaci s objekty.
    - **Osvětlení a materiály**: Funkce jako `glLightfv()`, `glMaterialfv()` pro nastavení světel a materiálů.

2. **GLSL (OpenGL Shading Language)**: GLSL je jazyk pro psaní shaderů v OpenGL. Shadery jsou malé programy, které běží na GPU a provádějí výpočty pro vykreslování grafiky.

    - **Vertex Shaders**: Manipulují s vrcholy objektů.
    - **Fragment Shaders**: Manipulují s pixely a určí konečnou barvu každého pixelu.
    - **Shader Pipeline**: Data procházejí pipeline od vertex shaderu přes fragment shader až po vykreslení na obrazovce.

```glsl
// Příklad jednoduchého fragment shaderu v GLSL
#version 330 core
out vec4 FragColor;

void main()
{
    FragColor = vec4(1.0, 0.5, 0.2, 1.0); // Nastaví barvu pixelu na oranžovou
}
```

### Shrnutí

Standardní zobrazovací řetězec zahrnuje všechny kroky od modelování a transformace objektů, přes osvětlení a řešení viditelnosti, až po finální vykreslení na obrazovku. Použití OpenGL a GLSL umožňuje efektivní a flexibilní vykreslování grafiky na různých platformách.