 # TP 5 : Héritage
 
 ## Exercice 1 : Hiérarchie de comptes bancaires
 
##  1. Objectif

Comprendre et mettre en œuvre l’héritage en Java à travers une hiérarchie concrète de classes : un compte bancaire de base (Compte), dont héritent deux types spécialisés (CompteEpargne et CompteCourant), chacun ajoutant son propre comportement.

 ## 2. Résultat attendu
 
``` bash
Compte #1 — solde = 1000.0
Compte #1 : dépôt de 200.0
Compte #1 : retrait impossible (solde insuffisant)
Compte #1 — solde = 1200.0

CompteEpargne #2 — solde = 500.0, taux = 3.0%
CompteEpargne #2 : intérêts de 15.0
CompteEpargne #2 — solde = 515.0, taux = 3.0%
CompteEpargne #2 : retrait de 100.0
CompteEpargne #2 — solde = 415.0, taux = 3.0%

CompteCourant #3 — solde = 200.0, découvert autorisé = 300.0
CompteCourant #3 : retrait de 400.0
CompteCourant #3 — solde = -200.0, découvert autorisé = 300.0
CompteCourant #3 : retrait impossible (découvert max dépassé)
CompteCourant #3 — solde = -200.0, découvert autorisé = 300.0

CompteEpargne #4 — solde = 100.0, taux = 5.0%

```
---

 ## Exercice 2 : Héritage et gestion d’un zoo avec tableau dynamique d’animaux
 
##  1. Objectif

Concevoir en Java une hiérarchie de classes pour modéliser un zoo, en appliquant l’héritage (sans abstrait ni interface) et en gérant un tableau d’`Animal` qui s’agrandit dynamiquement.


 ## 2. Résultat attendu
 
``` bash
Le zoo contient 6 animaux :
  - Animal[id=1, nom=Lion, age=5] {Mammifere, fourrure=Dorée}
  - Animal[id=2, nom=Aigle, age=3] {Oiseau, envergure=2.3}
  - Animal[id=3, nom=Crocodile, age=12] {Reptile, écailles=Épaisse}
  - Animal[id=4, nom=Girafe, age=7] {Mammifere, fourrure=Tachetée}
  - Animal[id=5, nom=Perroquet, age=2] {Oiseau, envergure=0.4}
  - Animal[id=6, nom=Serpent, age=4] {Reptile, écailles=Lisse}

Éléphant allaite ses petits.
Autruche s'envole avec une envergure de 1.8 m.

```



## Exercice 3 : Parc de véhicules – Héritage, composition et gestion de flotte

### 1. Objectif
- Modéliser un parc de véhicules en Java.
- Utiliser une hiérarchie multi-niveaux : `Vehicule → Motorise → Voiture, Camion, Moto, VoitureElectrique`.
- Utiliser la composition via la classe `Moteur`.
- Gérer le carburant ou la batterie sans lever d’exceptions.
- Créer une classe `Flotte` qui stocke dynamiquement les véhicules et calcule des statistiques.

## Exemple de sortie attendue

``` bash

Flotte (4 véhicules) :
  • Vehicule#1 [Clio] {Essence 75ch, carburant=50.0} {Voiture, portes=5}
  • Vehicule#2 [Volvo] {Diesel 400ch, carburant=200.0} {Camion, cap=20.0 t}
  • Vehicule#3 [Harley] {Essence 90ch, carburant=20.0} {Moto, cylindrée=1200.0 cm³}
  • Vehicule#4 [Tesla] {Élec 300ch, batterie=85.0} {Electrique}

Clio démarre avec 50.0 unités et moteur Essence 75ch
Clio a roulé 100.0 km, reste 40.0 unités
Clio ravitaillé de 20.0 unités (nouveau niveau : 60.0)
Clio a roulé 300.0 km, reste 30.0 unités

Tesla démarre avec 85.0 unités et moteur Élec 300ch
Tesla a roulé 200.0 km, reste 65.0 unités
Tesla recharge 50.0 kWh (niveau=115.0)
Tesla a roulé 300.0 km, reste 85.0 unités

Distance totale parcourue : 900.0 km

```



## Exercice 4 : Gestion d'une Bibliothèque

### 1. Objectif
- Développer un système de gestion d’une bibliothèque en Java.
- Utiliser l’encapsulation et l’auto-incrémentation pour les numéros d’enregistrement.
- Gérer une collection dynamique de documents.
- Fournir des opérations de base : ajouter, supprimer, afficher, rechercher, lister les auteurs.

