---
title: Recherches 
layout: default
---
# Recherches
## Présentation
Sont présentés dans cette page les différentes questions abordées, les méthodes pour y répondre ainsi que les résultats.
Dans la mesure du possible, les dates de recherches seront également spécifiées.

Cliquez sur le lien pour afficher directement chaque recherche effectuée :

- [Corrections radiométriques](recherche/radiometrie.md)
- [Corrections géométriques](recherche/geometrie.md)
- [Comparaison de l'impact des MNS sur la réflectance des orthomosaïques](recherche/comparaison_MNS.md)

### Questions

- Quelle est la précision des corrections radiométriques produites (DLS/CRP et ELM) ?

- Dans la série temporelle, existe-t-il une cohérence spectrale ? Est-elle utilisable dans l’état ?

### Méthode
#### 1.2 - Impact des méthodes de corrections radiométriques sur une date
##### 1.2.1 - Impact DLS/CRP
1. Production orthomosaïque du 29/04/2025 via Metashape en utilisant :
    - DLS + CRP avant et après le vol
    - DLS + CRP avant le vol
    - DLS + CRP après le vol
    - CRP avant le vol
    - CRP après le vol

2 - Normalisation de chaque bande pour passer en valeur de réflectance (entre 0 et 1) et export en Lambert-93

3 - Création de polygones au centre des linos des images et calcul de la valeur moyenne de réflectance dans chaque bande et pour chaque technique utilisée pour comparaison

4 - Inspection des valeurs du DLS (luminance) pour voir si de potentiels problèmes pourraient venir de là

## 2 - Corrections géométriques

## 3 - Comparaison des MNS 