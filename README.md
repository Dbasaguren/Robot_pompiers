Projet de Simulation : Système de Robots Pompiers
1. Présentation du Projet
Ce projet consiste en la conception et l'implémentation d'un simulateur de robots pompiers. L'objectif est de modéliser une flotte de robots autonomes capables d'éteindre des incendies sur une carte de terrain hétérogène. Le système repose sur une architecture centralisée où un Manager distribue les tâches en optimisant les ressources disponibles.

2. Architecture et Conception UML
Le projet a été conçu selon les principes du Génie Logiciel, en s'appuyant sur les diagrammes suivants :

Diagramme de Cas d'Utilisation : Définit les interactions entre l'utilisateur (configuration de la carte, ajout de robots) et le système (lancement et contrôle de la simulation).

Diagramme de Classes : Structure les entités principales (Robot, Manager, Carte, Incendie, Position). Il utilise l'héritage pour les différents types de robots et les énumérations pour les types de terrain.

Diagramme de Séquence : Détaille le protocole d'attribution des missions (enchères) entre le Manager et les Robots.

Diagramme d'États-Transitions : Modélise le comportement interne d'un robot (Disponible, En déplacement, Extinction, Retour à la base).

3. Fonctionnalités Implémentées
Algorithme de Pathfinding : Utilisation de l'algorithme de Dijkstra pour le calcul du chemin le plus court en tenant compte du coût spécifique de chaque terrain (Plat, Forêt, Montagne, Eau).

Gestion Multi-Agents : Attribution dynamique des incendies aux robots les plus proches et les plus aptes.

Interface Graphique (GUI) : Visualisation temps réel de l'évolution des robots et de l'extinction des feux via une interface développée sous Tkinter.

Paramétrage du Temps : Contrôle de la vitesse de simulation et gestion de l'horloge interne (ticks).

4. Spécifications des Robots
Le système supporte trois types de robots aux caractéristiques distinctes :

Robot à chenilles : Vitesse moyenne, réservoir haute capacité, tout terrain.

Robot à pattes : Vitesse lente, capacité moyenne, excellente mobilité en montagne.

Robot à roues : Vitesse élevée, capacité limitée, restreint aux terrains plats.

5. Instructions d'Installation
Prérequis
Python 3.8 ou supérieur.

Bibliothèque standard Tkinter (généralement incluse avec Python).

Lancement
Cloner le dépôt : git clone [URL_DU_DEPOT]

Naviguer dans le dossier : cd [NOM_DU_DOSSIER]

Exécuter le programme principal : python main.py

6. Utilisation du Simulateur
Utiliser les boutons "Ajouter Robot" et "Ajouter Incendie" pour configurer la scène.

Cliquer sur "Démarrer" pour lancer le cycle de l'horloge.

Ajuster le curseur de vitesse pour observer les comportements de déplacement et d'extinction.

Consulter le panneau latéral pour les statistiques en temps réel (nombre de feux éteints, niveau d'eau).

7. Structure du Code
Position / Carte : Gestion de la grille et de la topographie.

DijkstraPathfinder : Logique de calcul d'itinéraire.

Robot : Machine à états et gestion de l'autonomie.

Manager : Stratégie d'allocation des ressources.

FireSimulatorGUI : Moteur de rendu graphique.
