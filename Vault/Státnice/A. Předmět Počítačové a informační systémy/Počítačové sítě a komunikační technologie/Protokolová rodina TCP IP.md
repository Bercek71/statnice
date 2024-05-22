![[Okruhy#^53b405]]
#### TCP/IP model a jeho vztah k referenčnímu modelu ISO-OSI

**TCP/IP model**:
TCP/IP model je koncepční rámec, který popisuje protokoly a technologie používané pro přenos dat po internetu. Tento model má čtyři vrstvy:
1. **Síťové rozhraní (Network Interface)**:
   - Kombinuje fyzickou a spojovou vrstvu OSI modelu.
   - Zahrnuje technologie jako Ethernet, Wi-Fi, atd.

2. **Internetová vrstva (Internet)**:
   - Odpovídá síťové vrstvě OSI modelu.
   - Zahrnuje protokoly jako IP (IPv4, IPv6), ICMP, ARP.

3. **Transportní vrstva (Transport)**:
   - Odpovídá transportní vrstvě OSI modelu.
   - Zahrnuje protokoly jako TCP a UDP.

4. **Aplikační vrstva (Application)**:
   - Kombinuje aplikační, prezentační a relační vrstvu OSI modelu.
   - Zahrnuje protokoly jako HTTP, FTP, SMTP, DNS.

**Referenční model ISO-OSI**:
ISO-OSI (Open Systems Interconnection) model je teoretický model, který má sedm vrstev:
1. Fyzická vrstva
2. Spojová vrstva
3. Síťová vrstva
4. Transportní vrstva
5. Relační vrstva
6. Prezentační vrstva
7. Aplikační vrstva

**Vztah mezi TCP/IP a OSI modely**:
- TCP/IP model je praktičtější a používá se pro reálnou implementaci sítí.
- OSI model je více teoretický a poskytuje detailnější rozdělení funkcí.
- TCP/IP model kombinuje některé vrstvy OSI modelu, což odráží praktičtější přístup k návrhu sítí.

| Vrstva OSI       | Vrstva TCP/IP         |
|------------------|-----------------------|
| 7. Aplikační     | 4. Aplikační          |
| 6. Prezentační   | 4. Aplikační          |
| 5. Relační       | 4. Aplikační          |
| 4. Transportní   | 3. Transportní        |
| 3. Síťová        | 2. Internetová        |
| 2. Spojová       | 1. Síťové rozhraní    |
| 1. Fyzická       | 1. Síťové rozhraní    |

#### Síťové protokoly – IPv4 vs. IPv6

**IPv4**:
- Používá 32bitové adresy, což umožňuje přibližně 4,3 miliardy unikátních adres.
- Adresy jsou zapisovány jako čtyři desetinné číslice oddělené tečkami (např. 192.168.0.1).
- Má omezenou adresní kapacitu a je náchylný k problémům s vyčerpáním adres.

**IPv6**:
- Používá 128bitové adresy, což umožňuje prakticky neomezený počet unikátních adres (přibližně 3.4 x 10^38 adres).
- Adresy jsou zapisovány jako osm skupin čtyř hexadecimálních číslic oddělených dvojtečkami (např. 2001:0db8:85a3:0000:0000:8a2e:0370:7334).
- Nabízí mnoho vylepšení, jako je auto-konfigurace adres, integrovaná podpora pro zabezpečení a efektivnější směrování.

**Srovnání IPv4 a IPv6**:

| Funkce            | IPv4                                      | IPv6                                       |
| ----------------- | ----------------------------------------- | ------------------------------------------ |
| Velikost adresy   | 32 bitů                                   | 128 bitů                                   |
| Formát adresy     | Desetinné číslice oddělené tečkami        | Hexadecimální číslice oddělené dvojtečkami |
| Fragmentace       | Provádí se na odesílacím uzlu a routerech | Provádí se pouze na odesílacím uzlu        |
| Zabezpečení       | IPSec je volitelný                        | IPSec je povinný                           |
| Konfigurace adres | Manuální nebo DHCP                        | Auto-konfigurace, DHCPv6                   |
| Broadcast         | Ano                                       | Ne, nahrazeno multicastem a anycastem      |
| Počet adres       | ~4.3 miliardy                             | ~3.4 x 10^38                               |

#### Protokoly transportní vrstvy

Transportní vrstva je zodpovědná za poskytování spolehlivé nebo nespolehlivé komunikace mezi hostiteli. Dva hlavní protokoly této vrstvy jsou TCP a UDP.

**TCP (Transmission Control Protocol)**:
- Spolehlivý protokol, který zajišťuje bezeztrátový přenos dat.
- Vytváří spojení mezi odesílatelem a příjemcem před přenosem dat.
- Používá potvrzování (acknowledgements) a kontrolu toku (flow control).
- Sekvenční čísla a potvrzovací čísla zajišťují správné pořadí přijetí dat.
- Používá se pro aplikace, kde je důležitá spolehlivost, jako je webový prohlížeč (HTTP/HTTPS), e-mail (SMTP), a souborové přenosy (FTP).

**UDP (User Datagram Protocol)**:
- Nespolehlivý protokol, který neposkytuje záruku doručení nebo správného pořadí dat.
- Nevyžaduje navázání spojení před přenosem dat.
- Menší režie a rychlejší přenos než TCP.
- Používá se pro aplikace, kde je důležitá rychlost a nízká latence, jako je streamování videa, VoIP, a DNS.

#### Princip fungování spolehlivého přenosového kanálu protokolu TCP

TCP poskytuje spolehlivý přenos dat pomocí následujících mechanismů:

1. **Navázání spojení (Three-Way Handshake)**:
   - Protokol TCP používá tříkrokový proces k navázání spojení mezi odesílatelem a příjemcem.
   - SYN: Klient odešle SYN segment se sekvenčním číslem.
   - SYN-ACK: Server odpoví SYN-ACK segmentem, který potvrzuje přijetí SYN a obsahuje své vlastní sekvenční číslo.
   - ACK: Klient odpoví ACK segmentem, který potvrzuje přijetí SYN-ACK.

   ```mermaid
   sequenceDiagram
       participant Client
       participant Server
       Client->>Server: SYN (Seq=x)
       Server->>Client: SYN-ACK (Seq=y, Ack=x+1)
       Client->>Server: ACK (Seq=x+1, Ack=y+1)
   ```

2. **Přenos dat**:
   - Data jsou rozdělena na segmenty, které jsou očíslovány sekvenčními čísly.
   - Příjemce potvrzuje přijetí každého segmentu odesláním ACK se sekvenčním číslem dalšího očekávaného segmentu.
   - Odesílatel udržuje okno (window) potvrzených segmentů a opětovně vysílá ztracené segmenty.

3. **Řízení toku (Flow Control)**:
   - TCP používá mechanismus řízení toku nazvaný okno příjemce (receiver window), který omezuje počet neackovaných segmentů, které mohou být odeslány.
   - Příjemce určuje velikost svého přijímacího okna, aby zabránil přetížení a ztrátě dat.

4. **Řízení přetížení (Congestion Control)**:
   - TCP používá algoritmy, jako je Slow Start, Congestion Avoidance, Fast Retransmit a Fast Recovery, aby předešlo přetížení sítě.
   - Algoritmus Slow Start začíná malým oknem a postupně ho zvětšuje, aby se zjistila kapacita sítě.

5. **Uzavření spojení**:
   - Uzavření spojení je proces, který může být iniciován oběma stranami.
   - FIN: Odesílatel vyšle FIN segment, aby oznámil ukončení vysílání.
   - ACK: Příjemce potvrdí přijetí FIN segmentu.
   - Druhá strana poté vyšle svůj vlastní FIN segment, který je také potvrzen ACK segmentem.

   ```mermaid
   sequenceDiagram
       participant Client
       participant Server
       Client->>Server: FIN (Seq=u)
       Server->>Client: ACK (Ack=u+1)
       Server->>Client: FIN (Seq=v)
       Client->>Server: ACK (Ack=v+1)


   ```

### Shrnutí

Protokolová rodina TCP/IP poskytuje robustní a flexibilní rámec pro komunikaci v sítích, který zahrnuje model TCP/IP a jeho vztah k referenčnímu modelu OSI, srovnání IPv4 a IPv6, popis transportních protokolů (TCP a UDP) a detaily fungování spolehlivého přenosového kanálu TCP. Tento základ je klíčový pro pochopení moderních síťových technologií a jejich implementace.