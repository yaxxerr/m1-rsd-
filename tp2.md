# M1-TP-RSD-2025-2026

## TP N°2 : Analyse et comparaison des algorithmes de recherche et de détermination du maximum et minimum

**Module** : Algorithmique Avancée et Complexité - Master 1 (IL & RSD)
**Université** : USTHB - Faculté d'Électronique et d'Informatique
**Année** : 2025-2026

---

## Table des matières

1. [Description](#description)
2. [Fonctionnalités](#fonctionnalités)
3. [Liste testée](#liste-testée)
4. [Mesure des performances](#mesure-des-performances)
5. [Exemples de données](#exemples-de-données)
6. [Graphiques](#graphiques)
7. [Détails algorithmiques](#détails-algorithmiques)
8. [Rôles et contributions](#rôles-et-contributions)

---

## Description

Ce TP vise à comparer différents algorithmes de recherche et de détermination des valeurs maximale et minimale dans un tableau d'entiers. L'objectif est d'illustrer l'impact de l'organisation des données (non trié, trié, dichotomie) et d'optimiser la recherche de maximum et minimum (deux algorithmes : MaxEtMinA et MaxEtMinB).

Le programme mesure le temps d'exécution et le nombre de comparaisons pour chaque méthode sur plusieurs tailles de tableaux. L'analyse des résultats permet de mettre en évidence les gains liés à l'optimisation et à la structure des données.

---

## Fonctionnalités

* **Recherche non triée** : Parcourt le tableau sans aucun ordre.
* **Recherche triée** : Exploite l'ordre croissant du tableau pour réduire les comparaisons.
* **Recherche dichotomique** : Utilise une approche type dichotomie pour réduire considérablement le nombre de comparaisons sur des données triées.
* **Algorithmes MaxEtMin** : Deux variantes comparées pour la détermination simultanée du maximum et du minimum.
* **Mesure du temps et des comparaisons** pour toutes les méthodes.

---

## Liste testée

Pour l'analyse empirique, nous avons utilisé des tableaux de tailles différentes pour observer la variation des temps et comparaisons :

**Tailles utilisées :**
`int sizes[] = {100000, 200000, 400000, 600000, 800000, 1000000, 1200000, 1400000, 1600000, 1800000};`

---

## Mesure des performances

* Temps mesuré en **secondes** avec `clock()` ou un chronomètre haute précision.
* Nombre de comparaisons comptabilisé pour chaque algorithme.
* Comparaisons effectuées pour toutes les tailles de tableaux définies.
* Résultats enregistrés dans deux fichiers :

  * `tp2pt1.txt` : temps pour recherche Naïf, Trié et Dichotomique.
  * `tp2pt2.txt` : comparaisons et temps pour MaxEtMinA et MaxEtMinB.

---

## Exemples de données

### TP2 Partie 1 : Recherche Naïf / Trié / Dichotomie

| N       | EletsNonTries+ | EletsNonTries- | EletsTries+ | EletsTries- | EletsTriesDicho+ | EletsTriesDicho- |
| ------- | -------------- | -------------- | ----------- | ----------- | ---------------- | ---------------- |
| 100000  | 0.000000       | 0.000000       | 0.000000    | 0.000000    | 0.000000         | 0.000000         |
| 200000  | 0.000000       | 0.000000       | 0.000000    | 0.000000    | 0.000000         | 0.000000         |
| 400000  | 0.000000       | 0.000000       | 0.000000    | 0.000000    | 0.000000         | 0.000000         |
| 600000  | 0.000000       | 0.000000       | 0.000000    | 0.000000    | 0.000000         | 0.000000         |
| 800000  | 0.000000       | 0.000000       | 0.000000    | 0.000000    | 0.000000         | 0.000000         |
| 1000000 | 0.000000       | 0.001000       | 0.000000    | 0.001000    | 0.000000         | 0.000000         |
| 1200000 | 0.000000       | 0.000000       | 0.000000    | 0.016000    | 0.000000         | 0.000000         |
| 1400000 | 0.000000       | 0.000000       | 0.000000    | 0.000000    | 0.000000         | 0.000000         |
| 1600000 | 0.000000       | 0.000000       | 0.000000    | 0.000000    | 0.000000         | 0.000000         |
| 1800000 | 0.000000       | 0.000000       | 0.000000    | 0.000000    | 0.000000         | 0.000000         |

### TP2 Partie 2 : MaxEtMinA vs MaxEtMinB

| N       | CompA   | CompB   | TimeA(s) | TimeB(s) |
| ------- | ------- | ------- | -------- | -------- |
| 100000  | 199987  | 149998  | 0.000000 | 0.000000 |
| 200000  | 399984  | 299998  | 0.000000 | 0.000000 |
| 400000  | 799988  | 599998  | 0.000000 | 0.000000 |
| 600000  | 1199988 | 899998  | 0.000000 | 0.005000 |
| 800000  | 1599989 | 1199998 | 0.000000 | 0.000000 |
| 1000000 | 1999982 | 1499998 | 0.000000 | 0.018000 |
| 1200000 | 2399990 | 1799998 | 0.000000 | 0.015000 |
| 1400000 | 2799991 | 2099998 | 0.010000 | 0.006000 |
| 1600000 | 3199988 | 2399998 | 0.000000 | 0.000000 |
| 1800000 | 3599986 | 2699998 | 0.016000 | 0.000000 |

---

## Graphiques

Pour visualiser les résultats, des graphiques ont été générés en Python avec `matplotlib` :

* **TP2 Partie 1** : Comparaison des temps d'exécution pour Naïf / Trié / Dichotomie.
* **TP2 Partie 2** : Comparaison des temps pour MaxEtMinA et MaxEtMinB.

**Exemple Python pour générer les graphiques :**

```python
import matplotlib.pyplot as plt

numbers1 = [100000,200000,400000,600000,800000,1000000,1200000,1400000,1600000,1800000]
non_tried_plus = [0,0,0,0,0,0,0,0,0,0]
non_tried_minus = [0,0,0,0,0,0.001,0,0,0,0]
tried_plus = [0,0,0,0,0,0,0,0,0,0]
tried_minus = [0,0,0,0,0,0.001,0.016,0,0,0]
dicho_plus = [0]*10
dicho_minus = [0]*10

plt.figure(figsize=(12,6))
plt.plot(numbers1, non_tried_plus, 'o', label='Naïf +')
plt.plot(numbers1, non_tried_minus, 's', label='Naïf −')
plt.plot(numbers1, tried_plus, '^', label='Trié +')
plt.plot(numbers1, tried_minus, 'x', label='Trié −')
plt.plot(numbers1, dicho_plus, 'v', label='Dicho +')
plt.plot(numbers1, dicho_minus, 'd', label='Dicho −')
plt.xlabel("Taille du tableau N")
plt.ylabel("Temps (s)")
plt.title("TP2 Partie 1 : Comparaison Naïf / Trié / Dichotomie")
plt.xscale("log")
plt.yscale("log")
plt.grid(True, which="both", ls="--")
plt.legend()
plt.tight_layout()
plt.show()
```

---

## Détails algorithmiques

### Algorithmes Naïf

* Parcourt tout le tableau, retourne min et max.
* Nombre de comparaisons : N-1 pour le minimum, N-1 pour le maximum.

### Algorithmes Triés

* Exploite l'ordre croissant pour limiter les comparaisons.

### Algorithme Dichotomique

* Divise le tableau en deux, recherche récursive pour limiter le nombre de comparaisons.

### MaxEtMinA vs MaxEtMinB

* Deux variantes pour déterminer simultanément maximum et minimum.
* MaxEtMinB optimise le nombre de comparaisons en traitant les paires d'éléments.

---

## Rôles et Contributions

* **Code et développement** : ABDERRAHIM Sidali 222231402319  
* **Rédaction du rapport** : BELDJERDI Tayeb Yasser 222231404112
* **Tests et évaluations** : GACEM Abdenour 222231640608
* **Collecte des données** : DALIL Faycal 222231658510  

---

**Fin du rapport**
