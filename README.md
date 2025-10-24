 # TP 5 : Héritage
 
 ## Exercice 1 : Hiérarchie de comptes bancaires
 
##  1. Objectif

Comprendre et mettre en œuvre l’héritage en Java à travers une hiérarchie concrète de classes : un compte bancaire de base (Compte), dont héritent deux types spécialisés (CompteEpargne et CompteCourant), chacun ajoutant son propre comportement.

## 2. Structure du projet

``` bash
TP5/
└─ src/
   └─ com.example.tp/
      ├ Compte.java
      ├ CompteEpargne.java
      ├ CompteCourant.java
      └ Main.java
```
 ## 3. Résultat attendu
 
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

 ##Exercice 2 : Héritage et gestion d’un zoo avec tableau dynamique d’animaux
 
##  1. Objectif

Concevoir en Java une hiérarchie de classes pour modéliser un zoo, en appliquant l’héritage (sans abstrait ni interface) et en gérant un tableau d’Animal qui s’agrandit dynamiquement.


 ## 3. Résultat attendu
 
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

TP5/
│
├── src/
   └── com/
       └── example/
           └── tp/
               ├── Animal.java
               ├── Mammifere.java
               ├── Oiseau.java
               ├── Reptile.java
               ├── Zoo.java
               └── Main.java













 
