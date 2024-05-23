![[Okruhy#^ffe13c]]

### Explorativní analýza dat (EDA)

Explorativní analýza dat (EDA) je proces, který zahrnuje vizuální a statistické techniky pro shrnutí a pochopení hlavních charakteristik datových sad. Cílem EDA je odhalit vzorce, vztahy a anomálie v datech před použitím složitějších modelů.

#### Typy datových atributů

1. **Numerické atributy**:
   - **Kontinuální**: Mohou nabývat libovolných hodnot v určitém intervalu (např. hmotnost, výška).
   - **Diskrétní**: Mohou nabývat jen určitých hodnot, obvykle celých čísel (např. počet dětí, počet aut).

2. **Kategorie atributy**:
   - **Nominalní (nominální)**: Kategorizují data bez jakéhokoliv řádu (např. barva očí, druh zvířete).
   - **Ordinalní (ordinální)**: Kategorizují data s určitou pořadovou významností (např. stupně hodnocení, pořadí v závodě).

3. **Binární atributy**:
   - Speciální typ kategoriálních atributů, které mají pouze dvě možné hodnoty (např. ano/ne, pravda/nepravda).

4. **Datové a časové atributy**:
   - Specifické atributy představující datum a čas, které mohou být analyzovány jako kontinuální nebo kategoriální data v závislosti na kontextu.

### Statistické vlastnosti dat

1. **Centrální tendence**:
   - **Průměr**: Součet hodnot dělený počtem hodnot.
   - **Medián**: Střední hodnota datového souboru, pokud jsou data seřazena.
   - **Modus**: Nejčastěji se vyskytující hodnota.

2. **Rozptyl a šířka rozdělení**:
   - **Rozptyl (Variance)**: Průměr čtverců odchylek hodnot od průměru.
   - **Směrodatná odchylka (Standard Deviation)**: Druhá odmocnina z rozptylu.
   - **Kvartily**: Hodnoty, které rozdělují datový soubor na čtvrtiny.
   - **Interkvartilové rozpětí (IQR)**: Rozdíl mezi třetím a prvním kvartilem.

3. **Šikmost (Skewness)**:
   - Míra asymetrie rozdělení dat kolem průměru.

4. **Špičatost (Kurtosis)**:
   - Míra "ostrosti" vrcholu rozdělení dat.

### Vztahy mezi atributy

1. **Korelace**:
   - Míra lineárního vztahu mezi dvěma numerickými atributy.
   - **Pearsonův korelační koeficient (r)**: Hodnoty od -1 (dokonalá záporná korelace) do 1 (dokonalá kladná korelace).

$$r = \frac{\sum (x_i - \bar{x})(y_i - \bar{y})}{\sqrt{\sum (x_i - \bar{x})^2 \sum (y_i - \bar{y})^2}}$$

2. **Kovariance**:
   - Míra, jak dva atributy mění společně, avšak neškálovaná na rozsah (-1, 1).

$$\text{Cov}(X, Y) = \frac{\sum (x_i - \bar{x})(y_i - \bar{y})}{n-1}$$

3. **Kontingenční tabulky**:
   - Tabulky používané k analýze vztahů mezi dvěma kategoriálními atributy.

4. **Vizuální techniky**:
   - **Histogram**: Ukazuje rozdělení jedné numerické proměnné.
   - **Boxplot**: Vizualizuje medián, kvartily a případné odlehlé hodnoty.
   - **Scatter plot (bodový graf)**: Zobrazuje vztah mezi dvěma numerickými proměnnými.
   - **Heatmapa**: Vizualizuje korelační matici nebo frekvence v kontingenční tabulce.
   - **Pair plot**: Kombinovaný graf zobrazující všechny možné dvojice vztahů mezi několika numerickými atributy.


### Příklady statistických měr

**Průměr:**

$$ \bar{x} = \frac{1}{n} \sum_{i=1}^{n} x_i $$

**Rozptyl:**

$$ \sigma^2 = \frac{1}{n} \sum_{i=1}^{n} (x_i - \bar{x})^2$$

**Směrodatná odchylka:**

$$\sigma = \sqrt{\sigma^2}$$

**Pearsonův korelační koeficient:**

$$r = \frac{\sum (x_i - \bar{x})(y_i - \bar{y})}{\sqrt{\sum (x_i - \bar{x})^2 \sum (y_i - \bar{y})^2}}$$

Tímto způsobem můžeme provádět explorativní analýzu dat a získat cenné informace o vlastnostech a vztazích v datové sadě. Pokud máš další otázky nebo potřebuješ více podrobností, neváhej se zeptat!