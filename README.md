Proposition d'un système distribué de contrôle de trafic

Traffic-adaptative control : évalue un ensemble de décision de contrôle réalisable

look-ahead += capable de déterminer la décision optimale sur la base d'une analyse de long-terme

Vue sur un temps déterminé

Décide à chaque étape d'initier ou de terminer un état "vert" (ou de continuer)
Problème d'optimisation d'arbre de décision (NP-difficile)

## Block-based Traffic Signal control

Mouvement : flux de véhicule "vert <-> rouge"

L'approche par *block* permet de diminuer l'arbre de décision par rapport à l'approche *Stage*

# Multi-Agent approach
## Système multi-Agent
Ne marche que si le problème peut être subdivisé en sous-problèmes faiblement couplés
De cette manière, la compositions des solutions locales s'approchera de la solution globale

Agent : Acteur intelligent qui interagit avec son environnement via des capteurs et des actuateurs.

Défi : Pouvoir rendre les instruments, qui opéraient jusque-là purement localement, plus sensibles aux intérêt des voisins.

Le système proposé est un algorithme amélioré qui prend en compte le trafic aval et amont

## Procédure de coordination

Objectif : coordonner les feux pour permettre une progression la plus fluide (avec le moins d'arrêts) de pelotons de véhicules.
L'efficacité de ce genre de schéma dépend du ratio de pelotons dans l'ensemble du flux de circulation.

Platoon ratio = fraction du trafic d'une artère qui voyage de la première à la dernière intersection.

La performance dépend aussi du trafic sur les mvts mineurs.
1. Le volume de trafic sur les rues secondaires change le platoon ratio
2. Un faible volume de mvts mineurs permet au feu de donner plus temps *vert* aux mouvements coordonnés

Pour atteindre une meilleure flexibilité, le feux doit être conscient des actions des agents avals et amonts sur ses performances et des effets de ses actions sur les agents en aval et en amont.

### Fonctionnement :

**État initial :** Aucune information n'est disponible des agents voisins

Avec l'arrivée des informations, le plan de signalisation est mis à jours petit à petit.
À chaque étape temporelle (de plusieurs secondes à une minute), un contrôle optimal est déterminé pour un certain horizon de prédiction (typiquement plusieurs minutes).

À chaque itération, chaque agent détermine son état actuel sur la base des informations reçues de ses détecteurs et des données reçues des agents amonts et avals. Ensuite, chaque agent essaie d'optimiser sa
