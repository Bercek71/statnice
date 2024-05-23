![[Okruhy#^fc96e8]]

### Metody strojového učení

Strojové učení (ML) zahrnuje algoritmy a statistické modely, které umožňují počítačům zlepšovat se v úkolech na základě dat, aniž by byly explicitně naprogramovány. Strojové učení lze rozdělit do několika hlavních kategorií:

1. **Supervised Learning (Učení s učitelem)**
2. **Unsupervised Learning (Učení bez učitele)**
3. **Reinforcement Learning (Učení posilováním)**

Zde se zaměříme na dvě hlavní kategorie: shlukování (klusterování) a klasifikace, a také na metody vyhodnocení algoritmů.

### Shlukování (Clustering)

Shlukování je metoda učení bez učitele, která se používá k rozdělení datových bodů do skupin nebo shluků tak, aby data v rámci každého shluku byla si navzájem podobná a data mezi shluky byla různá.

**Algoritmy pro shlukování:**

1. **K-means clustering:**
   - K-means je algoritmus, který rozdělí n datových bodů do k shluků, přičemž každý datový bod patří ke shluku s nejbližším středem.
   - **Kroky:**
     1. Vyber k počátečních centroidů.
     2. Přiřaď každý datový bod k nejbližšímu centroidu.
     3. Aktualizuj centroidy jako průměry datových bodů v každém shluku.
     4. Opakuj kroky 2 a 3, dokud se centroidy neustálí.

```python
from sklearn.cluster import KMeans
import matplotlib.pyplot as plt

# Generování dat
from sklearn.datasets import make_blobs
X, y = make_blobs(n_samples=300, centers=4, cluster_std=0.60, random_state=0)

# Trénování K-means
kmeans = KMeans(n_clusters=4)
kmeans.fit(X)
y_kmeans = kmeans.predict(X)

# Vizualizace
plt.scatter(X[:, 0], X[:, 1], c=y_kmeans, s=50, cmap='viridis')
centers = kmeans.cluster_centers_
plt.scatter(centers[:, 0], centers[:, 1], c='red', s=200, alpha=0.75)
plt.show()
```

2. **Hierarchical clustering:**
   - Hierarchické shlukování vytváří hierarchii shluků, které mohou být reprezentovány dendrogramem.
   - Existují dva hlavní typy: aglomerativní (zdola nahoru) a divizivní (shora dolů).

```python
from scipy.cluster.hierarchy import dendrogram, linkage
from matplotlib import pyplot as plt

# Generování dat
X, y = make_blobs(n_samples=50, centers=3, random_state=0)

# Vytvoření propojení
Z = linkage(X, 'ward')

# Vykreslení dendrogramu
dendrogram(Z)
plt.show()
```

### Klasifikace (Classification)

Klasifikace je metoda učení s učitelem, kde se algoritmy učí z trénovacích dat obsahujících vstupy a odpovídající výstupy (štítky) a pak používají toto učení k predikci štítků pro nové, neznámé vstupy.

**Algoritmy pro klasifikaci:**

1. **Logistická regrese:**
   - Logistická regrese se používá pro binární klasifikaci a předpovídá pravděpodobnost, že vzorek patří do jedné ze dvou kategorií.

```python
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import classification_report

# Generování dat
from sklearn.datasets import make_classification
X, y = make_classification(n_samples=1000, n_features=20, random_state=0)

# Rozdělení dat
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=0)

# Trénování modelu
model = LogisticRegression()
model.fit(X_train, y_train)

# Predikce
y_pred = model.predict(X_test)

# Vyhodnocení
print(classification_report(y_test, y_pred))
```

2. **K-nearest neighbors (KNN):**
   - KNN je jednoduchý algoritmus, který klasifikuje vzorek na základě toho, ke které třídě patří většina jeho k nejbližších sousedů.

```python
from sklearn.neighbors import KNeighborsClassifier

# Trénování modelu
knn = KNeighborsClassifier(n_neighbors=3)
knn.fit

(X_train, y_train)

# Predikce
y_pred = knn.predict(X_test)

# Vyhodnocení
print(classification_report(y_test, y_pred))
```

3. **Support Vector Machines (SVM):**
   - SVM je algoritmus, který hledá optimální hyperrovinu oddělující různé třídy v trénovacích datech.

```python
from sklearn.svm import SVC

# Trénování modelu
svm = SVC()
svm.fit(X_train, y_train)

# Predikce
y_pred = svm.predict(X_test)

# Vyhodnocení
print(classification_report(y_test, y_pred))
```

### Vyhodnocení algoritmů

Vyhodnocení algoritmů je klíčovým krokem ve strojovém učení, který určuje, jak dobře model funguje na neviděných datech. Existuje několik metrik pro vyhodnocení klasifikačních modelů:

1. **Přesnost (Accuracy):**
   - Podíl správně předpovězených štítků k celkovému počtu předpovězených štítků.
   - \[ \text{Přesnost} = \frac{\text{počet správných predikcí}}{\text{celkový počet predikcí}} \]

2. **Precision, Recall a F1-Score:**
   - **Precision**: Podíl správně předpovězených pozitivních výsledků k celkovému počtu předpovězených pozitivních výsledků.
   - \[ \text{Precision} = \frac{TP}{TP + FP} \]
   - **Recall (Sensitivity)**: Podíl správně předpovězených pozitivních výsledků k celkovému počtu skutečných pozitivních výsledků.
   - \[ \text{Recall} = \frac{TP}{TP + FN} \]
   - **F1-Score**: Harmonický průměr mezi precision a recall.
   - \[ \text{F1-Score} = 2 \cdot \frac{\text{Precision} \cdot \text{Recall}}{\text{Precision} + \text{Recall}} \]

3. **ROC křivka a AUC (Area Under Curve):**
   - ROC křivka zobrazuje True Positive Rate (TPR) proti False Positive Rate (FPR) při různých prahových hodnotách.
   - AUC je plocha pod ROC křivkou a poskytuje souhrnné měřítko výkonu klasifikačního modelu.

```python
from sklearn.metrics import roc_curve, auc

# Predikce pravděpodobností
y_prob = svm.decision_function(X_test)

# Výpočet ROC křivky
fpr, tpr, thresholds = roc_curve(y_test, y_prob)
roc_auc = auc(fpr, tpr)

# Vykreslení ROC křivky
plt.figure()
plt.plot(fpr, tpr, color='darkorange', lw=2, label='ROC curve (area = %0.2f)' % roc_auc)
plt.plot([0, 1], [0, 1], color='navy', lw=2, linestyle='--')
plt.xlim([0.0, 1.0])
plt.ylim([0.0, 1.05])
plt.xlabel('False Positive Rate')
plt.ylabel('True Positive Rate')
plt.title('Receiver Operating Characteristic')
plt.legend(loc="lower right")
plt.show()
```

### Shlukování (Clustering) - Detaily

#### K-means Clustering

**Algoritmus:**
1. Inicializace \(k\) centroids náhodně z dat.
2. Přiřazení každého bodu k nejbližšímu centroidu.
3. Přepočítání pozic centroidů jako průměr bodů přiřazených k nim.
4. Opakování kroků 2 a 3, dokud centroidy nezůstanou stálé.

**Výhody:**
- Jednoduchost a rychlost.
- Dobré pro dobře rozdělené shluky.

**Nevýhody:**
- Počet shluků \(k\) musí být znám předem.
- Citlivost na počáteční umístění centroidů a na odlehlé hodnoty.

#### Hierarchical Clustering

**Aglomerativní shlukování:**
1. Začínáme s každým datovým bodem jako samostatným shlukem.
2. Postupně spojujeme nejbližší shluky, dokud nezbývá jeden shluk nebo nevyhovíme zadanému počtu shluků.

**Výhody:**
- Není nutné specifikovat počet shluků předem.
- Vytváří hierarchickou strukturu (dendrogram).

**Nevýhody:**
- Výpočetně náročné pro velké datové sady.
- Výběr metriky a způsobu spojování může ovlivnit výsledky.

### Klasifikace (Classification) - Detaily

#### Logistická regrese

Logistická regrese modeluje pravděpodobnost, že vzorek patří do určité třídy.

**Logistická funkce:**
\[ \sigma(z) = \frac{1}{1 + e^{-z}} \]

**Výhody:**
- Interpretovatelnost koeficientů.
- Dobré pro binární klasifikaci.

**Nevýhody:**
- Předpoklad lineární závislosti mezi vstupními proměnnými a logitovou proměnnou.
- Nevhodné pro nelineární problémy.

#### K-nearest neighbors (KNN)

KNN klasifikuje vzorek na základě třídy většiny jeho nejbližších sousedů.

**Výhody:**
- Jednoduchost a neparametrická povaha.
- Dobré pro malé datové sady.

**Nevýhody:**
- Výpočetně náročné pro velké datové sady.
- Citlivost na škálování dat a hodnotu \(k\).

### Vyhodnocení algoritmů - Detaily

#### Přesnost, Precision, Recall, F1-Score

Přesnost je jednoduchá metrika, ale může být zavádějící u nevyvážených dat.

**Precision a Recall:**
- Precision se zaměřuje na to, jak mnoho z našich predikovaných pozitivních případů je skutečně pozitivních.
- Recall se zaměřuje na to, jak mnoho z celkových skutečných pozitivních případů jsme správně identifikovali.

**F1-Score:**
- Harmonický průměr mezi precision a recall, což zajišťuje, že model dosahuje dobré rovnováhy mezi nimi.

#### ROC křivka a AUC

**ROC křivka:**
- Graficky zobrazuje trade-off mezi TPR a FPR pro různé prahové hodnoty.
- Umožňuje vizualizovat výkon modelu bez ohledu na prahovou hodnotu.

**AUC:**
- Poskytuje jedno číslo, které shrnuje výkon modelu.
- Hodnoty blížící se 1 indikují lepší výkon.

### Závěr

Metody strojového učení poskytují různé přístupy k analýze a predikci dat. Shlukování je užitečné pro objevování struktur v datech bez předchozích znalostí, zatímco klasifikace je užitečná pro predikci kategorií na základě trénovacích dat. Vyhodnocení algoritmů pomocí různých metrik je klíčové pro pochopení jejich výkonu a výběr nejvhodnějšího modelu pro konkrétní úlohu.
