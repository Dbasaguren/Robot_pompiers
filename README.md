# Projet de Simulation : Système de Robots Pompiers

## 1. Présentation du Projet
Ce projet consiste en la conception et l'implémentation d'un simulateur de robots pompiers. L'objectif est de modéliser une flotte de robots autonomes capables d'éteindre des incendies sur une carte de terrain hétérogène. Le système repose sur une architecture centralisée où un **Manager** distribue les tâches en optimisant les ressources disponibles.

## 2. Architecture et Conception UML
Le projet a été conçu selon les principes du Génie Logiciel, en s'appuyant sur les diagrammes suivants :

* **Diagramme de Cas d'Utilisation** : Définit les interactions entre l'utilisateur (configuration de la carte, ajout de robots) et le système (lancement et contrôle de la simulation).
* **Diagramme de Classes** : Structure les entités principales (Robot, Manager, Carte, Incendie, Position). Il utilise l'héritage pour les différents types de robots et les énumérations pour les types de terrain.
* **Diagramme de Séquence** : Détaille le protocole d'attribution des missions (enchères) entre le Manager et les Robots.
* **Diagramme d'États-Transitions** : Modélise le comportement interne d'un robot (Disponible, En déplacement, Extinction, Retour à la base).



## 3. Fonctionnalités Implémentées
* **Algorithme de Pathfinding** : Utilisation de l'algorithme de Dijkstra pour le calcul du chemin le plus court en tenant compte du coût spécifique de chaque terrain (Plat, Forêt, Montagne, Eau).
* **Gestion Multi-Agents** : Attribution dynamique des incendies aux robots les plus proches et les plus aptes via un système de coût.
* **Interface Graphique (GUI)** : Visualisation en temps réel de l'évolution des robots, des chemins calculés et de l'état des feux via Tkinter.
* **Animation Fluide** : Utilisation de l'interpolation pour les déplacements des robots entre deux cases de la grille.
* **Paramétrage du Temps** : Gestion d'une horloge interne avec fréquence modifiable pour accélérer ou ralentir la simulation.

## 4. Spécifications des Robots
Le système supporte trois types de robots aux caractéristiques distinctes :
* **Robot à chenilles** : Vitesse moyenne, réservoir haute capacité (100L), capable de franchir tous les terrains.
* **Robot à pattes** : Vitesse lente, capacité moyenne (70L), excellente mobilité en forêt et montagne.
* **Robot à roues** : Vitesse élevée, capacité limitée (50L), strictement restreint aux terrains plats.

## 5. Instructions d'Installation
### Prérequis
* Python 3.8 ou supérieur.
* Bibliothèque standard `tkinter` (généralement incluse par défaut).

### Lancement
1.  Cloner le dépôt :  
    `git clone [URL_DU_DEPOT]`
2.  Accéder au répertoire :  
    `cd [NOM_DU_DOSSIER]`
3.  Lancer l'application :  
    `python main.py`

## 6. Guide d'Utilisation
1.  **Configuration** : Utilisez le panneau de gauche pour ajouter des robots de différents types et des incendies sur la carte.
2.  **Simulation** : Cliquez sur le bouton **Démarrer** pour activer l'horloge.
3.  **Interactivité** : Vous pouvez modifier la vitesse de simulation en temps réel à l'aide du curseur.
4.  **Observation** : 
    * Les traits jaunes représentent les chemins calculés par les robots.
    * La couleur des robots change selon leur état (En route, Extinction, Retour base).
    * Le panneau **Statistiques** affiche les performances de chaque robot.

## 7. Structure du Code Source
* `Position` / `Carte` / `TerrainType` : Modélisation de l'environnement physique.
* `DijkstraPathfinder` : Logique algorithmique du plus court chemin.
* `Robot` : Gestion de l'état, de l'autonomie en eau et du déplacement.
* `Manager` : Intelligence centralisée pour l'affectation des missions.
* `FireSimulatorGUI` : Gestion du rendu graphique et des événements utilisateur.

