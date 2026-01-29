# Algorithmes sur les graphes en Python

Ce dépôt contient des **implémentations et expériences sur les algorithmes de graphes** en Python.  
Il est conçu pour être **pédagogique, modulaire et reproductible**.

Le projet couvre la génération de graphes, les algorithmes de plus court chemin, les parcours de graphes, la visualisation et les études expérimentales sur la performance des algorithmes et la connexité des graphes.

---

## Fonctionnalités

### Génération de graphes
- Graphes aléatoires pondérés avec matrices d’adjacence
- Graphes créés selon une probabilité de présence d’arêtes
- Support pour les poids infinis représentant les arêtes absentes

### Algorithmes de plus court chemin
- **Dijkstra** : plus courts chemins sur graphes pondérés sans cycles négatifs
- **Bellman-Ford** : plus courts chemins avec détection des cycles négatifs
- Gestion des prédécesseurs et reconstruction des chemins

### Parcours de graphes
- **DFS (Parcours en profondeur)**
- **BFS (Parcours en largeur)**
- Conversion des parcours en listes d’arêtes pour utilisation dans les algorithmes

### Visualisation
- Visualisation générique de graphes avec **NetworkX** et **Matplotlib**
- Mise en évidence des chemins les plus courts en rouge et des sommets visités en bleu
- Disposition automatique des nœuds avec spring layout

### Expériences et analyses
- Comparaison des **temps d’exécution** : Dijkstra vs Bellman-Ford
- Étude de l’effet de **l’ordre de parcours des arêtes** sur Bellman-Ford
- Analyse statistique de la **forte connexité** des graphes aléatoires
- Calcul du **seuil de forte connexité** en fonction de la taille des graphes
- Régression log-log pour étudier le comportement en complexité

---

## Structure du dépôt

```text
graph-algorithms/
│
├── graph_generation.py          # Fonctions de génération de graphes
├── graph_algorithms.py          # Algorithmes principaux (Dijkstra, Bellman-Ford, DFS, BFS)
├── graph_visualization.py       # Fonctions de visualisation générique
│
├── experiments/
│   ├── dijkstra_visualization.py             # Démonstration visuelle de Dijkstra
│   ├── bellman_ford_experiments.py          # Expériences sur l’ordre des arêtes pour Bellman-Ford
│   ├── benchmark_dijkstra_bellman_ford.py   # Comparaison des temps d’exécution
│   └── strong_connectivity_threshold.py     # Étude statistique de la forte connexité
│
├── requirements.txt
└── README.md
```
---

# Installation

Cloner le dépôt :

```bash
git clone https://github.com/votre-utilisateur/graph-algorithms.git
cd graph-algorithms
```
---
## Installer les packages requis :

```bash
pip install -r requirements.txt
```
---
## Utilisation

### Utilisation des algorithmes principaux

Importer les fonctions depuis graph_algorithms.py :

```bash
from graph_algorithms import dijkstra, Bellman_Ford, pp, pl

# Exemple : plus courts chemins avec Dijkstra
graph = [[0, 2, 0], [0, 0, 3], [1, 0, 0]]
distances, chemins, visites = dijkstra(graph, 0)
print("Distances :", distances)
print("Chemins :", chemins)
```

## Visualisation de graphes

Utiliser graph_visualization.py :

```bash
from graph_visualization import afficher_graphe

# Affichage d’un graphe et mise en évidence d’un chemin
afficher_graphe(graph, chemins[2], visites)
```
---

## Exécuter les expériences

Tous les scripts dans experiments/ peuvent être exécutés directement :

```bash
python experiments/dijkstra_visualization.py
python experiments/bellman_ford_experiments.py
python experiments/benchmark_dijkstra_bellman_ford.py
python experiments/strong_connectivity_threshold.py
```
---

## Notes

 - Les graphes sont représentés sous forme de matrices d’adjacence.

 - Les arêtes absentes sont représentées par float('inf').
 
 - Les expériences sont aléatoires, donc les résultats peuvent varier légèrement.

 - La structure du dépôt est conçue pour être pédagogique et reproductible.

---
# Licence
```bash
Ce projet est destiné à des fins pédagogiques.
Vous pouvez explorer, modifier et adapter librement pour votre apprentissage.
```