---
 
### 3. Description des classes

#### 3.1 `Document.java`
- Classe de base pour tous les documents.
- Attributs : `numEnreg` (auto-incrément), `titre`.
- Méthodes : `getNumEnreg()`, `getTitre()`, `toString()`.

#### 3.2 `Livre.java` (extends `Document`)
- Attributs supplémentaires : `auteur`, `nbPages`.
- Méthodes : getter/setter et `toString()` redéfini.

#### 3.3 `ReferenceBook.java` (extends `Livre`)
- Attribut supplémentaire : `domaine`.
- Méthodes : getter/setter et `toString()` redéfini.

#### 3.4 `Bibliotheque.java`
- Attribut : tableau `Document[] documents`, compteur `nbDocuments`.
- Méthodes :
  - `Bibliotheque(int capacite)` – constructeur.
  - `boolean ajouter(Document doc)` – ajoute un document.
  - `boolean supprimer(Document doc)` – supprime un document.
  - `Document document(int numEnrg)` – recherche par numéro.
  - `void afficherDocuments()` – affiche tous les documents.
  - `void afficherAuteurs()` – affiche tous les auteurs présents.

#### 3.5 `Main.java` (dans package `test`)
- Lit le nombre de documents à créer depuis le clavier.
- Initialise la bibliothèque avec deux documents.
- Affiche un menu permettant :
   - Ajouter un document
   - Supprimer un document
   -Afficher tous les documents
   -Rechercher un document par numéro
   - Afficher les auteurs
   -Quitter


---

### 4. Exemple d’exécution

``` bash
Donnez la capacité de la bibliothèque : 5

--- Menu ---
1. Ajouter un document
2. Supprimer un document
3. Afficher tous les documents
4. Rechercher un document par numéro
5. Afficher les auteurs
0. Quitter
Votre choix : 3
Livre [numEnreg=1, titre=Le Petit Prince, auteur=Saint-Exupéry, nbPages=96]
Dictionnaire [numEnreg=2, titre=Larousse, langue=Français]

--- Menu ---
1. Ajouter un document
2. Supprimer un document
3. Afficher tous les documents
4. Rechercher un document par numéro
5. Afficher les auteurs
0. Quitter
Votre choix : 1
Type de document (1: Livre / 2: Dictionnaire): 1
Titre : les miserable
Auteur : Victor Hugo
Nombre de pages : 1488

--- Menu ---
1. Ajouter un document
2. Supprimer un document
3. Afficher tous les documents
4. Rechercher un document par numéro
5. Afficher les auteurs
0. Quitter
Votre choix : 3
Livre [numEnreg=1, titre=Le Petit Prince, auteur=Saint-Exupéry, nbPages=96]
Dictionnaire [numEnreg=2, titre=Larousse, langue=Français]
Livre [numEnreg=3, titre=les miserable, auteur=Victor Hugo, nbPages=1488]

--- Menu ---
1. Ajouter un document
2. Supprimer un document
3. Afficher tous les documents
4. Rechercher un document par numéro
5. Afficher les auteurs
0. Quitter
Votre choix : 4
Numéro d’enregistrement : 2
Dictionnaire [numEnreg=2, titre=Larousse, langue=Français]

--- Menu ---
1. Ajouter un document
2. Supprimer un document
3. Afficher tous les documents
4. Rechercher un document par numéro
5. Afficher les auteurs
0. Quitter
Votre choix : 5
Auteurs présents dans la bibliothèque :
- Saint-Exupéry
- Victor Hugo

--- Menu ---
1. Ajouter un document
2. Supprimer un document
3. Afficher tous les documents
4. Rechercher un document par numéro
5. Afficher les auteurs
0. Quitter
Votre choix : 2
Numéro du document à supprimer : 1
Document supprimé !

--- Menu ---
1. Ajouter un document
2. Supprimer un document
3. Afficher tous les documents
4. Rechercher un document par numéro
5. Afficher les auteurs
0. Quitter
Votre choix : 3
Dictionnaire [numEnreg=2, titre=Larousse, langue=Français]
Livre [numEnreg=3, titre=les miserable, auteur=Victor Hugo, nbPages=1488]

--- Menu ---
1. Ajouter un document
2. Supprimer un document
3. Afficher tous les documents
4. Rechercher un document par numéro
5. Afficher les auteurs
0. Quitter
Votre choix : 0
Au revoir !

```




 
