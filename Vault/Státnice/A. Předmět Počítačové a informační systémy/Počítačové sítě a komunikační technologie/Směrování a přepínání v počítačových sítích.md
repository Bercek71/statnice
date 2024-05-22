![[Okruhy#^c621e9]]
#### Topologie LAN sítí

**Topologie** označuje způsob, jakým jsou zařízení v síti propojena. Existuje několik základních typů topologií LAN sítí:

1. **Hvězda (Star)**:
   - Všechny uzly jsou připojeny k centrálnímu zařízení (např. switch, hub).
   - Výhody: Snadná správa a diagnostika chyb, jednoduché přidávání nových zařízení.
   - Nevýhody: Selhání centrálního zařízení vede k výpadku celé sítě.

2. **Sběrnice (Bus)**:
   - Všechna zařízení jsou připojena ke společnému kabelu (sběrnici).
   - Výhody: Jednoduchá instalace, nízké náklady.
   - Nevýhody: Omezená délka kabelu, obtížná diagnostika chyb, nízká odolnost proti chybám.

3. **Kruh (Ring)**:
   - Každé zařízení je připojeno ke dvěma dalším, tvoří uzavřený kruh.
   - Výhody: Rovnoměrná distribuce dat, absence kolizí.
   - Nevýhody: Selhání jednoho zařízení může narušit celou síť, složitá instalace.

4. **Strom (Tree)**:
   - Kombinace hvězdicové a sběrnicové topologie. Centrální zařízení jsou propojena do hierarchie.
   - Výhody: Škálovatelnost, jednoduchá správa větších sítí.
   - Nevýhody: Složitější správa a instalace, závislost na centrálních uzlech.

5. **Síť (Mesh)**:
   - Každé zařízení je připojeno ke všem ostatním zařízením.
   - Výhody: Vysoká odolnost proti chybám, redundantní cesty.
   - Nevýhody: Vysoké náklady na instalaci a údržbu, složitá konfigurace.

#### Aktivní prvky a jejich funkce

**Aktivní prvky** jsou zařízení v síti, která zpracovávají a přeposílají data. Mezi nejdůležitější patří přepínače (switch) a směrovače (router).

1. **Přepínač (Switch)**:
   - Funkce: Přepínač spojuje zařízení v LAN síti a přeposílá data mezi nimi na základě MAC adres.
   - Operuje na 2. vrstvě modelu OSI (spojová vrstva).
   - Uchovává tabulku MAC adres a portů, takže může směrovat data pouze k určenému zařízení.
   - Umožňuje full-duplex komunikaci, což zvyšuje přenosovou kapacitu sítě.
   - Minimalizuje kolize dat v síti.

2. **Směrovač (Router)**:
   - Funkce: Směrovač propojuje různé sítě a směruje data mezi nimi na základě IP adres.
   - Operuje na 3. vrstvě modelu OSI (síťová vrstva).
   - Uchovává směrovací tabulky a používá směrovací protokoly k určení nejlepší cesty pro data.
   - Směrovače umožňují komunikaci mezi různými sítěmi, např. mezi LAN a WAN.

#### Směrovací protokoly – základní popis

**Směrovací protokoly** určují, jakým způsobem se data přesunují mezi různými sítěmi. Existují dva hlavní typy směrovacích protokolů: vektorové směrovací protokoly a protokoly na základě stavu spojů.

1. **Vektorové směrovací protokoly (Distance Vector Routing Protocols)**:
   - Každý směrovač udržuje tabulku, která obsahuje vzdálenosti k cílovým sítím a cestu k těmto sítím.
   - Směrovače pravidelně sdílejí své směrovací tabulky s přímými sousedy.
   - Příklady: RIP (Routing Information Protocol), IGRP (Interior Gateway Routing Protocol).

2. **Protokoly na základě stavu spojů (Link State Routing Protocols)**:
   - Každý směrovač má kompletní mapu topologie sítě a vypočítává nejlepší cesty pomocí algoritmů.
   - Směrovače šíří informace o stavu svých připojení do všech ostatních směrovačů v síti.
   - Příklady: OSPF (Open Shortest Path First), IS-IS (Intermediate System to Intermediate System).

#### Třídy směrovacích protokolů

1. **Vnitřní směrovací protokoly (Interior Gateway Protocols, IGP)**:
   - Používají se uvnitř jedné autonomní sítě.
   - Příklady: RIP, OSPF, EIGRP (Enhanced Interior Gateway Routing Protocol).

2. **Vnější směrovací protokoly (Exterior Gateway Protocols, EGP)**:
   - Používají se mezi autonomními sítěmi.
   - Příklady: BGP (Border Gateway Protocol).

#### Hierarchické směrování

**Hierarchické směrování** rozděluje síť na menší segmenty a zjednodušuje správu a směrování dat.

1. **Rozdělení na oblasti**:
   - Síť je rozdělena na oblasti, kde každý směrovač udržuje informace pouze o své oblasti.
   - Páteřní síť propojuje jednotlivé oblasti a přenáší data mezi nimi.

2. **Výhody**:
   - Snížení velikosti směrovacích tabulek.
   - Zvýšení efektivity a rychlosti směrování.
   - Snížení množství směrovacích aktualizací přenášených po síti.

3. **Nevýhody**:
   - Složitější konfigurace a správa.
   - Možnost vzniku problémů při špatném návrhu hierarchie.

Hierarchické směrování se často používá v rozsáhlých sítích, kde umožňuje efektivnější správu a lepší škálovatelnost.

### Shrnutí

Směrování a přepínání jsou základními funkcemi pro správu datových toků v počítačových sítích. Znalost topologií LAN sítí, funkcí aktivních prvků, jako jsou přepínače a směrovače, a pochopení směrovacích protokolů a hierarchického směrování jsou klíčové pro návrh a údržbu efektivních a spolehlivých sítí.