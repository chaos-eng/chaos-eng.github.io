+++
title = "PRINCIPES D’INGENIERIE DU CHAOS"
date = 2020-01-28T16:25:57+02:00
draft = false
+++

# PRINCIPES D’INGENIERIE DU CHAOS
Mise à jour : Mai 2018

*L’Ingénierie du Chaos est une discipline de l’expérimentation sur un système distribué afin de renforcer la confiance dans la capacité du système à résister à des conditions turbulentes en production.*

Les progrès dans les systèmes logiciels distribués à grande échelle changent le jeu pour l'ingénierie logicielle. En tant qu'industrie, nous adoptons rapidement des pratiques qui augmentent la flexibilité de développement et la rapidité de déploiement. Une question urgente émerge alors de ces évolutions : Quelle confiance pouvons-nous avoir dans les systèmes complexes que nous mettons en production ?

Même lorsque chacun des services d'un système réparti fonctionne individuellement correctement, les interactions entre ces services peuvent entraîner des résultats imprévisibles. Des résultats imprévisibles, aggravés par des événements rares mais perturbateurs du monde réel qui affectent les environnements de production, et rendent ces systèmes distribués intrinsèquement chaotiques.

Nous devons identifier les faiblesses avant qu'elles ne se manifestent dans des comportements aberrants à l'échelle du système. Les faiblesses systémiques peuvent prendre la forme de : paramètres de fallback inadéquats lorsqu'un service est indisponible ; tentative de reprise avec effets cataclysmique à la suite de timeout incorrectement réglées ; pannes lorsqu'une dépendance en aval reçoit trop de trafic ; échecs en cascade à la suite de la défaillance d’un seul point ; etc. .  Nous devons aborder les faiblesses les plus significatives de manière proactive, avant qu'elles n'affectent nos clients en production. Nous avons besoin d'un moyen de gérer le chaos inhérent à ces systèmes, de tirer parti de la flexibilité et de la vitesse croissantes, et de faire confiance à nos déploiements de production malgré la complexité qu'ils représentent.

Une approche empirique basée sur les systèmes aborde le chaos dans les systèmes distribués à grande échelle et renforce la confiance dans la capacité de ces systèmes à résister aux conditions du monde réel. Nous apprenons le comportement d'un système distribué en l'observant lors d'une expérience contrôlée. Nous appelons cela *l'Ingénierie du Chaos*.


## CHAOS EN PRATIQUE

Pour répondre spécifiquement à l'incertitude des systèmes distribués à grande échelle, l'Ingénierie du Chaos peut être considérée comme la facilitation d’expériences pour découvrir les faiblesses systémiques. Ces expériences suivent quatre étapes :

1. Définir un « état stable » comme une sortie mesurable d'un système qui indique un comportement normal.
2. Faire l’hypothèse que cet état d'équilibre se poursuivra dans le groupe témoin et dans le groupe expérimental.
3. Introduire des variations qui reflètent des événements réels, tels que les serveurs en panne, les disques durs défectueux, les connexions réseau coupées, etc.
4. Tenter de réfuter l'hypothèse en recherchant une différence d'état d'équilibre entre le groupe témoin et le groupe expérimental.

Plus il est difficile de perturber l'état stable, plus nous avons confiance dans le comportement du système. Si une faiblesse est découverte, nous avons maintenant un objectif d'amélioration pour éviter que ce comportement ne se manifeste un jour.

## PRINCIPES AVANCÉS

Les principes suivants décrivent une application idéale de l’Ingénierie du Chaos, en appliquant le processus d'expérimentation décrits ci-dessus. Le degré d’application de ces principes est fortement corrélé à la confiance que nous pouvons avoir dans un système distribué à grande échelle.

### Définir l’hypothèse “Etat Stable” 

Il est préférable de se concentrer sur la sortie mesurable d'un système plutôt que sur les attributs internes du système. Il faut ensuite effectuer ces mesures sur une courte période de temps afin de définir les valeurs constituant l'état stationnaire du système. Le débit global du système, les taux d'erreur, les percentiles de latence, etc. sont tous des indicateurs intéressant sur le comportement en régime nominal. En se concentrant sur les modèles de comportement systémique pendant les expériences d’ingénierie du Chaos, on vérifie que le système fonctionne, plutôt que d'essayer de valider *comment il fonctionne*.

### Multiplier les événements réels

Les variations d’événements Chaotiques permettent de refléter le monde réel. Il faut alors hiérarchiser les événements soit par impact potentiel ou fréquence estimée. Prenez en compte les événements qui correspondent à des défaillances matérielles telles que la mort des serveurs, les défaillances logicielles telles que les réponses mal formées et les événements sans échec tels qu'un pic de trafic ou un événement de mise à l'échelle. Tout événement capable de perturber l'état d'équilibre est une variable potentielle dans une expérience Chaos.

### Effectuer des expérimentations en Production

Les systèmes se comportent différemment selon l'environnement et les modèles de trafic. Comme le comportement d'utilisation peut changer à tout moment, l'échantillonnage du trafic réel est le seul moyen de capturer un modèle de requêtes de manière fiable. Pour garantir à la fois l'authenticité de la manière dont le système est utilisé et la pertinence par rapport au système déployé actuel, l’Ingénieur du Chaos préfère fortement expérimenter directement le trafic de production..

### Automatiser les expérimentations pour les lancer en continu

L’exécution des expériences manuellement nécessite beaucoup de main-d'œuvre et n'est finalement pas viable. Il est fortement recommandé d’automatiser les expériences pour pouvoir les exécuter en continu. L’Ingénierie du Chaos intègre l'automatisation dans le système pour piloter à la fois l'orchestration et l'analyse.

### Minimiser le rayon de l’explosion

L’Ingénierie du Chaos est une pratique puissante qui change déjà la façon dont les logiciels sont conçus et fabriqués dans le cadre de certaines des plus grandes opérations au monde. 

Là où d'autres pratiques traitent de la vitesse et de la flexibilité, le Chaos s'attaque spécifiquement à l'incertitude systémique des systèmes distribués. Les Principes du Chaos fournissent la confiance nécessaire pour innover rapidement à grande échelle et offrir aux clients un expériences avec le niveau de haute qualité qu'ils méritent.

Vous pouvez nous rejoindre pour échanger sur ces principes du Chaos et leur mise en application dans le groupe Google [Chaos Community](https://groups.google.com/forum/#!forum/chaos-community).
