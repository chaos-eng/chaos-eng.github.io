+++
title = "Principiile ingineriei HAOS"
date = 2020-01-28T16:25:57+02:00
draft = false
+++

# PRINCIPIILE INGINERIEI HAOS
Ultima actualizare: Ianuarie 2020

*Ingineria Haosului este disciplina experimentării pe un sistem pentru a consolida încrederea în capacitatea sistemului de a rezista condițiilor turbulente în mediu operațional.*

Creșterea fără precedent a sistemelor software distribuite la scară largă schimbă regulile jocului în tehnica modernă a calculatoarelor. Industria adoptă rapid tehnici care cresc agilitatea dezvoltării și viteza de desfășurare. Însă, după avantajele evidente ale noilor metodologii, apare o întrebare: Cât de încrezători suntem despre fiabilitatea sistemelor complexe pe care le punem în funcțiune?

Chiar și atunci când fiecare serviciu individual dintr-un sistem distribuit funcționează corect, interacțiunea dintre aceste servicii poate duce la rezultate imprevizibile. Rezultatele imprevizibile sunt agravate de evenimente reale rare, dar distructive, care afectează mediul operațional și conferă sistemelor distribuite proprietăți haotice.

Trebuie să determinăm punctele slabe ale sistemului înainte de a se revașa în defecțiuni la nivelul întregului sistem.

Defecțiunile sistemice pot lua următoarele forme: configurarea incorectă a opțiunii de rezerva, dacă serviciul nu este disponibil; o serie de încercări repetate de conectare ca urmare a setărilor incorecte de pauze (timeout); întreruperi atunci când o dependență primește din aval prea mult trafic; erori în cascadă într-un singur punct de eșec ([SPOF](https://en.wikipedia.org/wiki/Single_point_of_failure)), etc. Trebuie să eliminăm proactiv defectele cele mai semnificative înainte ca să afecteze clienții din production. Avem nevoie de modalități de a controla haosul inerent al acestor sisteme. Doar în acest fel vom reuși să realizăm pe deplin avantajele unei flexibilități și viteze mai mari și să derulăm cu încredere actualizări, indiferent de nivelul lor de complexitate.

O abordare empirică, orientată către sistem, elimină haosul în sistemele distribuite la scară largă și creează încredere în capacitatea acestor sisteme de a rezista condițiilor din lumea reală. Studiem comportamentul unui sistem distribuit observându-l în timpul unui experiment controlat. Aceasta este ceea ce numim *Ingineria Haosului*.

## HAOSUL ÎN PRACTICĂ

Ca instrument de gestionare a incertitudinii sistemelor distribuite la scară largă, Ingineria Haos servește la facilitarea experimentelor pentru identificarea defectelor sistemice. Protocolul acestor experimente constă din patru etape:

1. Începeți prin a defini o "stare de echilibru" ca o ieșire măsurabilă dintr-un sistem care indică un comportament normal.
2. Presupunem că această stare de echilibru va continua atât în ​​grupul de control, cât și în grupul experimental.
3. Introduceți variabile care reflectă evenimente reale, cum ar fi: servere care se prăbușeste, hard disk-uri rele, conexiuni de rețea încălcate etc.
4. Încercați să respingeți ipoteza comparând starea stabilă a grupului de control și a grupului experimental.

Cu cât este mai dificil să rupeți starea constantă, cu atât suntem mai siguri în fiabilitatea sistemului. Dacă se detectează slăbiciune, avem un obiectiv de îmbunătățire, care va preveni influența ulterioară a erorii asupra sistemului în ansamblu.

## PRINCIPII AVANSATE

Următoarele principii descriu aplicarea ideală a Ingineriei Haos aplicată proceselor experimentale descrise mai sus. Gradul de aderare la aceste principii se corelează cu gradul de încredere în operarea sistemelor distribuite la scară largă.

### Ipoteza în jurul stării de echilibru

Concentrați-vă pe starea măsurabilă a sistemului, nu pe atributele interne ale sistemului. Măsurarea acestor indicatori pentru o perioadă scurtă de timp este o indicație a stării constante a sistemului. Randamentul total, procentul de erori, timpul de întârziere etc. - toate pot fi măsuri semnificative ale comportamentului durabil. Prin concentrarea pe comportamente sistemice în timpul experimentelor, abordarea Haos verifică dacă sistemul funcționează cu adevărat, în loc să încerce să verifice cum se întâmplă acest lucru.

### Alternati evenimente reale

Variabilele haosului reflectă evenimente reale. Verificați evenimentele în funcție de gradul de impact potențial sau de frecvența preconizată a apariției. Luați în considerare evenimentele cauzate de defecțiunile hardware, cum ar fi eșecul serverului, defecțiuni ale software-ului, cum ar fi răspunsuri malformate și evenimente care nu au defecțiuni, precum abundente de trafic sau operațiuni de scalare. Orice eveniment care poate încălca o stare constantă este o variabilă potențială într-un experiment de haos.

### Faceți experimente în mediul de dezvoltare

Comportamentul sistemului depinde de mediu și de fluxul de date. Deoarece modul de utilizare a resurselor se poate schimba oricând, eșantionarea fluxului de date real este singura cale de a urmări în mod fiabil ruta de solicitare. Pentru a garanta autenticitatea funcționării sistemului și relevanța datelor, Haos preferă să se efectueze experimente direct pe traficul real.

### Automatizați experimentele pentru a rula continuu

Experimentele manuale sunt laborioase și, în cele din urmă, nu sunt de încredere. Automatizati experimentele și rulati-le tot timpul. Ingineria Haosului integrează automatizarea în sistem pentru a controla atât coordonarea actiunilor cât și analiza datelor.

### Minimizarea zonei afectate

Experimentele în production pot dăuna utilizatorilor. Deși ne asumăm riscul de efecte negative pe termen scurt, inginerul Haos este responsabil pentru minimizarea eșecurilor și tulburărilor cauzate de experimente.

Ingineria Haos este o practică eficientă care schimbă deja modul în care este planificat și dezvoltat software-ul la unele dintre cele mai mari întreprinderi din lume. În timp ce alte metode se ocupă de viteză și flexibilitate, Haos tratează în mod specific incertitudinea sistemică în aceste sisteme distribuite. Principiile haosului oferă încrederea necesară pentru a inova rapid pe scară largă și pentru a oferi clienților servicii de înaltă calitate.

Alăturați-vă discuției despre principiile Haos și aplicarea lor în Google Group [Chaos Community](https://groups.google.com/forum/#!forum/chaos-community).
