+++
title = "PRINCIPI DI INGEGNERIA DEL CAOS"
date = 2020-01-28T16:25:57+02:00
draft = false
+++

# PRINCIPI DI INGEGNERIA DEL CAOS
Ultimo aggiornamento: maggio 2018

*L'ingegneria del chaos è una disciplina che consiste nello sperimentare un sistema distribuito, in modo da generare confidenza nelle capacità del sistema
nel resistere a condizioni turbolente in produzione.*

I progressi nei sistemi software distribuiti su larga scala stanno cambiando il gioco per l'ingegneria del software. In quanto industria, siamo pronti ad adottare pratiche che aumentano la flessibilità dello sviluppo e la velocità di implementazione. Una domanda urgente segue immediatamente questi benefici: quanta fiducia possiamo avere nei sistemi complessi che mettiamo in produzione?

Anche quando tutti i singoli servizi di un sistema distribuito funzionano correttamente, le interazioni tra questi servizi possono causare esiti imprevedibili. Esiti imprevedibili, combinati con eventi reali rari ma dirompenti che influenzano gli ambienti di produzione, rendono questi sistemi distribuiti intrinsecamente caotici.

Dobbiamo identificare i punti deboli prima che si manifestino in comportamenti aberranti a livello di sistema. Le carenze sistemiche potrebbero assumere la forma di: impostazioni fallback errate quando un servizio non è disponibile; ritentare le tempeste da timeout impropriamente sintonizzati; interruzioni quando una dipendenza downstream riceve troppo traffico; guasti a cascata quando un singolo punto di errore si blocca; ecc . Dobbiamo affrontare le debolezze più significative in modo proattivo, prima che influenzino i nostri clienti nella produzione. Abbiamo bisogno di un modo per gestire il caos inerente a questi sistemi, sfruttare l'aumento della flessibilità e della velocità e avere fiducia nelle nostre implementazioni produttive nonostante la complessità che rappresentano.

Un approccio empirico, basato sui sistemi risolve il caos nei sistemi distribuiti su larga scala e crea fiducia nella capacità di tali sistemi di resistere condizioni realistiche. Apprendiamo il comportamento di un sistema distribuito da osservando durante un esperimento controllato Chiamiamo questo *Ingegneria del caos*.

## CAOS IN PRATICA

Per risolvere specificamente l'incertezza dei sistemi distribuiti su larga scala, Chaos Engineering può essere pensata come la facilitazione di esperimenti per scoprire debolezze sistemiche. Questi esperimenti seguono quattro passaggi:

1. Inizia definendo 'stato stazionario' come un output misurabile di un sistema che indica un comportamento normale.
2. Hypothesize che questo steady state continuerà sia nel gruppo di controllo che nel gruppo sperimentale.
3. Introduci variabili che riflettono eventi del mondo reale come server che si bloccano, dischi rigidi che funzionano male, connessioni di rete interrotte, ecc.
4. Prova a smentire l'ipotesi cercando una differenza di stato stazionario tra il gruppo di controllo e il gruppo sperimentale.

Più è difficile perturbare lo stato stazionario, maggiore è la fiducia nel comportamento del sistema. Se viene rilevata una vulnerabilità, ora abbiamo un obiettivo di miglioramento prima che il comportamento si manifesti nel sistema in generale. 

## PRINCIPI AVANZATI

I seguenti principi descrivono un'applicazione ideale di Chaos Engineering, applicata ai processi di sperimentazione descritti sopra. Il grado in cui questi principi sono perseguiti è fortemente correlato alla fiducia che possiamo avere in un sistema distribuito su vasta scala. 

### Crea un'ipotesi attorno al comportamento dello stato stazionario

Concentrati sull'output misurabile misurabile di un sistema, piuttosto che attributi interni del sistema. Le misurazioni di quell'output in un breve periodo di tempo costituiscono un proxy per lo stato stazionario del sistema. Il throughput complessivo del sistema, i tassi di errore, i percentili di latenza, ecc. Potrebbero essere tutti parametri di interesse che rappresentano il comportamento a regime. Concentrandosi sui modelli comportamentali sistemici durante gli esperimenti, Chaos verifica che il sistema fa funziona, invece di provare a convalidare come funziona. 

### Variazione gli eventi del mondo reale

Le variabili del Chaos riflettono eventi del mondo reale. Assegna la priorità agli eventi in base al potenziale impatto o alla frequenza stimata . Considera eventi che corrispondono a guasti hardware come server che muoiono, errori software come risposte errate e eventi non di fallimento come un picco in traffico o un evento di ridimensionamento. Qualsiasi evento in grado di interrompere lo steady state è una variabile potenziale in un esperimento Caos. 

### Esegui esperimenti in produzione

I sistemi si comportano in modo diverso a seconda dell'ambiente e dei modelli di traffico. Poiché il comportamento dell'utilizzo può cambiare in qualsiasi momento, il campionamento del traffico reale è l'unico modo per acquisire in modo affidabile il percorso della richiesta. Per garantire sia l'autenticità del modo in cui il sistema viene esercitato che la pertinenza con il sistema attuale implementato, Chaos preferisce fortemente sperimentare direttamente sul traffico di produzione . 

### Automatizza gli esperimenti per l'esecuzione continua

L'esecuzione manuale degli esperimenti è laboriosa e alla fine insostenibile. Automatizza gli esperimenti ed eseguili continuamente. Chaos Engineering crea l'automazione nel sistema per guidare sia l'orchestrazione che l'analisi. 

### Riduci raggio di esplosione

L'esperimento in produzione ha il potenziale per causare dolore al cliente non necessario. Sebbene debba esserci un margine per un impatto negativo a breve termine, è responsabilità e obbligo del Chaos Engineer assicurare che le ricadute dagli esperimenti siano ridotte al minimo e contenute. 

Chaos Engineering è una pratica potente che sta già cambiando il modo in cui il software è progettato e progettato in alcune delle operazioni su scala più grande del mondo. Laddove altre pratiche affrontano velocità e flessibilità, Chaos affronta specificamente l'incertezza sistemica in questi sistemi distribuiti. The Principles of Chaos fornisce sicurezza per innovare rapidamente su enormi scale e offrire ai clienti le esperienze di alta qualità che meritano. 

Partecipa alla discussione in corso sui Principles of Chaos e la loro applicazione nel Google Group [Chaos Community](https://groups.google.com/forum/#!forum/chaos-community).
