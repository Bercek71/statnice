![[Okruhy#^66df3a]]
#### SQL (Structured Query Language)

SQL je standardizovaný jazyk pro práci s relačními databázemi. SQL zahrnuje jazyk pro definici dat (DDL), jazyk pro manipulaci s daty (DML), jazyk pro řízení dat (DCL) a jazyk pro dotazování dat (SELECT).

**Jazyk pro definici dat (DDL):**
DDL se používá k definování a modifikaci struktury databází a jejich objektů.

- **CREATE**: Vytváří nové objekty v databázi (např. tabulky, indexy).
  ```sql
  CREATE TABLE Student (
      id INT PRIMARY KEY,
      jmeno VARCHAR(50),
      datum_narozeni DATE
  );
  ```
- **ALTER**: Modifikuje existující objekty v databázi.
  ```sql
  ALTER TABLE Student ADD email VARCHAR(100);
  ```
- **DROP**: Odstraňuje objekty z databáze.
  ```sql
  DROP TABLE Student;
  ```

**Jazyk pro manipulaci s daty (DML):**
DML se používá k manipulaci s daty v rámci existujících objektů databáze.

- **INSERT**: Vkládá nová data do tabulek.
  ```sql
  INSERT INTO Student (id, jmeno, datum_narozeni) VALUES (1, 'Jan Novak', '1990-01-01');
  ```
- **UPDATE**: Aktualizuje existující data v tabulkách.
  ```sql
  UPDATE Student SET email = 'jan.novak@example.com' WHERE id = 1;
  ```
- **DELETE**: Odstraňuje data z tabulek.
  ```sql
  DELETE FROM Student WHERE id = 1;
  ```

**SELECT – dotazovací jazyk:**
SELECT se používá k dotazování dat z jedné nebo více tabulek.

- **Spojení (JOIN)**:
  Spojení tabulek na základě společného atributu.
  ```sql
  SELECT s.jmeno, k.nazev_kurzu
  FROM Student s
  JOIN Kurz k ON s.id = k.student_id;
  ```

- **Poddotazy (Subqueries)**:
  Dotazy vnořené uvnitř jiných dotazů.
  ```sql
  SELECT jmeno
  FROM Student
  WHERE id IN (SELECT student_id FROM Kurz WHERE nazev_kurzu = 'Databaze');
  ```

- **Agregační funkce**:
  Funkce pro sumarizaci dat.
  ```sql
  SELECT COUNT(*), AVG(vek), MAX(plat)
  FROM Zamestnanec;
  ```

#### Procedurální rozšíření SQL

**PL/SQL (Procedural Language/SQL):**
PL/SQL je procedurální rozšíření SQL používané v Oracle databázích.

- **Uložené procedury**: Bloky kódu, které lze opakovaně volat.
  ```sql
  CREATE OR REPLACE PROCEDURE ZvysPlat (
      p_id IN Zamestnanec.id%TYPE,
      p_castka IN NUMBER
  ) AS
  BEGIN
      UPDATE Zamestnanec SET plat = plat + p_castka WHERE id = p_id;
  END;
  ```

- **Kurzory**: Umožňují postupně procházet výsledky dotazu.
  ```sql
  DECLARE
      CURSOR c1 IS SELECT jmeno FROM Student;
      v_jmeno Student.jmeno%TYPE;
  BEGIN
      OPEN c1;
      LOOP
          FETCH c1 INTO v_jmeno;
          EXIT WHEN c1%NOTFOUND;
          DBMS_OUTPUT.PUT_LINE(v_jmeno);
      END LOOP;
      CLOSE c1;
  END;
  ```

- **Triggery**: Automaticky spouštěné bloky kódu při určité akci.
  ```sql
  CREATE OR REPLACE TRIGGER trg_zamestnanec
  BEFORE INSERT ON Zamestnanec
  FOR EACH ROW
  BEGIN
      IF :NEW.plat < 0 THEN
          RAISE_APPLICATION_ERROR(-20001, 'Plat nemůže být záporný.');
      END IF;
  END;
  ```

**T-SQL (Transact-SQL):**
T-SQL je procedurální rozšíření SQL používané v Microsoft SQL Serveru.

- **Uložené procedury**:
  ```sql
  CREATE PROCEDURE ZvysPlat
      @id INT,
      @castka DECIMAL
  AS
  BEGIN
      UPDATE Zamestnanec SET plat = plat + @castka WHERE id = @id;
  END;
  ```

- **Kurzory**:
  ```sql
  DECLARE @jmeno NVARCHAR(50);
  DECLARE c1 CURSOR FOR SELECT jmeno FROM Student;
  OPEN c1;
  FETCH NEXT FROM c1 INTO @jmeno;
  WHILE @@FETCH_STATUS = 0
  BEGIN
      PRINT @jmeno;
      FETCH NEXT FROM c1 INTO @jmeno;
  END;
  CLOSE c1;
  DEALLOCATE c1;
  ```

- **Triggery**:
  ```sql
  CREATE TRIGGER trg_zamestnanec
  ON Zamestnanec
  AFTER INSERT
  AS
  BEGIN
      IF EXISTS (SELECT * FROM inserted WHERE plat < 0)
      BEGIN
          RAISERROR ('Plat nemůže být záporný.', 16, 1);
          ROLLBACK TRANSACTION;
      END
  END;
  ```

**Obecné rysy procedurálních rozšíření:**
- **Uložené procedury**: Seskupení jednoho nebo více SQL příkazů do bloku, který může být uložen a volán podle potřeby.
- **Kurzory**: Mechanismy pro postupné procházení řádků výsledku dotazu.
- **Triggery**: Automatické spouštění akcí na základě změn v databázi, jako je INSERT, UPDATE nebo DELETE.

### Rozdíl mezi PL/SQL a T-SQL

**1. Syntaxe a funkcionalita:**
- **PL/SQL (Oracle)**
  - PL/SQL umožňuje použití operátorů %TYPE a %ROWTYPE pro deklaraci proměnných, které mají stejné datové typy jako sloupce tabulek.
  - PL/SQL podporuje konstrukci `CREATE OR REPLACE`, která umožňuje jednoduše aktualizovat existující procedury a triggery.
  - PL/SQL umožňuje zpracování výjimek s `EXCEPTION` blokem, který zachytává a zpracovává chyby.

  ```sql
  DECLARE
      v_jmeno Student.jmeno%TYPE;
  BEGIN
      BEGIN
          SELECT jmeno INTO v_jmeno FROM Student WHERE id = 1;
      EXCEPTION
          WHEN NO_DATA_FOUND THEN
              DBMS_OUTPUT.PUT_LINE('Student nebyl nalezen.');
      END;
  END;
  ```

- **T-SQL (Microsoft SQL Server)**
  - T-SQL nemá operátory %TYPE a %ROWTYPE, místo toho používá explicitní deklaraci proměnných.
  - T-SQL podporuje konstrukci `CREATE OR ALTER`, která je podobná `CREATE OR REPLACE` v PL/SQL (dostupné od verze SQL Server 2016).
  - T-SQL má jednodušší mechanizmus pro zpracování chyb pomocí `TRY...CATCH` bloků.

  ```sql
  DECLARE @jmeno NVARCHAR(50);
  BEGIN
      BEGIN TRY
          SELECT @jmeno = jmeno FROM Student WHERE id = 1;
      END TRY
      BEGIN CATCH
          PRINT 'Student nebyl nalezen.';
      END CATCH;
  END;
  ```

**2. Zpracování kurzorů:**
- **PL/SQL**
  - PL/SQL kurzory jsou definovány pomocí `DECLARE CURSOR` a mohou být otevřeny, načteny a zavřeny.
  - PL/SQL umožňuje použití implicitních kurzorů pomocí `FOR` smyček.

  ```sql
  DECLARE
      CURSOR c1 IS SELECT jmeno FROM Student;
      v_jmeno Student.jmeno%TYPE;
  BEGIN
      OPEN c1;
      LOOP
          FETCH c1 INTO v_jmeno;
          EXIT WHEN c1%NOTFOUND;
          DBMS_OUTPUT.PUT_LINE(v_jmeno);
      END LOOP;
      CLOSE c1;
  END;
  ```

- **T-SQL**
  - T-SQL kurzory jsou definovány pomocí `DECLARE CURSOR FOR` a musí být explicitně otevřeny, načteny, uzavřeny a deallokovány.
  - T-SQL kurzory vyžadují použití `FETCH NEXT` a `WHILE` smyček pro iteraci přes výsledky.

  ```sql
  DECLARE @jmeno NVARCHAR(50);
  DECLARE c1 CURSOR FOR SELECT jmeno FROM Student;
  OPEN c1;
  FETCH NEXT FROM c1 INTO @jmeno;
  WHILE @@FETCH_STATUS = 0
  BEGIN
      PRINT @jmeno;
      FETCH NEXT FROM c1 INTO @jmeno;
  END;
  CLOSE c1;
  DEALLOCATE c1;


  ```

**3. Triggery:**
- **PL/SQL**
  - PL/SQL triggery mohou být definovány pro různé události (např. `BEFORE INSERT`, `AFTER UPDATE`) a mohou používat speciální proměnné `:NEW` a `:OLD` pro přístup k novým a starým hodnotám.

  ```sql
  CREATE OR REPLACE TRIGGER trg_zamestnanec
  BEFORE INSERT ON Zamestnanec
  FOR EACH ROW
  BEGIN
      IF :NEW.plat < 0 THEN
          RAISE_APPLICATION_ERROR(-20001, 'Plat nemůže být záporný.');
      END IF;
  END;
  ```

- **T-SQL**
  - T-SQL triggery používají vložené (INSERTED) a smazané (DELETED) tabulky pro přístup k novým a starým hodnotám.
  - T-SQL triggery jsou definovány pomocí `CREATE TRIGGER` a mohou být spouštěny po (AFTER) nebo místo (INSTEAD OF) určité události.

  ```sql
  CREATE TRIGGER trg_zamestnanec
  ON Zamestnanec
  AFTER INSERT
  AS
  BEGIN
      IF EXISTS (SELECT * FROM inserted WHERE plat < 0)
      BEGIN
          RAISERROR ('Plat nemůže být záporný.', 16, 1);
          ROLLBACK TRANSACTION;
      END
  END;
  ```

**4. Zpracování chyb:**
- **PL/SQL** používá bloky `EXCEPTION` k zachycení a zpracování výjimek.
- **T-SQL** používá bloky `TRY...CATCH` k zachycení a zpracování výjimek.

**5. Specifické funkce a rozšíření:**
- **PL/SQL** má bohatou sadu vestavěných balíků, jako je `DBMS_OUTPUT` pro výstup z PL/SQL bloků.
- **T-SQL** poskytuje specifické funkce pro práci s Windows Azure a dalšími Microsoft technologiemi.

### Shrnutí

PL/SQL a T-SQL jsou mocná procedurální rozšíření SQL, každé s vlastními specifiky a rozšířeními pro konkrétní databázový systém. Znalost těchto rozdílů je klíčová pro efektivní práci s databázemi Oracle a Microsoft SQL Server.