![[Okruhy#^747c1d]]

#### Obecné principy

Při tvorbě bezpečných aplikací je důležité dodržovat několik základních principů:

1. **Princip nejmenších oprávnění**:
   - Uživatelé a procesy by měly mít jen minimální nezbytná oprávnění, která potřebují ke svému fungování.

2. **Obrana v hloubce (Defense in Depth)**:
   - Implementace více vrstev bezpečnostních opatření, které zajišťují ochranu i v případě prolomení jedné vrstvy.

3. **Bezpečné programovací techniky**:
   - Používání bezpečných knihoven a frameworků.
   - Pravidelné aktualizace softwaru a záplatování zranitelností.
   - Důkladné testování aplikací, včetně bezpečnostních testů.

4. **Šifrování**:
   - Šifrování citlivých dat během přenosu i uložení.
   - Používání silných šifrovacích algoritmů a správné správy klíčů.

5. **Autentizace a autorizace**:
   - Silná autentizace uživatelů (např. dvoufaktorová autentizace).
   - Správná autorizace přístupu k různým funkcím a datům.

#### Nejčastější zranitelnosti

Zranitelnosti aplikací lze kategorizovat podle různých kritérií. Jedním z nejznámějších zdrojů pro tuto kategorizaci je OWASP (Open Web Application Security Project), který pravidelně vydává seznam nejčastějších zranitelností webových aplikací (OWASP Top Ten).

1. **Injection (Injekční útoky)**:
   - Například SQL injection, kdy útočník vkládá škodlivé SQL dotazy prostřednictvím vstupních polí.
   - Prevence: Používání parametrizovaných dotazů a připravených výrazů.

2. **Broken Authentication (Slabá autentizace)**:
   - Zranitelnosti v autentizačních mechanismech, které umožňují neoprávněný přístup.
   - Prevence: Implementace silné autentizace, správná správa relací.

3. **Sensitive Data Exposure (Odhalení citlivých dat)**:
   - Nešifrované přenosy dat nebo nedostatečná ochrana uložených dat.
   - Prevence: Používání šifrování, správná správa klíčů.

4. **XML External Entities (XXE)**:
   - Zranitelnost v XML parseru, která umožňuje útočníkům číst soubory na serveru nebo iniciovat síťové požadavky.
   - Prevence: Konfigurace XML parserů k zakázání externích entit.

5. **Broken Access Control (Nesprávná kontrola přístupu)**:
   - Neoprávněný přístup k funkcím nebo datům.
   - Prevence: Implementace robustních kontrol přístupu.

6. **Security Misconfiguration (Chybná konfigurace zabezpečení)**:
   - Nesprávná konfigurace bezpečnostních nastavení.
   - Prevence: Pravidelná kontrola a aktualizace konfigurací.

7. **Cross-Site Scripting (XSS)**:
   - Útoky, které umožňují vkládání škodlivého skriptu do webové stránky.
   - Prevence: Validace a escapování vstupních dat.

8. **Insecure Deserialization (Nezabezpečená deserializace)**:
   - Zranitelnosti při deserializaci dat, které umožňují spuštění škodlivého kódu.
   - Prevence: Používání bezpečných metod deserializace.

9. **Using Components with Known Vulnerabilities (Používání komponent se známými zranitelnostmi)**:
   - Použití zastaralých nebo zranitelných knihoven a frameworků.
   - Prevence: Pravidelně aktualizovat všechny závislosti.

10. **Insufficient Logging & Monitoring (Nedostatečné logování a monitorování)**:
    - Nedostatečné sledování a logování, které ztěžuje detekci a reakci na útoky.
    - Prevence: Implementace důkladného logování a monitorování bezpečnostních událostí.

#### Bezpečnost databází a webových aplikací

**Bezpečnost databází**:

1. **Řízení přístupu**:
   - Implementace správných oprávnění pro uživatele a role.
   - Používání principu nejmenších oprávnění.

2. **Šifrování dat**:
   - Šifrování citlivých dat jak v klidu (uložených) tak během přenosu.
   - Použití SSL/TLS pro zabezpečení přenosu dat mezi aplikací a databází.

3. **Ochrana před SQL injection**:
   - Používání parametrizovaných dotazů a připravených výrazů.
   - Validace a escapování vstupních dat.

4. **Pravidelné zálohování**:
   - Pravidelné zálohování databází a testování obnovitelnosti záloh.

**Bezpečnost webových aplikací**:

1. **Vstupní validace**:
   - Validace všech vstupních dat na straně klienta i serveru.
   - Použití whitelistů pro povolené hodnoty.

2. **Ochrana před XSS**:
   - Escapování výstupních dat.
   - Použití bezpečnostních hlaviček jako Content Security Policy (CSP).

3. **Ochrana před CSRF (Cross-Site Request Forgery)**:
   - Použití tokenů (CSRF tokeny) v formulářích a HTTP požadavcích.

4. **Bezpečné ukládání hesel**:
   - Používání silných hashovacích funkcí jako bcrypt, scrypt nebo Argon2.
   - Přidání soli (salt) k heslům před hashováním.

**Typické útoky na webové aplikace**:

1. **SQL Injection**:
   - Útočníci vkládají škodlivé SQL dotazy do vstupních polí, což může vést k neoprávněnému přístupu nebo modifikaci dat.
   - Prevence: Parametrizované dotazy, validace vstupů.

2. **Cross-Site Scripting (XSS)**:
   - Útočníci vkládají škodlivé skripty, které jsou vykonány v prohlížečích uživatelů.
   - Prevence: Escapování vstupů, Content Security Policy (CSP).

3. **Cross-Site Request Forgery (CSRF)**:
   - Útočníci zneužijí autentizovaného uživatele k provedení neautorizovaných akcí.
   - Prevence: CSRF tokeny, validace refererů.

4. **Directory Traversal**:
   - Útočníci zneužijí chyby ve vstupních datech k přístupu k souborům mimo povolené adresáře.
   - Prevence: Validace a normalizace cest, omezení přístupu na souborový systém.

5. **Man-in-the-Middle (MITM)**:
   - Útočníci odposlouchávají nebo modifikují komunikaci mezi uživatelem a serverem.
   - Prevence: Použití SSL/TLS pro šifrování přenosu dat.

### Shrnutí

Tvorba bezpečných aplikací vyžaduje pečlivé dodržování osvědčených bezpečnostních praktik a neustálou pozornost k potenciálním zranitelnostem. Zajištění bezpečnosti databází a webových aplikací zahrnuje validaci vstupů, správu oprávnění, šifrování dat a pravidelné aktualizace softwaru. Dodržováním těchto zásad lze minimalizovat rizika a chránit aplikace a data před různými typy útoků.