+++
title = "DE PRINCIPES VAN CHAOS ENGINEERING"
date = 2023-12-04T16:25:57+01:00
draft = false
+++

# DE PRINCIPES VAN CHAOS ENGINEERING
Laatst bijgewerkt: december 2023

*Chaos Engineering is het vakgebied dat zich bezighoudt met het uitvoeren van experimenten op een systeem met als doel vertrouwen te creëren in het vermogen van het systeem om turbulente productieomstandigheden te kunnen doorstaan.*

De spelregels voor softwareontwikkeling veranderen als gevolg van ontwikkelingen op het gebied van grootschalige, gedistribueerde softwaresystemen. De IT-industrie zet voortdurend nieuwe methoden in om zowel de flexibiliteit van softwareontwikkeling als de doorloopsnelheid van deployments te verhogen. Deze veranderingen roepen een dringende vraag op: hoeveel vertrouwen kunnen we hebben in de complexe systemen die we in productie nemen? Zelfs wanneer alle afzonderlijke services in een gedistribueerd systeem goed functioneren, kan de interactie tussen deze services onvoorspelbare uitkomsten opleveren. Deze onverwachte resultaten, verergerd door zeldzame, maar ontwrichtende gebeurtenissen in productie, maken gedistribueerde systemen inherent chaotisch.

We moeten zwakke plekken in het systeem identificeren voordat ze zich manifesteren als systeem-breed afwijkend gedrag. Zwakke punten in het systeem kunnen verschillende vormen aannemen zoals: onjuiste fallback-instellingen als een service niet beschikbaar is; ‘retry storms’ door verkeerd ingestelde time-outs, storingen als gevolg van overbelaste afhankelijkheden of kettingreacties in het geval een single point of failure faalt. Het is belangrijkste proactief de zwakke punten aan te pakken voordat onze klanten er in productie hinder van ondervinden. We hebben een methode nodig om de inherente chaos in deze systemen te beheersen, zodat we kunnen profiteren van de toenemende flexibiliteit en snelheid, terwijl toch vertrouwen houden in onze complexe productiesystemen.

Een empirische, op systemen gebaseerde aanpak, richt zich op de chaos in grootschalige gedistribueerde systemen en bouwt vertrouwen op in het vermogen van die systemen om realistische omstandigheden aan te kunnen. We leren over het gedrag van een gedistribueerd systeem door het te observeren tijdens een gecontroleerd experiment.  Dit noemen we *Chaos Engineering*.

## CHAOS DE PRAKTIJK

Om specifiek de onzekerheid van gedistribueerde systemen op schaal aan te pakken, kan Chaos Engineering worden gezien als het faciliteren van experimenten om zwakke punten in het systeem bloot te leggen.  Deze experimenten bestaan uit vier stappen:

1. Begin door de stabiele situatie te definiëren als een meetbare output die het normale gedrag van het systeem beschrijft. 
2. Formuleer de hypothese dat zowel de controlegroep als de experimentele groep in deze stabiele situatie blijven.
3. Introduceer variabelen die echte gebeurtenissen in productie weerspiegelen, zoals servers die crashen, harde schijven die falen, netwerkverbindingen die worden verbroken, etc.
4. Probeer de hypothese te weerleggen door te zoeken naar een verschil in de stabiele situatie tussen de controlegroep en de experimentele groep.

Hoe lastiger het is om een systeem uit de stabiele toestand te halen, des te meer vertrouwen we hebben in het gedrag van het systeem. Mochten we een zwak punt ontdekken, dan kunnen we dit nu doelgericht aanpakken voordat het gedrag zich manifesteert in het hele systeem.

## GEAVANCEERDE PRINCIPES

De volgende principes beschrijven een ideale toepassing van Chaos Engineering, gebaseerd op de bovenstaande processen. De mate waarin deze principes worden nagestreefd, hangt sterk af van de mate van vertrouwen die we hebben in een gedistribueerd systeem op schaal.

### Formuleer een hypothese rond het gedrag in de stabiele situatie

Richt je op de meetbare output, in plaats van de interne eigenschappen van het systeem. Metingen van die output gedurende een korte periode vormen een indicatie voor de stabiele situatie van het systeem. De totale verwerkingscapaciteit van het systeem, foutpercentages, reactietijden etc. kunnen allemaal interessante metingen zijn voor het beschrijven van de statiele situatie. Door tijdens experimenten te focussen op systemische gedragspatronen, verifieert Chaos Engineering dat het systeem werkt, maar het valideert niet hoe het systeem werk.

### Varieer met realistische gebeurtenissen

Chaosvariabelen weerspiegelen daadwerkelijk optredende gebeurtenissen. Geef prioriteit aan gebeurtenissen op basis van hun potentiële impact of geschatte frequentie. Overweeg gebeurtenissen die overeenkomen met hardware storingen zoals het uitvallen van servers, softwarestoringen zoals corrupte netwerk responses, maar ook gebeurtenissen die niet veroorzaakt worden door een storing zoals een piek in het verkeer of opschalen van de capaciteit. Elke gebeurtenis die mogelijke de stabiele situatie verstoort, is een potentiële variabele in een Chaos-experiment.

### Experimenteer in productie

Systemen gedragen zich verschillend afhankelijk van de omgeving en netwerkverkeer. Aangezien het typische gebruik van het systeem ieder moment kan veranderen, is het observeren van productieverkeer de enige betrouwbare manier om het pad van een request door het systeem vast te leggen. Om ervoor te zorgen dat het systeem realistisch wordt belast en om relevant te zijn voor het huidige productiesysteem, geeft Chaos Engineering er sterk de voorkeur aan experimenten uit te voeren met productieverkeer.

### Automatiseer experimenten en voer ze continu uit

Handmatig uitvoeren van experimenten is arbeidsintensief en uiteindelijk onhoudbaar. Automatiseer de experimenten en voer ze continu uit. Chaos Engineering bouwt automatisering in het systeem om het aansturen en analyseren van experimenten te verbeteren.

### Minimaliseer *Blast Radius*

Experimenteren in productie kan onnodige problemen bij klanten te veroorzaken. Hoewel er rekening moet worden gehouden met beperkte negatieve impact op de korte termijn, is het de verantwoordelijkheid en verplichting van de Chaos Engineer om ervoor te zorgen dat de gevolgen van experimenten minimaal en beperkt zijn.

Chaos Engineering is een effectieve methode die nu al de manier verandert waarop enkele van de grootste bedrijven ter wereld software ontwerpen en ontwikkelen. Waar andere methodes zich richten op snelheid en flexibiliteit, pakt Chaos Engineering specifiek de systemische onzekerheid in gedistribueerde systemen aan. De principes van Chaos Engineering geven vertrouwen om snel te op grote schaal te innoveren en klanten de hoge kwaliteitservaringen te geven die ze verdienen.

Doe mee aan de voortdurende discussie over de Principes van Chaos Engineering en hun toepassing in de [Chaos Community](https://groups.google.com/forum/#!forum/chaos-community).