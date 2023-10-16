# Kali linux

## Obsah

- [Kali linux](#kali-linux)
  - [Obsah](#obsah)
  - [Úvod](#úvod)
  - [Dostupné nástroje](#dostupné-nástroje)
    - [Zenmap](#zenmap)
    - [Wireshark](#wireshark)
    - [Sparta](#sparta)
    - [Metasploit](#metasploit)
    - [Aircrack-ng](#aircrack-ng)
    - [Burp Suite](#burp-suite)
    - [John the Ripper](#john-the-ripper)
  - [Distribuce a Instalace Kali Linux](#distribuce-a-instalace-kali-linux)
    - [Stahování Kali Linux](#stahování-kali-linux)
    - [Instalace na hardware](#instalace-na-hardware)
    - [Live image](#live-image)
    - [Virtuální stroj](#virtuální-stroj)

## Úvod
- Kali Linux je linuxový operační systém, který vznikl s cílem poskytnout komplexní řešení pro bezpečnostní testování, penetrační testování a kybernetickou bezpečnost. Tento operační systém, vyvinutý firmou Offensive Security, nabízí bezpečnostním profesionálům, etickým hackerům a všem zájemcům o bezpečnost jedinečnou sadu nástrojů a prostředí pro identifikaci zranitelností, analýzu sítí a ochranu proti kybernetickým hrozbám.

- Kali Linux, původně známý pod názvem BackTrack Linux, zaznamenal velký úspěch díky své rozmanité nabídce nástrojů a funkcionality. Kali Linux, postavený na Debianu a nabízející více než 600 nástrojů pro bezpečnostní testování a řízení vývoje, se stal základním nástrojem pro všechny, kteří se věnují kybernetické bezpečnosti.

- Kali Linux je nejen významným nástrojem v oblasti kybernetické bezpečnosti, ale také důležitým prostředkem pro zkoumání a ochranu digitálního světa.


## Dostupné nástroje

### Zenmap
- GUI pro nástroj Nmap
- Port Scanner na skenování otevřených, zavřených a posunutých portů
- Využívá trojcestné potvrzování(3-way handshake), který používá TCP protocol
  - Klient pošle SYN(synchronizace) packet spolu s ISN(initial sequence number)
  - Server vrací SYN + ACK(acknowledge) packetem, který také obsahuje ISN + 1
  - Klient obdrží odpověď a odpoví svým ACK paketem pro dokončení
- Můžeme narazit na tři druhy portů
    - filtrované: Tyto porty jsou chráněny firewallem a na běžné skenovací nástroje, jako je Nmap, často nereagují
    - zavřené: zde nic neběží, avšak firewall stále nebrání v provádění testů nebo prozkoumání
    - otevřené: porty jejichž administrace je otevřena všem. Všichni jsou schopni zjistit jaká administrace zde běží.

![Zenmap](https://geek-university.com/wp-content/uploads/2016/03/zenmap_example_scan.jpg)

### Wireshark
- Wireshark je mimořádně výkonný nástroj pro analýzu síťového provozu, který umožňuje uživatelům zachytávat, zobrazovat a analyzovat síťové pakety v reálném čase.
- Tento software poskytuje detailní pohled do komunikace mezi zařízeními v síti a umožňuje uživatelům sledovat, jak data putují přes síťové rozhraní.
- Wireshark podporuje mnoho různých síťových protokolů a dokáže identifikovat zranitelnosti, ladit síťové problémy a sledovat síťový provoz pro účely bezpečnostního auditu.
- Je často používán v oblasti bezpečnostního testování k odhalení zranitelností v síti a provádění bezpečnostní analýzy.
- Wireshark je nástroj s otevřeným zdrojovým kódem a je dostupný pro různé platformy, což ho činí oblíbenou volbou mezi profesionály v oblasti kybernetické bezpečnosti a síťových administrátorů.

### Sparta
- GUI aplikace založená na pythonu k automatizaci skenování, zhodnocení slabin a sběru informací.
- V dnešní době se více objevuje Legion, fork Sparty s quality of life změnami.
- Obsahuje nástroj Hydra pro cracking(louskání) hesel pomocí slovníkových útoků nebo brute-force.
- Dobře spolupracuje s Zenmapem, kde si dokáže importovat data pomocí XML.
- Ke skenování se používá Nikto

### Metasploit
- Metasploit je výkonný framework pro testování zranitelností a provádění penetračních testů.
- Umí simulovat různé útoky a je známý pro svou schopnost najít a využít zranitelnosti v systémech.
- Metasploit poskytuje širokou škálu nástrojů a modulů, které usnadňují provádění útoků a testování zabezpečení.
- Framework obsahuje připravené exploit moduly pro různé zranitelnosti, což umožňuje rychle provádět útoky.
- Je oblíbeným nástrojem pro profesionály v oblasti kyberbezpečnosti, etických hackerů a penetračních testerů.
- **Modularita**: Metasploit je známý svou modulární architekturou, která umožňuje uživatelům přidávat vlastní moduly a rozšiřovat jeho funkčnost.
- **Exploit Databáze**: Obsahuje rozsáhlou databázi exploit modulů a payloadů pro různé zranitelnosti a systémy.
- **Vývojářská Komunita**: Má aktivní komunitu vývojářů a uživatelů, kteří přispívají k rozvoji projektu a udržují jeho aktuálnost.
- **Využití v Bezpečnostním Testování**: Metasploit se často používá pro testování zabezpečení a identifikaci zranitelností v sítích a aplikacích.


### Aircrack-ng
- Soubor nástrojů k ověření zabezpečení bezdrátových sítí
- hlavní funkce:
    -   Monitoring: Zachycování paketů a export dat do textových souborů pro další zpracování dalšími nástroji.
    - Útoky: Útoky typu opakování, deautentizace, vytváření falešných přístupových bodů a další prostřednictvím injekce paketů.
    - Testování: Ověřování schopností WiFi karet a ovladačů (schopnost zachytávání a injekce).
    - Lámání: Lámání hesel pro WEP a WPA PSK (WPA 1 a 2).
- dostupné nástroje:
    - airmon-ng
        - tento nástroj umožňuje přepnout bezdrátový adaptér do monitorovacího módu, který je nezbytný pro další používání této sady nástrojů
    - airodump-ng
        - slouží k pasivnímu monitorování bezdrátových sítí
        - zobrazuje informace o dostupných sítích, včetně SSID, BSSID, kanálu a kvalitě signálu
    - aireplay-ng
        - díky tomuto nástroji lze útočit na bezdrátové sítě pomocí injekce, přeposílání paketů (pakety jsou zachyceny, uloženy a znovu poslány) a deutorizace (klientům sítě je poslán paket, který je donutí odpojit se od sítě, což útočníkovi následně umožní odposlechnout přihlašovací údaje k síti)
    - aircrack-ng
        - slouží k prolamování zachycených hashů
- Použití tohoto softwaru není triviální, proto je útokům na bezdrátové sítě s cílem získání hesla lepší použít Wifite, který celý útok automatizuje.

### Burp Suite
- Nástroj pro testování webových aplikací. Poskytuje širokou škálu funkcí pro analýzu a manipulaci komunikace.
- Obsahuje proxy server, ve kterém lze sledovat a modifikovat https komunikaci.
- Má funkci Intruder, která umožňuje útok na různé části webové aplikace jako formuláře a parametry URL.
- Má vlastní scanner na hledání zranitelností a chyb. Může identifikovat bezpečnostní trhliny jako SQL injection, cross-site scripting a zastaralé verze softwaru.
- Decoder a Encoder pro dekódování různých formátů dat.

![Burp Suite](https://upload.wikimedia.org/wikipedia/commons/thumb/c/ca/Thumbnail_BurpSuite.png/800px-Thumbnail_BurpSuite.png)

### SQLMap
- SQLMap je výkonným nástrojem pro testování zabezpečení webových aplikací a identifikaci SQL injection zranitelností.
- Tento nástroj automatizuje proces detekce a zneužití SQL injection útoků v databázových systémech.
- SQLMap umožňuje provádět různé typy SQL injection útoků, včetně union-based, time-based, blind, a dalších.
- Poskytuje uživatelské rozhraní, které usnadňuje konfiguraci a spouštění testů na cílových webových aplikacích.
- Je oblíbeným nástrojem mezi penetračními testery a bezpečnostními profesionály pro identifikaci a odstranění SQL injection zranitelností a ochranu webových aplikací před tímto typem útoků.

### Hashcat
- **Hashcat** je výkonný nástroj pro prolamování hesel a získávání hesel z různých formátů hashů.
- Tento software je známý svou schopností rychle a efektivně prolamovat hesla prostřednictvím různých metod, včetně brute-force útoků, slovníkových útoků a kombinací těchto technik.
- Klíčové rysy Hashcat zahrnují:
    - **Podpora Pro Různé Hashovací Algoritmy**: Hashcat podporuje širokou škálu hashovacích algoritmů, což umožňuje pracovat s různými typy hashovaných hesel.
    - **Rychlost**: Hashcat je známý svou výkonností a schopností rychle prolamovat hesla.
    - **Slovníkové Útoky**: Tento nástroj umožňuje provádět slovníkové útoky, kdy jsou testována hesla z velké slovníkové databáze.
    - **Kombinované Útoky**: Hashcat umožňuje kombinovat různé útoky a techniky pro co nejefektivnější prolamování hesel.
- Hashcat je často používán kyberbezpečnostními profesionály a penetračními testery pro testování zabezpečení a identifikaci slabých hesel v rámci bezpečnostních auditů.


## Distribuce a Instalace Kali Linux
- V této části se zaměříme na způsoby, jak získat a nainstalovat Kali Linux. Kali Linux je k dispozici ve formě distribuce, kterou lze zdarma stáhnout z oficiálních zdrojů a instalovat na různé platformy, včetně fyzických počítačů, virtuálních strojů a bootovatelných médií.
### Stahování Kali Linux
- Kali Linux můžete stáhnout z [oficiálních stránek projektu](https://www.kali.org/). Zde najdete různé verze Kali Linuxu, včetně 32bitových a 64bitových verzí a různých desktopových prostředí. Můžete si vybrat verzi, která nejlépe vyhovuje vašim potřebám.
### Instalace na hardware
- Po získání iso souboru je třeba vytvořit instalační médium například pomocí programu Rufus, který nám vytvoří bootovatelné médium. Po spuštění systému můžete spustit instalační skript, který Vás procesem provede.
### Live image
- Přestože se jedná o plně funkční systém, jeho použití pro každodenní potřeby není doporučeno. Proto lze také využít Live boot image, který spočívá k zavedení systému přímo z bootovatelného média. Výhodou je, že tímto způsobem nezasáhneme do počítače a zároveň máme přímý přístup k hardwaru.
### Virtuální stroj
- Pro vyzkoušení systému bez zásahu do počítače, či nutnosti vytvářet instalační médium je nejlepším způsobem spustit Kali Linux na stávajícím operačním systému jako virtuální stroj na platformách jako je VMWare, Virtualbox, či Hyperware. Virtuální stroje běží nad hostitelským operačním systémem, což znamená, že nemají přímý přístup k fyzickému hardware počítače. To může být problém, pokud chcete provádět určité úkoly, které vyžadují přímý přístup k hardware, například útoky na bezdrátové sítě. Navíc virtuální stroje sdílí prostředky s hostitelským operačním systémem, to znamená, že mohou mít omezený výkon.