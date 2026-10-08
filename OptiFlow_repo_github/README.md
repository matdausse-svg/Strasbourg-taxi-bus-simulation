# Simulation du réseau de taxis et de bus de Strasbourg / Strasbourg taxi and bus network simulation

Plant Simulation 2404 · SimTalk 2.0

[🇫🇷 Français](#-français) · [🇬🇧 English](#-english)

---

## 🇫🇷 Français

### Présentation
Code SimTalk d'un modèle de simulation à événements discrets du transport touristique de Strasbourg (taxis, TaxiVans et deux lignes de bus). Projet du cours « Plant Simulation, Digitalfabrik » (Hochschule München, semestre d'été 2026), réalisé en groupe de 4 dans le cadre d'un scénario fictif : le bureau d'ingénieurs OptiFlow GmbH est mandaté par la Mairie de Strasbourg pour réduire les temps d'attente des voyageurs.

**Les résultats viennent d'une simulation sur un scénario fictif, pas de mesures réelles.**

### Ce que contient le dépôt
Le dépôt contient le code des 46 méthodes du modèle, un fichier par méthode. **Le modèle Plant Simulation (.spp) n'est pas inclus.** Les commentaires du code sont en allemand.

| Dossier | Contenu |
|---|---|
| `src/01_init` | Initialisation, listes d'arrivées, création des véhicules |
| `src/02_arrivals` | Arrivées des voyageurs (aéroport, gare, gare routière) |
| `src/03_taxi` | Chargement, déchargement, choix de destination, appel de taxi |
| `src/04_bus` | Deux lignes de bus, correspondance à l'hôtel 2 |
| `src/05_groups` | Recherche et chargement des groupes |
| `src/06_traffic_lights` | Feux des 20 carrefours, priorité bus |
| `src/07_traveller_logic` | Scénarios de voyage, visites, retours |
| `src/08_tracking_kpi` | Suivi des voyageurs, mesure des temps d'attente |
| `src/09_parameters` | Vitesses |

### Fonctionnement en bref
- Arrivées irrégulières à 3 stations (gare, gare routière, aéroport), groupes de 1 à 6 personnes qui restent ensemble.
- Taxis (4 places) et TaxiVans (6 places) autonomes : ils choisissent leur prochaine station selon le nombre de voyageurs compatibles qui attendent.
- Appel de taxi automatique quand un voyageur attend trop longtemps.
- Deux lignes de bus avec correspondance automatique à l'hôtel 2.
- 20 carrefours à feux, avec priorité bus.
- Mesure du temps d'attente de chaque voyageur (minimum, moyenne, maximum).

### Situation initiale et situation améliorée
Le code publié correspond à la **situation améliorée**. La situation initiale s'en distingue par ces paramètres :

| Paramètre | Situation initiale | Situation améliorée |
|---|---|---|
| Flotte | 15 taxis + 15 TaxiVans | 30 taxis + 30 TaxiVans |
| Appel de taxi automatique | non | oui |
| Covoiturage (voyageurs au même trajet) | non | oui |
| Priorité bus aux feux | non | oui |
| Part des touristes en bus | 30 % | 70 % |

### Résultats (simulation, scénario fictif)
| | Situation initiale | Situation améliorée | Objectif de la ville |
|---|---|---|---|
| Attente moyenne | 2 h 26 | 5 min 8 s | 10 min |
| Attente maximale | 2 jours 8 h 38 | 1 h 50 | 20 min |

L'objectif de la moyenne est atteint, pas celui du maximum.

### Utilisation
Les fichiers sont du texte à copier dans les méthodes d'un modèle Plant Simulation 2404. Ils ne s'exécutent pas seuls.

### Remarques
- Code écrit à plusieurs : les méthodes s'appellent entre elles et ne sont pas attribuées individuellement.
- Le dépôt ne contient pas de données réelles.

---

## 🇬🇧 English

### Overview
SimTalk code of a discrete-event simulation model of tourist transport in Strasbourg (taxis, TaxiVans and two bus lines). Project of the course "Plant Simulation, Digitalfabrik" (Hochschule München, summer semester 2026), done in a group of 4 within a fictional scenario: the engineering firm OptiFlow GmbH is mandated by the City of Strasbourg to reduce travellers' waiting times.

**The results come from a simulation of a fictional scenario, not from real measurements.**

### What the repository contains
The repository holds the code of the model's 46 methods, one file per method. **The Plant Simulation model (.spp) is not included.** Code comments are in German.

| Folder | Content |
|---|---|
| `src/01_init` | Initialisation, arrival schedules, vehicle creation |
| `src/02_arrivals` | Traveller arrivals (airport, train station, bus station) |
| `src/03_taxi` | Loading, unloading, destination choice, taxi call |
| `src/04_bus` | Two bus lines, transfer at hotel 2 |
| `src/05_groups` | Group search and loading |
| `src/06_traffic_lights` | Lights at 20 junctions, bus priority |
| `src/07_traveller_logic` | Travel scenarios, visits, return trips |
| `src/08_tracking_kpi` | Traveller tracking, waiting-time measurement |
| `src/09_parameters` | Speeds |

### How it works
- Irregular arrivals at 3 stations (train station, bus station, airport), groups of 1 to 6 travellers who stay together.
- Autonomous taxis (4 seats) and TaxiVans (6 seats): each picks its next station based on the number of compatible travellers waiting.
- Automatic taxi call when a traveller has waited too long.
- Two bus lines with an automatic transfer at hotel 2.
- 20 signalised junctions, with bus priority.
- Waiting time measured for every traveller (minimum, average, maximum).

### Initial and improved situation
The published code is the **improved situation**. The initial situation differs by these parameters:

| Parameter | Initial situation | Improved situation |
|---|---|---|
| Fleet | 15 taxis + 15 TaxiVans | 30 taxis + 30 TaxiVans |
| Automatic taxi call | no | yes |
| Ride sharing (travellers on the same route) | no | yes |
| Bus priority at lights | no | yes |
| Share of tourists using the bus | 30% | 70% |

### Results (simulation, fictional scenario)
| | Initial situation | Improved situation | City target |
|---|---|---|---|
| Average wait | 2 h 26 min | 5 min 8 s | 10 min |
| Maximum wait | 2 days 8 h 38 min | 1 h 50 min | 20 min |

The average-wait target is met, the maximum-wait target is not.

### Usage
The files are plain text to paste into the methods of a Plant Simulation 2404 model. They do not run on their own.

### Notes
- Code written by several people: methods call each other and are not attributed individually.
- The repository contains no real data.
