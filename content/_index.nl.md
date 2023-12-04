+++
title = "PRINCIPES VAN CHAOS ENGINEERING"
date = 2023-11-28T16:25:57+02:00
draft = true
+++

# PRINCIPES VAN CHAOS ENGINEERING
Laatste Update: 2023 November

*Chaos Engineering is het vakgebied dat zich bezighoudt met het uitvoeren van experimenten op een systeem met als doel vertrouwen op te bouwen in het vermogen van het systeem om productieomstandigheden aan te kunnen.*

Door ontwikkelingen op het gebied van grootschalige, gedistribueerde softwaresystemen veranderen de spelregels voor softwareontwikkeling. De IT-industrie zet voortdurend nieuwe methoden in om de flexibiliteit van softwareontwikkeling en de doorloopsnelheid van deployments te verhogen. Deze veranderingen roepen een dringende vraag op: hoeveel vertrouwen kunnen we hebben in de complexe systemen die we in productie nemen?

Zelfs als alle verschillende services in een gedistribueerd systeem goed functioneren, kan de interactie tussen deze services onvoorspelbare uitkomsten opleveren. Deze onverwachte resultaten, verergerd door zeldzame, maar verstorende gebeurtenissen in de productieomgeving, maken gedistribueerde systemen inherent chaotisch.

We moeten zwakke plekken in het systeem identificeren voordat ze zich openbaren als systeem-breed afwijkend gedrag. Zwakke punten in het systeem kunnen verschillende vormen aannemen zoals: onjuiste fallback instellingen als een service niet beschikbaar is; retry storms bij onjuist ingestelde time-outs, storingen wanneer een afhankelijkheid te veel verkeer te verwerken krijgt, kettingreacties in het geval een single point of failure faalt, etc. We moeten de belangrijkste zwakke punten proactief aanpakken voordat onze klanten er in productie last van hebben. We hebben een manier nodig om de inherente chaos in deze systemen te beheersen om te kunnen profiteren van de toenemende flexibiliteit en snelheid en daarnaast, ondanks hun complexiteit, vertrouwen te hebben in onze productiesystemen.

Een empirische, systeem-gebaseerde aanpak pakt de chaos in grootschalige gedistribueerde systemen aan en bouwt vertrouwen op in het vermogen van die systemen om realistische omstandigheden aan te kunnen. We leren over het gedrag van een gedistribueerd systeem door het te observeren tijdens een gecontroleerd experiment.  We noemen dit *Chaos Engineering*.

## CHAOS DE PRAKTIJK

To specifically address the uncertainty of distributed systems at scale, Chaos Engineering can be thought of as the facilitation of experiments to uncover systemic weaknesses.  These experiments follow four steps:

1. Start by defining ‘steady state’ as some measurable output of a system that indicates normal behavior.
2. Hypothesize that this steady state will continue in both the control group and the experimental group.
3. Introduce variables that reflect real world events like servers that crash, hard drives that malfunction, network connections that are severed, etc.
4. Try to disprove the hypothesis by looking for a difference in steady state between the control group and the experimental group.

The harder it is to disrupt the steady state, the more confidence we have in the behavior of the system.  If a weakness is uncovered, we now have a target for improvement before that behavior manifests in the system at large.

## ADVANCED PRINCIPLES

The following principles describe an ideal application of Chaos Engineering, applied to the processes of experimentation described above.  The degree to which these principles are pursued strongly correlates to the confidence we can have in a distributed system at scale.

### Build a Hypothesis around Steady State Behavior

Focus on the measurable output of a system, rather than internal attributes of the system.  Measurements of that output over a short period of time constitute a proxy for the system’s steady state.  The overall system’s throughput, error rates, latency percentiles, etc. could all be metrics of interest representing steady state behavior.  By focusing on systemic behavior patterns during experiments, Chaos verifies that the system does work, rather than trying to validate how it works.

### Vary Real-world Events

Chaos variables reflect real-world events.  Prioritize events either by potential impact or estimated frequency.  Consider events that correspond to hardware failures like servers dying, software failures like malformed responses, and non-failure events like a spike in traffic or a scaling event.  Any event capable of disrupting steady state is a potential variable in a Chaos experiment.

### Run Experiments in Production

Systems behave differently depending on environment and traffic patterns.  Since the behavior of utilization can change at any time, sampling real traffic is the only way to reliably capture the request path.  To guarantee both authenticity of the way in which the system is exercised and relevance to the current deployed system, Chaos strongly prefers to experiment directly on production traffic.

### Automate Experiments to Run Continuously

Running experiments manually is labor-intensive and ultimately unsustainable.  Automate experiments and run them continuously.  Chaos Engineering builds automation into the system to drive both orchestration and analysis.

### Minimize Blast Radius

Experimenting in production has the potential to cause unnecessary customer pain. While there must be an allowance for some short-term negative impact, it is the responsibility and obligation of the Chaos Engineer to ensure the fallout from experiments are minimized and contained.

Chaos Engineering is a powerful practice that is already changing how software is designed and engineered at some of the largest-scale operations in the world.  Where other practices address velocity and flexibility, Chaos specifically tackles systemic uncertainty in these distributed systems.  The Principles of Chaos provide confidence to innovate quickly at massive scales and give customers the high quality experiences they deserve.

Join the ongoing discussion of the Principles of Chaos and their application in the [Chaos Community](https://groups.google.com/forum/#!forum/chaos-community).
