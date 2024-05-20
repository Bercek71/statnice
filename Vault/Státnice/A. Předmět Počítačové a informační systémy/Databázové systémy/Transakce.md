![[Okruhy#^99db54]]

#### Definice

Transakce je základní jednotka zpracování, která provádí sekvenci operací na databázi jako jediný logický celek. Transakce začíná příkazem `BEGIN TRANSACTION` a končí příkazem `COMMIT` nebo `ROLLBACK`.

- **BEGIN TRANSACTION**: Zahájení transakce.
- **COMMIT**: Potvrzení a trvalé uložení všech změn provedených transakcí.
- **ROLLBACK**: Zrušení všech změn provedených transakcí a návrat databáze do stavu před začátkem transakce.

#### ACID

ACID je akronym pro čtyři základní vlastnosti transakcí, které zaručují spolehlivost zpracování dat v databázových systémech.

1. **Atomicity (Atomicita)**:
   - Zajišťuje, že všechny operace v rámci transakce jsou provedeny buď všechny, nebo žádná. Pokud dojde k chybě, všechny změny jsou vráceny zpět.
   - Příklad: Při převodu peněz mezi dvěma účty musí být částka odečtena z jednoho účtu a přičtena k druhému účtu jako jediný atomický celek.

2. **Consistency (Konzistence)**:
   - Zaručuje, že transakce převede databázi z jednoho konzistentního stavu do druhého konzistentního stavu. Všechny definované pravidla a omezení musí být dodrženy.
   - Příklad: Při vložení záznamu do databáze musí být dodrženy všechny integritní omezení, jako jsou primární a cizí klíče.

3. **Isolation (Izolace)**:
   - Zajišťuje, že současně prováděné transakce se vzájemně neovlivňují. Změny provedené jednou transakcí nejsou viditelné pro jiné transakce, dokud nejsou potvrzeny.
   - Příklad: Pokud dvě transakce současně aktualizují stejné záznamy, každá transakce by měla vidět pouze své vlastní změny, dokud nejsou obě potvrzeny.

4. **Durability (Trvalost)**:
   - Zaručuje, že jakmile je transakce potvrzena, její změny jsou trvalé a přetrvají i v případě výpadku systému.
   - Příklad: Po potvrzení transakce zůstávají všechny provedené změny v databázi uloženy i po restartu databázového systému.

#### Serializovatelnost transakcí

Serializovatelnost je vlastnost plánů transakcí, která zajišťuje, že výsledek provádění transakcí je ekvivalentní jejich nějakému sériovému provedení, i když jsou prováděny současně.

- **Sériový plán**: Transakce jsou provedeny jedna po druhé, bez překrývání.
  - Příklad: Transakce A a B jsou provedeny v pořadí A, pak B.
- **Serializovatelný plán**: Plán provádění transakcí, který je ekvivalentní nějakému sériovému plánu.
  - Příklad: Transakce A a B jsou provedeny v takovém pořadí, že jejich kombinovaný efekt je stejný jako u sériového provedení.

#### Zotavení

Zotavení databáze je proces, který zajišťuje návrat databáze do konzistentního stavu po selhání, ať už jde o selhání systému, chyby aplikací nebo jiné problémy.

- **UNDO**: Vrácení zpět změn provedených neúspěšnou transakcí.
- **REDO**: Opětovné provedení změn provedených úspěšnou transakcí, které nebyly trvale zapsány do databáze.

**Techniky zotavení:**

1. **Odložená aktualizace (Deferred Update)**:
   - Změny provedené transakcemi jsou nejprve zaznamenány do logu a do databáze se zapíší až po úspěšném potvrzení transakce.
   - Pouze operace REDO jsou nutné při zotavení, protože neúspěšné transakce neprováděly žádné změny v databázi.

2. **Okamžitá aktualizace (Immediate Update)**:
   - Změny jsou zaznamenány do logu a ihned aplikovány na databázi během provádění transakce.
   - Při zotavení jsou nutné operace UNDO pro neúspěšné transakce a operace REDO pro potvrzené transakce, které nebyly trvale zapsány.

#### Řízení souběhu

Řízení souběhu je proces, který zajišťuje správnou izolaci a správnost transakcí prováděných současně. Existuje několik technik řízení souběhu:

1. **Zamykání (Locking)**:
   - Zajišťuje exkluzivní přístup k datům pomocí zámků. Sdílené zámky (S) umožňují čtení, výlučné zámky (X) umožňují zápis.
   - **Dvoufázový zamykací protokol (Two-Phase Locking, 2PL)**: Transakce získává zámky během fáze růstu a uvolňuje je během fáze zkracování.
     - **Striktní 2PL (Strict 2PL)**: Zámky jsou uvolněny až po potvrzení nebo zrušení transakce.

2. **Optimistické řízení souběhu (Optimistic Concurrency Control)**:
   - Předpokládá, že konflikty mezi transakcemi jsou vzácné. Transakce pracují bez zámků a konflikty se kontrolují před potvrzením.
   - Pokud se zjistí konflikt, transakce je zrušena a musí být opakována.

3. **Časová razítka (Timestamp Ordering)**:
   - Každé transakci je přiřazeno jedinečné časové razítko. Operace transakcí jsou prováděny v pořadí podle jejich časových razítek.
   - Konflikty jsou řešeny na základě časových razítek, starší transakce mají přednost.

#### Úroveň izolace transakcí

Úroveň izolace transakcí určuje, jak jsou transakce izolovány jedna od druhé a jaké typy anomálií mohou nastat. SQL standard definuje čtyři úrovně izolace:

1. **Read Uncommitted (Nezávazně přečteno)**:
   - Transakce mohou číst data, která byla změněna jinými transakcemi, ale ještě nebyla potvrzena.
   - Může nastat: Špinavé čtení (dirty read), Neopakovatelné čtení (non-repeatable read), Fantomové čtení (phantom read).

2. **Read Committed (Závazně přečteno)**:
   - Transakce mohou číst pouze data, která byla potvrzena jinými transakcemi.
   - Může nastat: Neopakovatelné čtení, Fantomové čtení.
   - Nemůže nastat: Špinavé čtení.

3. **Repeatable Read (Opakovatelné čtení)**:
   - Zajišťuje, že pokud transakce čte stejná data vícekrát, vždy dostane stejné hodnoty. Žádné jiné transakce nemohou měnit čtená data, dokud není tato transakce potvrzena.
   - Může nastat: Fantomové čtení.
   - Nemůže nastat: Špinavé čtení, Neopakovatelné čtení.

4. **Serializable (Serializovatelné)**:
   - Nejvyšší úroveň izolace, která zajišťuje úplnou izolaci transakcí. Transakce jsou prováděny tak, jako by byly prováděny sériově.
   - Nemůže nastat: Špinavé čtení, Neopakovatelné čtení, Fantomové čtení.

#### Shrnutí

Transakce jsou základními stavebními kameny databázových systémů, které zajišťují integritu a spolehlivost zpracování dat. Dodržování vlastností ACID, správná úroveň izolace, efektivní řízení souběhu a robustní mechanismy zotavení jsou klíčové pro dosažení spolehlivého a konzistentního chování databázových systémů.