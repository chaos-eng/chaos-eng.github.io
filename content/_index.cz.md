+++
title = "PRINCIPY CHAOSINŽENÝRSTVÍ"
date = 2020-01-28T16:25:57+02:00
draft = false
+++

# PRINCIPY CHAOSINŽENÝRSTVÍ
Last Update: 2019 January

*Chaosinženýrství je obor zabývající se experimentováním na systému, které má za cíl vybudovat důvěru ve schopnost systému odolávat turbulentním podmínkám v produkčním prostředí.*

Rozvoj v oblasti vývoje velkých, distribuovaných softwarových systémů mění pravidla, jakými se softwarové inženýrství řídilo. V odvětví rychle zavádíme postupy, které zvyšují flexibilitu vývoje a rychlost dodávek. Ruku v ruce s těmito výhodami ale přichází i otázka: Jak moc můžeme důvěřovat komplexním systémům, které jsme nasadili do produkčního prostředí?

Dokonce i když všechny služby v distribuovaném systému fungují správně, interakce mezi nimi mohou vést k nepředvídatelným výsledkům. Tyto výsledky, způsobené výjimečnými, přesto reálnými, zničujícími událostmi postihujícími produkční prostředí, dělají z distribuovaných systémů systémy z podstaty nestálé, chaotické.

Slabiny potřebujeme objevit dříve, než se projeví nestandardním chováním celého systému.  Zmíněnou slabinou může být např.: špatné nastavení zotavení z chybového stavu v případě nedostupnosti služby; smršť opětovných volání způsobená nevyladěnými timeouty; výpadky v případě přetížení provolávané služby; kaskádovitá selhání v případě pádu kritického místa systému; atd.  Těmito nejvýznamnějšími slabinami se musíme aktivně zabývat předtím, než budou mít dopad na naše zákazníky v produkčním prostředí. Musíme navrhnout, jak zvládat chaos vlastní distribuovanému systému, využít narůstající rychlost a flexibilitu a získat důvěru v systém běžící v produkčním prostředí bez ohledu na jeho složitost.

Důvěru ve schopnost daných distribuovaných systémů obstát v reálném provozu můžeme vybudovat použitím systematických postupů založených na zkušenostech, přičemž se zaměřujeme na zvládání chaosu v distribuovaných systémech. Chování distribuovaného systému poznáváme jeho pozorováním při provádění kontrolovaného experimentu. Tento postup nazýváme chaosinženýrstvím.


## CHAOS V PRAXI

Abychom zvládli nejistotu v distribuovaném systému, experimentujeme, čímž pomocí chaosinženýrství odhalujeme slabiny systému. Proces experimentování se skládá ze čtyř kroků:

1. Nejprve stanovte "ustálené chování" systému pomocí měřitelného výstupu, který ukáže, jak se systém normálně chová.
2. Navrhněte hypotézu, že systém se bude chovat ustáleně jak pro kontrolní, tak pro experimentální skupinu.
3. Uveďte proměnné vyjadřující události z reálného světa, např. pády serverů, selhání disků, přerušená síťová spojení atd.
4. Snažte se vyvrátit hypotézu. Hledejte rozdíly mezi ustáleným chováním kontrolní a experimentální skupiny.

Čím těžší je vychýlit systém z ustáleného stavu, tím větší důvěru v jeho chování máme. Jestliže však v systému objevíme slabinu, získáme možnost ho vylepšit ještě před tím, než se nežádoucí chování projeví ve velkém.

## POKROČILÉ PRINCIPY

Následující principy popisují ideální použití chaos engineeringu, aplikované na výše popsané procesy experimentování. Míra uplatňování těchto principů je silně svázána s důvěrou, kterou máme v distribuovaný systém.

### Vytvořte hypotézu o ustáleném chování

Spíše než na interní atributy systému se zaměřte na jeho měřitelné výstupy. Výsledky krátkého měření výstupů reprezentují ustálené chování. Mezi metriky představující ustálené chování mohou patřit např. celková propustnost systému, chybovost, percentily latence atd. Díky soustavnému sledování metrik o chování systému během chaos experimentů ověříme spíše to, žesystém pracuje , nežjak to dělá .

### Kombinujte skutečné (realistické) události

O událostech v reálném světě uvažujeme v kontextu chaosu jako o proměnných. Dejte důraz na události, které mohou mít významný dopad nebo ke kterým pravděpodobně dojde nejčastěji. Uvažujte o událostech jako jsou poruchy hardwaru, např. nedostupné servery, softwarové chyby, např. špatně strukturované odpovědi, ev. další události jako skokové nárůsty v objemu komunikace, nebo události spojené se škálováním. Jakákoliv událost, která může narušit ustálené chování je potenciálně proměnná v chaos experimentu.

### Provádějte experimenty v produkci

V závislosti na prostředí a zatížení se systémy se chovají odlišně. Otisk reálného provozu je jediný způsob, jak věrohodně podchytit průchod dotazu, protože rozložení zdrojů se může kdykoliv změnit. Velmi doporučujeme experimentovat v produkčním provozu, protože pouze tak získáme autentické a relevantní výsledky vzhledem k tomu, jak je systém provozován a v jakém nastavení je nasazen.

### Automatizujte experimenty, aby mohly být prováděny nepřetržitě

Manuální provádění experimentů je pracné a v podstatě neudržitelné. Automatizujte experimenty, provádějte je nepřetržitě. Díky chaosinženýrství začleníme do provozovaného systému automatické mechanismy pro orchestraci a analýzu problémů.

### Minimalizujte dopad

Experimentování v produkci může zákazníkům způsobit zbytečné problémy. Ačkoli musí existovat ochota nést krátkodobé negativní dopady, je zodpovědností a povinností chaos inženýra zajistit, aby dopad experimentů byl minimalizován a ohraničen.

Chaosinženýrství je užitečný postup, který mění způsob, jakým je software v některých z největších společností na světě navržen a vystavěn. Zatímco se jiné přístupy věnují rychlosti a flexibilitě, chaos se v distribuovaných systémech zabývá systémovou nejistotou. Principy chaosinženýrství poskytují důvěru, která umožňuje rychle a ve velkém rozsahu inovovat, a přináší zákazníkům vysokou kvalitu.

Připojte se k diskusi o principech chaosu a jejich použití, kterou vedeme ve skupině Google [Chaos Community](https://groups.google.com/forum/#!forum/chaos-community).
