# M1-TP-RSD-2025-2026

## TP N°2 : Analyse et comparaison des algorithmes de recherche et de détermination du maximum et minimum

**Module** : Algorithmique Avancée et Complexité - Master 1 (IL & RSD)
**Université** : USTHB - Faculté d'Électronique et d'Informatique
**Année** : 2025-2026

**Machine utilisée pour les tests :**

* **Processeur** : 13th Gen Intel(R) Core(TM) i5-13420H @ 2.10 GHz
* **RAM installée** : 8.00 GB (7.70 GB utilisable)
* **Type de système** : 64-bit, processeur x64

---

## Table des matières

1. [Description](#description)
2. [Fonctionnalités](#fonctionnalités)
3. [Liste testée](#liste-testée)
4. [Compilation et exécution](#compilation-et-exécution)
5. [Mesure des performances](#mesure-des-performances)
6. [Exemples de données](#exemples-de-données)
7. [Graphiques](#graphiques)
8. [Détails algorithmiques](#détails-algorithmiques)
9. [Rôles et contributions](#rôles-et-contributions)

---

## Description

Ce TP a pour objectif d'analyser et de comparer plusieurs algorithmes de recherche de minimum et maximum dans des tableaux d'entiers :

* **Recherche non triée (Naïf)**
* **Recherche triée**
* **Recherche dichotomique**
* **Algorithmes MaxEtMinA et MaxEtMinB**

Les tests ont été réalisés pour différentes tailles de tableaux, en mesurant **le temps d’exécution** et **le nombre de comparaisons**. Les données ont été **générées par le programme et stockées dans des fichiers texte**, puis lues dans des tables pour analyse. L'objectif est de visualiser l'impact de l'organisation des données et l'efficacité des optimisations algorithmiques.

---

## Fonctionnalités

* Parcours complet des tableaux pour les recherches naïves.
* Exploitation de l’ordre pour les recherches triées.
* Division récursive pour les recherches dichotomiques.
* Comparaison de deux stratégies de calcul du max et min (A et B).
* Collecte et stockage des **temps et comparaisons** dans des fichiers : `tp2pt1.txt` et `tp2pt2.txt`.
* Graphiques réalisés à partir de ces fichiers en utilisant **Excel**.

---

## Liste testée

**Tailles de tableaux utilisées :**

```c
int sizes[] = {100000, 200000, 300000, 400000, 500000, 600000, 700000, 800000, 900000,
               1000000, 1100000, 1200000, 1300000, 1400000, 1500000, 1600000, 1700000,
               1800000, 2000000, 4000000, 6000000, 8000000};
```

---

## Compilation et exécution

Pour compiler le programme sous Linux :

```bash
gcc -o tp2 tp2.c -O2
./tp2
```

* `-O2` active l’optimisation du compilateur pour des mesures plus réalistes.
* L'exécution produit les fichiers de sortie pour les temps et comparaisons.

---

## Mesure des performances

* **Temps** : en secondes (avec `clock()` ou chronomètre haute précision).
* **Comparaisons** : nombre de comparaisons réalisées par l’algorithme.
* Résultats **stockés dans des fichiers** et importés dans **Excel** pour génération des tableaux et graphiques.

---

## Exemples de données

### TP2 Partie 1 : Naïf / Trié / Dichotomie (best et worst cases)

| N       | Naïf + (s) | Naïf − (s) | Trié + (s) | Trié − (s) | Dicho + (s) | Dicho − (s) |
| ------- | ---------- | ---------- | ---------- | ---------- | ----------- | ----------- |
| 100000  | 0.000000   | 0.000174   | 0.000000   | 0.000187   | 0.000001    | 0.000001    |
| 200000  | 0.000000   | 0.000230   | 0.000000   | 0.000414   | 0.000001    | 0.000001    |
| 400000  | 0.000000   | 0.000518   | 0.000000   | 0.000961   | 0.000001    | 0.000000    |
| 600000  | 0.000001   | 0.000739   | 0.000000   | 0.001251   | 0.000001    | 0.000001    |
| 800000  | 0.000000   | 0.001434   | 0.000000   | 0.002169   | 0.000000    | 0.000001    |
| 1000000 | 0.000001   | 0.002234   | 0.000001   | 0.002718   | 0.000001    | 0.000001    |
| 2000000 | 0.000001   | 0.002827   | 0.000001   | 0.004550   | 0.000001    | 0.000001    |
| 4000000 | 0.000001   | 0.005915   | 0.000000   | 0.007500   | 0.000001    | 0.000001    |
| 6000000 | 0.000000   | 0.009176   | 0.000000   | 0.010153   | 0.000001    | 0.000001    |
| 8000000 | 0.000000   | 0.011319   | 0.000000   | 0.014508   | 0.000001    | 0.000001    |

### TP2 Partie 2 : MaxEtMinA vs MaxEtMinB

| N       | Comparaisons A | Comparaisons B | Temps A (s) | Temps B (s) |
| ------- | -------------- | -------------- | ----------- | ----------- |
| 100000  | 199998         | 149998         | 0.000120    | 0.000332    |
| 200000  | 399998         | 299998         | 0.000234    | 0.000699    |
| 300000  | 599998         | 449998         | 0.000603    | 0.001215    |
| 400000  | 799998         | 599998         | 0.000469    | 0.001327    |
| 500000  | 999998         | 749998         | 0.000584    | 0.001929    |
| 600000  | 1199998        | 899998         | 0.000851    | 0.002356    |
| 700000  | 1399998        | 1049998        | 0.000933    | 0.002330    |
| 800000  | 1599998        | 1199998        | 0.001311    | 0.003090    |
| 900000  | 1799998        | 1349998        | 0.001329    | 0.003404    |
| 1000000 | 1999998        | 1499998        | 0.001167    | 0.003748    |
| 2000000 | 3999998        | 2999998        | 0.002863    | 0.006940    |
| 4000000 | 7999998        | 5999998        | 0.005816    | 0.013533    |
| 6000000 | 11999998       | 8999998        | 0.010562    | 0.020386    |
| 8000000 | 15999998       | 11999998       | 0.010600    | 0.027189    |

---

## Graphiques

**Ordre des graphiques réalisés dans Excel :**

1. **Triés : Worst vs Best cases**
   Visualisation des temps pour Trié + et Trié − en comparant le meilleur et le pire cas.
   <img width="592" height="354" alt="Screenshot 2025-11-23 201734" src="https://github.com/user-attachments/assets/2252fcb5-787d-4838-9aba-5e4dba9a2796" />


3. **Non triés : Worst vs Best cases**
   Visualisation des temps pour Naïf + et Naïf − pour comparer meilleur et pire cas.
   <img width="596" height="356" alt="Screenshot 2025-11-23 202136" src="https://github.com/user-attachments/assets/65782053-9e25-4c76-b8cc-9f74bb718083" />


5. **Dichotomie : Worst vs Best cases**
   Visualisation des temps pour Dicho + et Dicho −.
   <img width="595" height="355" alt="Screenshot 2025-11-23 202412" src="https://github.com/user-attachments/assets/4caf5890-b75d-4cf1-b3ac-1254a9bd7c9c" />


7. **Comparaison globale Worst cases**
   Tous les algorithmes ensemble (Naïf, Trié, Dicho) pour le pire cas.
   <img width="598" height="358" alt="Screenshot 2025-11-23 202633" src="https://github.com/user-attachments/assets/8b3b82dc-6388-4372-81c7-7ecb4d5905ec" />


9. **Comparaison globale Best cases**
   Tous les algorithmes ensemble pour le meilleur cas.
   <img width="600" height="356" alt="Screenshot 2025-11-23 202826" src="https://github.com/user-attachments/assets/ba04bd6c-58d1-4b3f-9be9-8b882998dcee" />


11. **MaxEtMin Comparaisons A vs B**
   Visualisation du nombre de comparaisons pour MaxEtMinA et MaxEtMinB.
   <img width="596" height="350" alt="Screenshot 2025-11-23 203908" src="https://github.com/user-attachments/assets/eb58a1a2-7e8e-41ea-97b2-55a675ef65fa" />


13. **MaxEtMin Temps A vs B**
   Visualisation du temps d’exécution pour MaxEtMinA et MaxEtMinB.
   <img width="592" height="346" alt="Screenshot 2025-11-23 204034" src="https://github.com/user-attachments/assets/31d4bf3f-dae7-4b9c-b3d0-c7a8425d2b1c" />


*Les axes :*

* X → Taille du tableau (N)
* Y → Temps (s) ou Comparaisons
* Les graphes permettent de visualiser la **croissance temporelle et le nombre de comparaisons** pour chaque algorithme.

---

## Détails algorithmiques

### Algorithmes Naïf

* Parcourt tout le tableau, retourne min et max.
* Comparaisons : N-1 pour min et N-1 pour max.

### Algorithmes Triés

* Exploite l'ordre croissant pour limiter les comparaisons.

### Algorithme Dichotomique

* Recherche récursive en divisant le tableau pour limiter le nombre de comparaisons.

### MaxEtMinA vs MaxEtMinB

* MaxEtMinB optimise le nombre de comparaisons en traitant les paires d’éléments.

---

## Rôles et Contributions

* **Code et développement** : ABDERRAHIM Sidali 222231402319
* **Rédaction du rapport** : BELDJERDI Tayeb Yasser 222231404112
* **Tests et évaluations** : GACEM Abdenour 222231640608
* **Collecte des données** : DALIL Faycal 222231658510

---

**Fin du rapport**
