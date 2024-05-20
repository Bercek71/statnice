![[Okruhy#^631b5b]]

### Návrh a implementace datové vrstvy

Návrh a implementace datové vrstvy je klíčovým krokem při vývoji softwarového systému, který zajišťuje správu a přístup k datům uloženým v databázi. Tento proces zahrnuje několik konceptů a technik, jako je objektově-relační mapování (ORM), Data Transfer Objects (DTO), Data Access Objects (DAO) a efektivní implementace datové vrstvy.

#### Objektově-relační mapování (ORM)

Objektově-relační mapování je technika, která spojuje objektově-orientovaný programovací model s relačním databázovým modelem. ORM nástroje umožňují vývojářům pracovat s databázovými daty jako s objekty v programovacím jazyce, což usnadňuje práci s daty a zlepšuje produktivitu.

**Hlavní výhody ORM:**
- **Abstrakce databázových operací**: Vývojáři pracují s objekty namísto přímého psaní SQL dotazů.
- **Automatické mapování**: ORM automaticky mapuje tabulky a sloupce na třídy a atributy.
- **Podpora různých databází**: ORM nástroje obvykle podporují různé databázové systémy, což umožňuje snadnou změnu databáze bez velkých úprav kódu.

**Příklad ORM (Hibernate, JPA):**
```java
@Entity
public class Student {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String jmeno;
    private LocalDate datumNarozeni;

    // Gettery a settery
}
```

#### Data Transfer Objects (DTO)

DTO je vzor používaný k přenosu dat mezi vrstvami aplikace. DTO jsou jednoduché objekty, které nemají žádnou logiku, pouze obsahují data.

**Výhody DTO:**
- **Oddělení vrstev**: DTO oddělují prezentační a datovou vrstvu, což zlepšuje modularitu.
- **Optimalizace přenosu dat**: DTO mohou obsahovat pouze potřebná data, čímž se minimalizuje objem přenášených dat.

**Příklad DTO:**
```java
public class StudentDTO {
    private Long id;
    private String jmeno;
    private LocalDate datumNarozeni;

    // Gettery a settery
}
```

#### Data Access Objects (DAO)

DAO je vzor používaný k oddělení aplikační logiky od logiky přístupu k datům. DAO poskytují metody pro CRUD operace (Create, Read, Update, Delete) nad entitami.

**Výhody DAO:**
- **Oddělení logiky**: DAO odděluje přístup k datům od aplikační logiky.
- **Znovupoužitelnost**: Kód pro přístup k datům je centralizovaný a znovupoužitelný.
- **Snadná údržba**: Změny v databázové logice jsou omezeny na DAO třídy, což usnadňuje údržbu.

**Příklad DAO:**
```java
public interface StudentDAO {
    void save(Student student);
    Student findById(Long id);
    List<Student> findAll();
    void update(Student student);
    void delete(Student student);
}

public class StudentDAOImpl implements StudentDAO {
    // Implementace CRUD operací pomocí ORM frameworku (např. Hibernate)
}
```

#### Efektivní implementace datové vrstvy

Efektivní implementace datové vrstvy zahrnuje několik klíčových aspektů, které zajišťují výkon, škálovatelnost a udržovatelnost aplikace.

1. **Použití ORM frameworku**:
   - ORM frameworky, jako jsou Hibernate nebo JPA, zjednodušují práci s databází a zajišťují automatické mapování mezi objekty a databázovými tabulkami.

2. **Optimalizace dotazů**:
   - Používání lazy loading pro odložení načítání souvisejících entit, dokud nejsou skutečně potřeba.
   - Využití nativních SQL dotazů nebo pojmenovaných dotazů pro složité dotazy, které by byly neefektivní v HQL nebo JPQL.

3. **Cache**:
   - Implementace cache na úrovni druhé úrovně (second-level cache) pro snížení počtu dotazů na databázi.
   - Využití cache frameworků, jako je Ehcache nebo Hazelcast.

4. **Transakční řízení**:
   - Použití transakčního řízení k zajištění atomických operací a zachování konzistence dat.
   - Využití @Transactional anotace v Spring frameworku nebo ekvivalentních mechanismů v jiných frameworkech.

5. **Jednotkové testy a integrační testy**:
   - Vytváření jednotkových testů pro DAO vrstvy pomocí testovacích rámců jako JUnit nebo TestNG.
   - Použití nástrojů jako H2 databáze pro integrační testy bez potřeby přístupu k produkční databázi.

**Příklad DAO implementace s použitím Spring a JPA:**
```java
@Repository
public class StudentDAOImpl implements StudentDAO {

    @PersistenceContext
    private EntityManager entityManager;

    @Transactional
    @Override
    public void save(Student student) {
        entityManager.persist(student);
    }

    @Override
    public Student findById(Long id) {
        return entityManager.find(Student.class, id);
    }

    @Override
    public List<Student> findAll() {
        String query = "SELECT s FROM Student s";
        return entityManager.createQuery(query, Student.class).getResultList();
    }

    @Transactional
    @Override
    public void update(Student student) {
        entityManager.merge(student);
    }

    @Transactional
    @Override
    public void delete(Student student) {
        if (entityManager.contains(student)) {
            entityManager.remove(student);
        } else {
            entityManager.remove(entityManager.merge(student));
        }
    }
}
```

### Shrnutí

Návrh a implementace datové vrstvy zahrnuje použití několika designových vzorů a technik, jako je ORM pro zjednodušení práce s databází, DTO pro efektivní přenos dat mezi vrstvami, DAO pro oddělení přístupu k datům od aplikační logiky a různé optimalizační techniky pro zajištění výkonu a škálovatelnosti aplikace. Tyto techniky společně zajišťují, že datová vrstva je dobře strukturovaná, udržovatelná a výkonná.