![[Okruhy#^91ccf4]]

Bezpečnost počítačových sítí je klíčová pro ochranu dat a zajištění spolehlivosti a dostupnosti služeb. Zahrnuje ochranu před různými typy útoků a implementaci bezpečnostních opatření, jako jsou firewally a virtuální privátní sítě.

#### Útoky na infrastrukturu, servery a aplikační protokoly, a jejich detekce

**Útoky na infrastrukturu**:
1. **DDoS (Distributed Denial of Service)**:
   - Útoky, které zahlcují síť nebo server velkým množstvím falešných požadavků, čímž způsobují nedostupnost služby.
   - Detekce: Monitorování síťového provozu, identifikace anomálií, nasazení ochranných zařízení jako DDoS ochrany.

2. **ARP Spoofing**:
   - Útok, při kterém útočník posílá falešné ARP zprávy, aby přesměroval provoz mezi dvěma zařízeními přes svou vlastní stanici.
   - Detekce: Monitorování ARP zpráv, použití statických ARP tabulek, nasazení nástrojů pro detekci ARP spoofingu.

**Útoky na servery**:
1. **Brute Force Attack**:
   - Útok, který zkouší všechny možné kombinace hesel, dokud nenajde správné heslo.
   - Detekce: Monitorování neúspěšných přihlašovacích pokusů, nasazení ochrany jako je rate limiting, implementace dvoufaktorové autentizace.

2. **Exploity zranitelností**:
   - Útoky využívající zranitelnosti v softwaru nebo operačním systému k získání neoprávněného přístupu nebo k spuštění škodlivého kódu.
   - Detekce: Pravidelné skenování zranitelností, nasazení intrusion detection/prevention systémů (IDS/IPS), aplikace bezpečnostních záplat.

**Útoky na aplikační protokoly**:
1. **SQL Injection**:
   - Útoky, které vkládají škodlivé SQL dotazy do vstupních polí aplikace, aby získaly přístup k databázi nebo ji modifikovaly.
   - Detekce: Validace a sanitizace vstupních dat, nasazení WAF (Web Application Firewall).

2. **Cross-Site Scripting (XSS)**:
   - Útoky, které vkládají škodlivý skript do webové stránky, který je následně vykonán v prohlížeči jiného uživatele.
   - Detekce: Validace a escapování vstupních dat, nasazení Content Security Policy (CSP).

#### Paketové filtry a stavový firewall

**Paketové filtry**:
- Pracují na síťové vrstvě a transportní vrstvě modelu OSI.
- Kontrolují každý paket zvlášť na základě předem definovaných pravidel.
- Filtrují provoz podle IP adres, portů a protokolů.
- Nevýhoda: Nemohou sledovat stav spojení, což omezuje jejich efektivitu proti pokročilým útokům.

**Stavový firewall**:
- Sleduje stav spojení a rozhoduje o povolení nebo zamítnutí paketů na základě stavu a kontextu spojení.
- Udržuje tabulku stavu (state table), kde sleduje aktivní spojení.
- Efektivnější při ochraně proti útokům, které využívají vícestavové spojení.
- Výhoda: Lepší schopnost detekovat a blokovat pokročilé útoky.

#### Virtuální privátní sítě (VPN)

**Virtuální privátní síť (VPN)**:
- Umožňuje bezpečné připojení k síti přes veřejnou síť (např. internet).
- Šifruje veškerý provoz mezi klientem a VPN serverem, čímž zajišťuje důvěrnost a integritu dat.
- Používá různé protokoly, jako jsou PPTP, L2TP/IPsec, OpenVPN, a SSL/TLS.

**Typy VPN**:
1. **Remote Access VPN**:
   - Umožňuje jednotlivým uživatelům připojit se k firemní síti z libovolného místa přes internet.
   - Ideální pro zaměstnance pracující na dálku.

2. **Site-to-Site VPN**:
   - Propojuje dvě nebo více sítí přes internet.
   - Používá se k propojení poboček firmy nebo ke spojení firemních sítí s partnery.

**Zabezpečení VPN**:
- **Šifrování**: Využívá silné šifrovací algoritmy pro zajištění důvěrnosti dat (např. AES).
- **Autentizace**: Používá různé metody autentizace uživatelů, jako jsou hesla, certifikáty nebo dvoufaktorová autentizace.
- **Integrita dat**: Zajišťuje, že data nejsou během přenosu modifikována pomocí hashovacích funkcí a kontrolních součtů.

### Shrnutí

Bezpečnost počítačových sítí zahrnuje ochranu před různými typy útoků na infrastrukturu, servery a aplikační protokoly. Detekce těchto útoků je klíčová pro minimalizaci škod. Použití paketových filtrů a stavových firewallů poskytuje různé úrovně ochrany na základě kontroly paketů a sledování stavu spojení. Virtuální privátní sítě (VPN) umožňují bezpečné připojení k síti přes veřejné sítě, zajišťují šifrování a autentizaci dat, čímž chrání důvěrnost a integritu přenášených informací.