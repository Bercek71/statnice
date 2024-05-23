![[Okruhy#^f2b26e]]

### Základní datové struktury

Datové struktury jsou způsoby organizace a ukládání dat tak, aby bylo možné je efektivně používat. Níže jsou popsány některé z nejdůležitějších základních datových struktur:

#### 1. Pole (Array)
- **Definice**: Statická datová struktura, která ukládá prvky stejného typu v kontinuální paměťové oblasti.
- **Přístup k prvkům**: O(1)
- **Operace**: Vkládání a mazání prvků je O(n) v nejhorším případě (kvůli potřebě přeuspořádání prvků).

**Příklad:**
```python
arr = [1, 2, 3, 4, 5]
print(arr[2])  # Výstup: 3
```

#### 2. Seznam (Linked List)
- **Definice**: Dynamická datová struktura, kde každý prvek (uzel) obsahuje hodnotu a ukazatel na další prvek.
- **Typy**: Jednosměrně vázaný seznam (Singly Linked List), obousměrně vázaný seznam (Doubly Linked List).
- **Přístup k prvkům**: O(n)
- **Operace**: Vkládání a mazání prvků je O(1) při známé pozici.

**Příklad:**
```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

head = Node(1)
head.next = Node(2)
head.next.next = Node(3)
```

#### 3. Zásobník (Stack)
- **Definice**: Datová struktura, která funguje na principu LIFO (Last In, First Out).
- **Operace**: push (vložit prvek), pop (odstranit prvek), top/peek (nahlédnout na vrchol).
- **Časová složitost**: O(1) pro všechny operace.

**Příklad:**
```python
stack = []
stack.append(1)  # push
stack.append(2)
stack.pop()      # pop
```

#### 4. Fronta (Queue)
- **Definice**: Datová struktura, která funguje na principu FIFO (First In, First Out).
- **Operace**: enqueue (vložit prvek), dequeue (odstranit prvek), front (nahlédnout na přední prvek).
- **Časová složitost**: O(1) pro všechny operace.

**Příklad:**
```python
from collections import deque
queue = deque()
queue.append(1)  # enqueue
queue.append(2)
queue.popleft()  # dequeue
```

#### 5. Graf (Graph)
- **Definice**: Datová struktura sestávající z vrcholů (nodes) a hran (edges) spojujících dvojice vrcholů.
- **Typy**: Orientovaný (directed) nebo neorientovaný (undirected).
- **Reprezentace**: Matice sousednosti (adjacency matrix), seznam sousednosti (adjacency list).

**Příklad:**
```python
graph = {
    'A': ['B', 'C'],
    'B': ['A', 'D', 'E'],
    'C': ['A', 'F'],
    'D': ['B'],
    'E': ['B', 'F'],
    'F': ['C', 'E']
}
```

#### 6. Vyhledávací strom (Binary Search Tree, BST)
- **Definice**: Binární strom, kde každý uzel má nejvýše dva potomky a hodnoty v levém podstromu jsou menší než hodnota v uzlu, zatímco hodnoty v pravém podstromu jsou větší.
- **Operace**: Vložení, smazání a hledání prvek O(h), kde h je výška stromu.

**Příklad:**
```python
class TreeNode:
    def __init__(self, key):
        self.left = None
        self.right = None
        self.val = key

root = TreeNode(10)
root.left = TreeNode(5)
root.right = TreeNode(20)
```

### Halda (Heap)

Halda je specializovaný stromový datový typ, který splňuje vlastnost haldy. V max-heapu je každý rodičovský uzel větší nebo rovný svým dětem, zatímco v min-heapu je každý rodičovský uzel menší nebo rovný svým dětem. 

#### Ukládání prvků na haldě

Halda se často implementuje pomocí pole, což umožňuje efektivní přístup k rodičům a dětem.

**Indexace:**
- Pro uzel na indexu \(i\):
  - Levý potomek je na indexu \(2i + 1\).
  - Pravý potomek je na indexu \(2i + 2\).
  - Rodič je na indexu \(\lfloor (i - 1) / 2 \rfloor\).

**Vložení prvku (Insert):**
1. **Přidej prvek na konec** pole (do první volné pozice).
2. **Proplachování nahoru (Heapify Up)**:
   - Porovnej nový prvek s jeho rodičem.
   - Pokud je nový prvek větší (u max-heapu) nebo menší (u min-heapu) než rodič, vyměň je.
   - Opakuj proces, dokud není vlastnost haldy obnovena nebo nedosáhneš kořene stromu.

**Příklad:**

Předpokládejme, že máme max-heap a chceme vložit prvek 15:

```plaintext
Pole před vložením: [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]
Po vložení 15:      [10, 9, 8, 7, 6, 5, 4, 3, 2, 1, 15]

Proplachování nahoru:
1. 15 (index 10) vs. 6 (index 4) - výměna
2. 15 (index 4) vs. 9 (index 1) - výměna
3. 15 (index 1) vs. 10 (index 0) - výměna

Pole po vložení:   [15, 10, 8, 7, 9, 5, 4, 3, 2, 1, 6]
```

**Odstranění kořene (Delete Root):**
1. **Vyměň kořen** s posledním prvkem v poli.
2. **Odstraň poslední prvek** (nyní kořen).
3. **Proplachování dolů (Heapify Down)**:
   - Porovnej nový kořen s jeho dětmi.
   - Pokud je kořen menší (u max-heapu) nebo větší (u min-heapu) než některé dítě, vyměň je s největším (u max-heapu) nebo nejmenším (u min-heapu) dítětem.
   - Opakuj proces, dokud není vlastnost haldy obnovena nebo nedosáhneš listu stromu.

**Příklad:**

Předpokládejme, že máme max-heap a chceme odstranit kořen (15):

```plaintext
Pole před odstraněním: [15, 10, 8, 7, 9, 5, 4, 3, 2, 1, 6]
Výměna kořene a posledního prvku: [6, 10, 8, 7, 9, 5, 4, 3, 2, 1]

Proplachování dolů:
1. 6 (index 0) vs. 10 (index 1) - výměna
2. 6 (index 1) vs. 9 (index 4) - výměna

Pole po odstranění: [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]
```

### Hašovací tabulka (Hash Table)

Hašovací tabulka je datová struktura, která mapuje klíče na hodnoty pomocí hashovací funkce. Tato funkce převádí klíče na indexy v poli, kde jsou uloženy hodnoty.

#### Hashování a kolize

**Hashovací funkce:** 
- Funkce, která bere klíč a vrací index v poli.
- Měla by být rychlá a rozložit klíče rovnoměrně.

**Kolize:** 
- Nastává, když dva různé klíče mají stejný hash (index).
- Musí být řešeny efektivním způsobem.

**Řešení kolizí:**

1. **Řetězení (Chaining):**
   - Každý prvek pole je ukazatelem na seznam

 (obvykle spojený seznam).
   - V případě kolize se prvek přidá na začátek nebo konec seznamu.

   ```python
   class HashTable:
       def __init__(self):
           self.size = 10
           self.table = [[] for _ in range(self.size)]
       
       def hash_function(self, key):
           return hash(key) % self.size
       
       def insert(self, key, value):
           index = self.hash_function(key)
           for kv in self.table[index]:
               if kv[0] == key:
                   kv[1] = value
                   return
           self.table[index].append([key, value])
       
       def get(self, key):
           index = self.hash_function(key)
           for kv in self.table[index]:
               if kv[0] == key:
                   return kv[1]
           return None
   ```

2. **Otevřené adresování (Open Addressing):**
   - Při kolizi se hledá další volné místo v poli podle určitého pravidla (např. lineární prohledávání, kvadratické prohledávání).

   **Lineární prohledávání (Linear Probing):**
   - Pokud je místo obsazeno, prohledává se pole sekvenčně, dokud se nenajde volné místo.
   ```plaintext
   index = (hash(key) + i) % size, kde i = 0, 1, 2, ...
   ```

   **Kvadratické prohledávání (Quadratic Probing):**
   - Pokud je místo obsazeno, prohledává se pole kvadratickým skokem.
   ```plaintext
   index = (hash(key) + i^2) % size, kde i = 0, 1, 2, ...
   ```

   **Dvojité hashování (Double Hashing):**
   - Používají se dvě hashovací funkce. Druhá hashovací funkce určuje skok.
   ```plaintext
   index = (hash1(key) + i * hash2(key)) % size, kde i = 0, 1, 2, ...
   ```

**Příklad (Řetězení):**

```python
hash_table = HashTable()
hash_table.insert("apple", 5)
hash_table.insert("banana", 3)
hash_table.insert("orange", 8)

print(hash_table.get("apple"))   # Výstup: 5
print(hash_table.get("banana"))  # Výstup: 3
print(hash_table.get("orange"))  # Výstup: 8
```

### Shrnutí

Každá datová struktura má své specifické použití a efektivitu pro různé typy operací:

- **Pole**: Rychlý přístup k prvkům, náročné vkládání a mazání.
- **Seznam**: Efektivní vkládání a mazání prvků, pomalý přístup.
- **Zásobník**: LIFO, efektivní operace.
- **Fronta**: FIFO, efektivní operace.
- **Graf**: Flexibilní reprezentace vztahů mezi uzly.
- **Vyhledávací strom**: Rychlé vyhledávání, vkládání a mazání.
- **Halda**: Efektivní prioritní fronta, efektivní vkládání a mazání kořene.
- **Hašovací tabulka**: Rychlé vyhledávání, vkládání a mazání, řešení kolizí pomocí řetězení nebo otevřeného adresování.
