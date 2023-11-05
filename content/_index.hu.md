+++
title = "A CHAOS ENGINEERING ALAPELVEI"
date = 2020-01-28T16:25:57+02:00
draft = false
+++

# A CHAOS ENGINEERING ALAPELVEI
Utolsó szerkesztés: 2018 Május

*A Chaos Engineering annak a tudománya, amikor kísérleteket végzünk a produkciós környezetben annak érdekében, hogy megbizonyosodjunk a rendszer hibatűrő képességéről különböző hibajelenségek esetén.*

A skálázható, elosztott szoftverrendszerek által elérhető előnyök megváltoztatták az egész szoftverfejlesztést. A teljes iparág felgyorsult, gyorsan képes adoptálni azokat a gyakorlatokat amelyek a fejlesztés rugalmasságát segítik, vagy az éles üzembe állítást meggyorsítják. Azonban ezek az előnyök további kérdéseket vetnek fel: Mennyire bízhatunk ezekben a komplex rendszerekben, amikor éles üzembe állítjuk?

Ha egy elosztott rendszer összes független szolgáltatása funkcionálisan jól működik, akkor is előfordulhatnak kiszámíthatatlan kimenetelek a szolgáltatások közötti interakciók során. A kiszámíthatatlan események, kombinálva a ritka, de előforduló valós produkciós üzemzavarokkal azt eredményezik, hogy ezek az elosztott rendszerek természetükből adódóan kaotikusak.

Nekünk kell azonosítanunk a rendszer gyengeségeit, mielőtt azok a teljes rendszert érintő rendellenességet okoznának. A rendszer gyengeségei különböző formában jelentkezhetnek: nem megfelelő fallback beállítások amikor egy szolgáltatás nem elérhető, nagy mennyiségű újrapróbálkozás nem megfelelő időtúllépés beállítások miatt, kimaradások, amikor a folyamatban egy kulcs komponens túlterhelődik, amikor a hibák tovább terjednek egy nem hibatűrő komponens meghibásodása miatt, stb. Proaktívan foglalkoznunk kell a legjellemzőbb gyengeségekkel, mielőtt azok az ügyfeleinket elérik a produkciós környezetben. Kezelnünk kell a rendszerekre jellemző káoszt, de egyúttal ki kell használnunk a rugalmasság, és a gyorsaság nyújtotta előnyöket, és biztosnak kell lennünk a produkciós környezetünk működésében, annak ellenére hogy mennyire komplexek tudnak lenni.

Tapasztalati, rendszeralapú kísérletezés által ismerjük meg az okozott zűrt a skálázódó, elosztott rendszerekben, és ezáltal növeljük a magabiztosságunkat abban, hogy ezek a rendszerek valóban ellenállnak az előforduló hibáknak. Megismerjük az elosztott rendszer viselkedését, azáltal hogy egy kontrollált kísérletben figyeljük meg. Ezt hívjuk Chaos Engineering-nek.

## CHAOS A GYAKORLATBAN

Hogy kezeljük a bizonytalanságot egy elosztott skálázott rendszer esetén, a Chaos Engineering-re tekinthetünk úgy, mint a rendszerszintű gyengeségek feltárására irányuló kísérletek végrehajtása. Ezek a kísérletek négy lépésből állnak:

1. Kezdjük a "nyugalmi állapot" definiálásával, amikor a rendszer valamilyen mérhető tulajdonságát tekintjük normál működésnek.
2. Feltételezzük, hogy a nyugalmi állapot megmarad mind a kísérleti és a kontroll csoportban.
3. Idézzünk elő olyan eseményeket, amelyek valós eseményeket szimulálnak, mint szerver összeomlás, merevlemez rendellenesség, gyenge hálózati kapcsolat, stb.
4. Próbáljuk cáfolni az eredeti feltételezésünket úgy, hogy megfigyeljük hogy van-e eltérés a nyugalmi állapotban a kontroll és a kísérleti csoport között.

