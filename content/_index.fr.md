+++
title = "LES PRINCIPES DE L'INGÉNIERIE DU CHAOS"
date = 2020-01-28T16:25:57+02:00
draft = false
+++

# LES PRINCIPES DE L'INGÉNIERIE DU CHAOS
Mise à jour : Mai 2025

*L'Ingénierie du Chaos est une discipline qui consiste à expérimenter la capacité d'un système informatique à résister à des conditions turbulentes en environnement de production afin de renforcer la confiance en ce système.*

---

## I. Introduction

Les progrès dans les systèmes logiciels distribués à grande échelle changent drastiquement l'ingénierie logicielle. En tant qu'industrie, nous adoptons rapidement des pratiques qui augmentent la flexibilité de développement et la rapidité de déploiement. Une question urgente émerge alors de ces évolutions : Quelle confiance pouvons-nous avoir dans les systèmes complexes que nous mettons en production ?

Même lorsque chacun des services d'un ensemble logiciel fonctionne individuellement correctement, les interactions entre ces services peuvent entraîner des résultats imprévisibles. Ces résultats imprévisibles, aggravés par des événements rares mais perturbateurs du monde réel qui affectent les environnements de production, rendent ces systèmes logiciels distribués intrinsèquement chaotiques.

Nous devons identifier les faiblesses avant qu'elles ne se manifestent dans des comportements aberrants à l'échelle du système. Les faiblesses systémiques peuvent prendre la forme de : paramètres de "fallback" inadéquats lorsqu'un service est indisponible ; tentative de reprise avec effets cataclysmiques à la suite de "timeouts" incorrectement réglés ; pannes lorsqu'une dépendance en aval reçoit trop de trafic ; échecs en cascade à la suite de la défaillance d'un seul point, etc. Nous devons aborder les faiblesses les plus significatives de manière proactive, avant qu'elles n'affectent nos clients en production. Nous avons besoin d'un moyen de gérer le chaos inhérent à ces systèmes, de tirer parti de cette flexibilité forte et de cette accélération croissante, et de faire confiance à nos déploiements en production malgré la complexité qu'ils représentent.

Une approche empirique aborde le chaos dans ces systèmes et renforce la confiance en la capacité de ces systèmes à résister aux conditions de production du monde réel. Nous apprenons le comportement d'un système en l'observant lors d'une expérience contrôlée. Nous appelons cela *l'Ingénierie du Chaos*.

---

## II. L'Ingénierie du Chaos, en pratique

Pour répondre spécifiquement à l'incertitude de nos systèmes logiciels distribués, l'Ingénierie du Chaos peut être considérée comme un moyen facile d’expérimenter pour découvrir les faiblesses de ces derniers. Ces expériences suivent quatre étapes :

1. Définir l'état « stable », comme une sortie ou une donnée mesurable, d'un système qui agit avec un comportement nominal.
2. Faire l’hypothèse que cet état stable se poursuivra dans le groupe témoin et dans le groupe expérimental.
3. Introduire des variations qui reflètent des événements réels, tels que des serveurs en panne, des disques durs défectueux, des connexions réseau coupées, etc.
4. Tenter de réfuter l'hypothèse en recherchant une différence d'état entre le groupe témoin et le groupe expérimental.

Plus il est difficile de perturber l'état stable d'un système, plus nous avons confiance en le comportement de ce dit système. Si une faiblesse est découverte, nous avons maintenant un objectif d'amélioration pour éviter que ce comportement ne se manifeste un jour dans un environnement non contrôlé.

---

## III. Application idéale

Les étapes suivantes décrivent un exemple d'application idéale du principe d'Ingénierie du Chaos, en appliquant le processus d'expérimentation décrit ci-dessus. Le degré d'approfondissement de ces principes est fortement corrélé à la confiance que nous pouvons avoir en un système logiciel.

### 1. Définir notre « État Stable »

Il est préférable de se concentrer sur la sortie mesurable d'un système plutôt que sur les attributs internes du système. Il faut ensuite effectuer ces mesures sur une courte période afin de définir les valeurs constituant l'état stable du système. Le débit global du système, les taux d'erreur, les percentiles de latence, etc. sont tous des indicateurs intéressants sur le comportement d'un système en fonctionnement nominal. En se concentrant sur les modèles de comportement systémique pendant les expériences, on vérifie que le système fonctionne, plutôt que d'essayer de valider *comment il fonctionne*.

### 2. Varier les événements réels

Les variations d'événements chaotiques permettent de refléter le monde réel. Il faut alors hiérarchiser les événements soit par impact potentiel, soit par fréquence estimée. Prenez en compte les événements qui correspondent à des défaillances matérielles telles que la casse des serveurs, des défaillances logicielles telles que les réponses mal formées ou des événements qui n'entraînent pas d'échec tels qu'un pic de trafic ou un événement de mise à l'échelle du système. Tout événement capable de perturber l'état stable de notre système est une variable potentielle dans une expérience d'Ingénierie du Chaos.

### 3. Effectuer des expérimentations en environnement de production

Les systèmes se comportent différemment selon l'environnement et les modèles de trafic. Comme le comportement d'utilisation peut changer à tout moment, l'échantillonnage du trafic réel en condition de production est le seul moyen de capturer un modèle de requêtes de manière fiable. Pour garantir à la fois l'authenticité de la manière dont le système est utilisé et la pertinence par rapport au système déployé actuel, nous préférons fortement expérimenter directement sur le trafic en environnement de production.

### 4. Automatiser les expérimentations pour des essais continus

L’exécution manuelle des expériences nécessite beaucoup de main-d'œuvre et n'est finalement pas viable. Il est fortement recommandé d’automatiser les expériences pour pouvoir les exécuter en continu. L’Ingénierie du Chaos intègre l'automatisation dans le système pour piloter à la fois l'orchestration et l'analyse.

### 5. Minimiser le rayon d'impact des expériences

Les expérimentations en production peuvent engendrer des difficultés inutiles pour les clients. Bien qu'il faille prévoir un impact négatif à court terme, il est de notre responsabilité et de notre obligation de veiller à ce que les retombées des expérimentations soient minimisées, contenues et encadrées.

---

## IV. Conclusion

L'Ingénierie du Chaos est une pratique puissante qui impacte déjà la façon dont les logiciels sont conçus et fabriqués dans le cadre de certaines des plus grandes opérations au monde. Là où d'autres pratiques traitent de la vitesse et de la flexibilité, l'Ingénierie du Chaos s'attaque spécifiquement à l'incertitude systémique des systèmes logiciels distribués à grande échelle. Ces principes fournissent la confiance nécessaire pour innover rapidement à grande échelle et offrir aux clients une expérience de haute qualité continue qu'ils méritent.

---

## V. Informations utiles

- Vous pouvez nous rejoindre pour échanger sur ces principes de l'Ingénierie du Chaos et leur mise en application dans le groupe Google [Chaos Community](https://groups.google.com/forum/#!forum/chaos-community).
- Vous pouvez contribuer à la traduction de cette page via [Github](https://github.com/chaos-eng/chaos-eng.github.io).
