![[Okruhy#^574e1d]]


Geometrické modelování je klíčovou součástí počítačové grafiky, která se zabývá reprezentací a manipulací s geometrickými tvary a objekty. Zahrnuje několik konceptů, jako jsou afinní a projektivní prostory, reprezentace těles, a křivky jako Fergusonova kubika a Bézierova křivka.

#### Afinní a projektivní prostory

1. **Afinní prostor**:
   - Afinní prostor je geometrická struktura, která rozšiřuje vektorové prostory o možnost translací. 
   - Zahrnuje body, přímky, roviny a další geometrické objekty, které se zachovávají při afinních transformacích (např. translace, rotace, škálování, střih).

2. **Projektivní prostor**:
   - Projektivní prostor je rozšířením afinního prostoru, který zahrnuje koncept bodů v nekonečnu.
   - Transformace v projektivním prostoru zahrnují perspektivní projekce, které umožňují realistické zobrazování trojrozměrných objektů na dvojrozměrném zobrazovacím médiu.

#### Popis těles a možnosti jejich reprezentace

1. **Hraniční reprezentace (Boundary Representation, B-Rep)**:
   - Popisuje povrch tělesa pomocí vrcholů, hran a stěn.
   - Výhoda: Přesná reprezentace tvarů a povrchů.
   - Nevýhoda: Složitá manipulace a úpravy geometrie.

2. **Konstrukční geometrie (Constructive Solid Geometry, CSG)**:
   - Popisuje tělesa pomocí kombinací základních primitiv (koule, kvádry, válce) pomocí množinových operací (sjednocení, průnik, rozdíl).
   - Výhoda: Snadná manipulace a modifikace těles.
   - Nevýhoda: Může být složitější dosáhnout velmi detailních tvarů.

3. **Voxelové reprezentace**:
   - Tělesa jsou reprezentována jako mřížka objemových prvků (voxelů).
   - Výhoda: Jednoduchá implementace a vhodné pro volumetrická data.
   - Nevýhoda: Vysoká paměťová náročnost a nízké rozlišení detailů.

#### Základní křivky používané v počítačové grafice

1. **Fergusonova kubika**:
   - Používá se k reprezentaci hladkých křivek pomocí kubických polynomů.
   - Vlastnosti: Hladké spojení segmentů křivky, jednoduchá implementace.
   - Použití: Modelování hladkých přechodů a tvarů.

   Fergusonova kubika je definována jako kubická interpolace mezi body a tangenty na koncích segmentu:

   $$
   P(t) = (2t^3 - 3t^2 + 1)P_0 + (t^3 - 2t^2 + t)M_0 + (-2t^3 + 3t^2)P_1 + (t^3 - t^2)M_1
   $$

   kde ( $P_0$ ) a ( $P_1$ ) jsou koncové body, ($M_0$ ) a ( $M_1$ ) jsou odpovídající tangenty a ( t ) je parametr v rozmezí [0, 1].

2. **Bézierova křivka**:
   - Používá se pro modelování hladkých křivek, které jsou definovány kontrolními body.
   - Vlastnosti: Křivka vždy prochází prvním a posledním kontrolním bodem a je ovlivněna polohou ostatních kontrolních bodů.
   - Použití: Grafický design, vektorová grafika, animace.

   Bézierova křivka je definována Bernsteinovými polynomy a kontrolními body $( P_0, P_1, ..., P_n )$:

   $$ B(t) = \sum_{i=0}^{n} \binom{n}{i} (1-t)^{n-i} t^i P_i $$

   kde \( $t$ \) je parametr v rozmezí $[0, 1]$ a ( $\binom{n}{i}$ ) je binomický koeficient.

#### Vlastnosti a použití základních křivek

1. **Interpolace**: Fergusonova kubika a Bézierova křivka mohou být použity pro interpolaci mezi danými body, což je užitečné pro vytváření hladkých přechodů.
2. **Kontrola tvaru**: Kontrolní body Bézierovy křivky poskytují intuitivní způsob, jak ovládat tvar křivky.
3. **Hladkost**: Kubické křivky (jako Fergusonova a Bézierova) zajišťují hladké spojení mezi segmenty, což je důležité pro realistické modelování.

### Stručná charakteristika standardu OpenGL a jazyka GLSL

1. **OpenGL**:
   - OpenGL (Open Graphics Library) je otevřený standard pro vykreslování 2D a 3D grafiky.
   - Poskytuje rozsáhlé API pro práci s grafickým hardwarem a podporuje různé grafické operace, jako jsou transformace, osvětlení, texturování a rasterizace.
   - OpenGL je platformově nezávislé a široce podporované na různých operačních systémech a zařízeních.

2. **GLSL (OpenGL Shading Language)**:
   - GLSL je jazyk pro psaní shaderů v OpenGL. Shadery jsou malé programy, které běží na GPU a provádějí výpočty pro vykreslování grafiky.
   - Existují různé typy shaderů, včetně vertex shaderů, fragment shaderů a geometry shaderů.
   - GLSL umožňuje programátorům psát vlastní algoritmy pro zpracování vrcholů, pixelů a dalších grafických prvků, což poskytuje vysokou flexibilitu a možnosti optimalizace.

### Shrnutí

Geometrické modelování zahrnuje mnoho technik a konceptů, které umožňují realistickou a efektivní reprezentaci a manipulaci s 3D objekty. Afinní a projektivní prostory, různé metody reprezentace těles, základní křivky jako Fergusonova kubika a Bézierova křivka jsou klíčovými prvky tohoto procesu. Standardy jako OpenGL a jazyk GLSL poskytují potřebné nástroje a prostředí pro realizaci těchto technik v praxi.