Minél nehezebb megzavarni a nyugalmi állapotot, annál biztosabbak vagyunk a rendszerünk működésével kapcsolatban. Ha felfedezünk egy gyengeséget, akkor a célunk, hogy fejlesszük, javítsuk ezt, mielőtt ez a jelenség a rendszert szélesebb körben érintené.

## HALADÓ IRÁNYELVEK

A következő irányelvek a Chaos Engineering ideális alkalmazását mutatják be, a fent leírt kísérletezési folyamatok alkalmazására vonatkozólag. Ezen alapelvek megvalósításának mértéke erősen korrelál azzal, hogy mennyire vagyunk biztosak az elosztott skálázódó rendszerünk működésében.

### A nyugalmi állapot hipotézis felállítása

Inkább a rendszer egyik mérhető kimenetére kell fókuszálni, mint egy belső rendszer jellemzőre. Ennek a kimenetnek a rövid időn keresztül történő mérései mutatják a rendszer nyugalmi állapotát. A rendszer átviteli teljesítménye, hibaarány, késleltetési szintek, stb. Lehet olyan metrika, amely a rendszer nyugalmi állapotát mutatja. Azzal, hogy a rendszerszintű viselkedésre koncentrálunk a kísérlet alatt, a káosz azt vizsgálja, hogy a rendszer működik, és nem azt próbálja ellenőrizni, hogy hogyan működik.

### Változatos valós események

A Káosz változók különböző valós eseményeket fejeznek ki. Priorizáld az eseményeket vagy a potenciális hatásuk, vagy az előfordulásuk gyakorisága alapján. Vedd számításba az olyan eseményeket is, amelyek hardver meghibásodást jelentenek, szerver összeomlással, szoftver hibákat hibás válaszokkal, és az olyan, nem feltétlenül hibás eseményeket, mint például egy hirtelen jött nagy terhelés, vagy skálázódás. Minden olyan esemény, amely képes megzavarni a rendszer nyugalmi állapotát, az egy potenciális tényező egy Káosz kísérletben.

### A produkciós környezetben kísérletezz

A rendszerek különbözőképpen viselkednek környezettől és terheléstől függően. Mivel a rendszer igénybevétele bármelyik pillanatban változhat, ezért a valós terhelés minta az egy egyetlen megbízható módszer a rendszerhez érkező kérések megfigyelésére. Hogy garantálva legyen az, hogy a rendszer hitelesen viselkedik, és ez az aktuálisan telepített rendszerre vonatkozzon, a Chaos engineering erősen javasolja, hogy a kísérleteket közvetlenül a produkciós forgalmon végezzük.

### Automatizáld a kísérleteket, hogy folyamatosan futtathatók legyenek

A kísérletek manuális futtatása nagyon munkaigényes, és nehezen fenntartható. Automatizáld ezeket a kísérleteket, és folyamatosan futtasd őket. A Chaos Engineering automatizálásával fejlődni fog a rendszer telepítése és tesztelése is.

### Minimalizáld a hatókört

Az éles környezetben való kísérletezés okozhat ügyfél elégedetlenséget is. Rövid ideig tartó negatív hatások előfordulhatnak, de az a Chaos engineer hatásköre és felelőssége, hogy a kísérletekkel járó üzletmenet kiesések a lehető legalacsonyabbak legyenek.

A Chaos Engineering egy jó gyakorlat, ami már most megváltoztatta a szoftvertervezést, és megvalósítást a világ legnagyobb méretű rendszereinél. Míg más módszertanok a fejlesztés rugalmasságát és felgyorsítását célozzák meg, a Chaos engineering kifejezetten az elosztott rendszerek bizonytalanságával foglalkozik. A Chaos Engineering alapelvei segítenek a nagy léptékű, gyors innovációkkal járó bizonytalanságot kezelni, annak érdekében hogy az ügyfelek magas színvonalú kiszolgálásban részesüljenek.

Csatlakozz a Chaos Engineering alapelveiről és annak alkalmazásáról szóló beszélgetésekhez Google Csoportba [Chaos Community](https://groups.google.com/forum/#!forum/chaos-community).
