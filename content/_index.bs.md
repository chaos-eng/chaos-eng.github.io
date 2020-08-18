+++
title = "OSNOVNA NAČELA INŽINJERINGA HAOSA"
date = 2020-01-28T16:25:57+02:00
draft = false
+++

# OSNOVNA NAČELA INŽINJERINGA HAOSA
Posljednje ažuriranje: Jan 2020.

*Inžinjering haosa je disciplina experimentisanja na sistemu da bi se izgradilo povjerenje u sposobnost sistema da izdrži nagle promjene pri korištenju u produkciji.*

Napredak velikih distribuiranih softverskih sistema mijenja igru ​​za softverski inženjering. Kao industrija, brzo prihvatamo prakse koje povećavaju fleksibilnost razvoja i brzinu implementacije. Ovo nameće slijedeće pitanje: Koliko povjerenja možemo imati u složene sisteme koje koristimo u produkciji?

Čak i kada sve pojedinačne usluge u distribuiranom sistemu funkcionišu ispravno, interakcije između tih usluga mogu uzrokovati nepredvidive ishode. Nepredvidivi ishodi, sastavljeni od rijetkih, ali remetilačkih događaja iz stvarnog svijeta koji utječu na okruženja u produkciji, čine ove distribuirane sisteme inherentno haotičnim.

Treba identifikovati slabosti prije nego što se pojave u neželjenom obliku širom sistema. Sistemske slabosti mogle bi biti u obliku: neispravnih rezervnih postavki kada usluga nije dostupna; preveliki pokušaji zapisa iz nepravilno podešenih vremenskih ograničenja; kvarovi zbog prezagušenog prometa; kaskadni otkazi kada se sruši samo jedan čvor; itd. Najznačajnije slabosti moraju se riješiti proaktivno, prije nego što utječu na kupce u produkciji. Potreban je način upravljanja haosom svojstvenim ovim sistemima, iskoristiti veću fleksibilnost i brzinu i imati povjerenja u sisteme u produkciji uprkos složenosti koju predstavljaju.

Empirijski, sistemski zasnovan pristup rješavanja haosa u distribuiranim sistemima i izgradnja povjerenja u sistem da može izdržati opterećenja i napade u realnim uslovima. O ponašanju distribuiranog sistema učimo posmotrajući ga tokom kontrolisanog eksperimenta. Mi to nazivamo *Inžinjeringom haosa*.

## HAOS U PRAKSI

Da bi se konkretno pozabavilo nesigurnošću distribuiranih skaliranih sistema, Inžinjering haosa se može smatrati eksperimentom koji olakšava otkrivanje slabosti sistema. Ti eksperimenti imaju četiri koraka:

1. Definisati "stabilno stanje" kao izlaz koji predstavlja normalno ponašanje.
2. Pretpostavka da će se to stabilno stanje ostati i u kontrolnoj i u eksperimentalnoj grupi.
3. Uvođenje promjenjivih koje odražavaju događaje iz stvarnog svijeta poput servera koji se ruše, hard diskova koji ne rade, mrežne veze koje su prekinute ili usporene i slično.
4. Pokušaj opovrgavanja hipoteze tražeći razliku stabilnosti sistema između kontrolne i eksperimentalne grupe.

Što je teže poremetiti stabilno stanje, to se više povjerenja ima u ponašanje sistema. Ako se otkrije slabost, sada se ima cilj za poboljšanje prije nego što se takvo ponašanje manifestuje u sistemu uopšte.

## NAPREDNA NAČELA

Sljedeća načela opisuju idealnu primjenu Inžinjeringa haosa, primijenjenu na gore opisane postupke eksperimentisanja. Stepen primjene ovih načela snažno je u korelaciji s povjerenjem koje se može imati u skaliranom distribuiranom sistemu.

### Izgradnja hipoteze o stabilnom ponašanju

Skoncentrisati se na mjerljivi izlaz sistema, a ne na unutrašnje atribute sistema. Merenja tog izlaza tokom kratkog vremenskog perioda predstavljaju proxy za stabilno stanje sistema. Propusnost cjelokupnog sistema, stope grešaka, postotci kašnjenja itd., Sve bi to mogle biti mjerne vrijednosti koje predstavljaju ponašanje u stabilnom stanju. Usredsređujući se na sistemske obrasce ponašanja tokom eksperimenata, Haos potvrđuje da sistem radi, a ne pokušava da potvrdi kako funkcioniše.

### Različiti događaji iz stvarnog svijeta

Promjenjive haosa odražavaju stvarna dešavanja. Prioritetno odrediti događaje bilo potencijalnim utjecajem ili procijenjenom učestalošću. Razmotriti događaje koji odgovaraju greškama hardvera poput servera koji umire, softverske kvarove poput nepravilnih odgovora i događaje koji to nisu, poput duha u prometu ili kod skaliranja. Svaki događaj koji može narušiti stabilno stanje potencijalna je promjenjiva u eksperimentu Haosa.

### Izvršiti eksperimente u produkciji

Sistemi se ponašaju različito ovisno o okruženju i obrascima prometa. Budući da se ponašanje korištenja može promijeniti u bilo kojem trenutku, uzorkovanje stvarnog prometa jedini je način pouzdanog hvatanja putanje zahtjeva. Kako bi garantovali istinitost načina na koji se sistem koristi i relevantnost za trenutni implementirani sistem, Haos snažno preferira eksperimentisanje direktno na proizvodnom prometu.

### Automatiziranje eksperimenata kako bi se stalno izvodili

Ručno pokretanje eksperimenata naporno je i na kraju neodrživo. Automatizirajte eksperimente i pustite ih da trče stalno. Inžinjering haosa ugrađuje automatizaciju u sistem kako bi pokrenuo i orkestraciju i analizu.

### Umanjiti radijus udara

Eksperimentisanje u produkciji može izazvati nepotrebne bolove kod kupaca. Iako mora postojati dopuštenje za kratkoročni negativni utjecaj, inženjer haosa je dužan osigurati da ispadi iz eksperimenata budu minimizirani i sadržani.

Inžinjering haosa je snažna praksa koja već mijenja način na koji je softver dizajniran i oblikovan u nekim od najvećih operacija na svijetu. Kada se druge prakse bave brzinom i fleksibilnošću, Haos se posebno bavi sistemskom nesigurnošću u tim distribuiranim sistemima. Načela Haosa pružaju samopouzdanje za brzo uvođenje inovacija na golemoj skali i kupcima pružaju visokokvalitetno iskustvo koje zaslužuju.

Pridružite se tekućoj raspravi o načelima haosa i njihovoj primjeni u Google grupi [Chaos Community](https://groups.google.com/forum/#!forum/chaos-community).
