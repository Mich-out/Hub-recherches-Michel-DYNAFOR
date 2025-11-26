---
title: Compte rendu - R1/R2 FAGRESCUE  
layout: page
---

**Réunion du 18/07/2025 à 10h**

## Participants
- Michel Tarby – DYNAFOR  
- Sophie Fabre – ONERA

## Objectifs de la réunion  
Cette réunion avait pour but de faire un point sur le projet **FAGRESCUE**, en particulier sur les **corrections radiométriques et géométriques** à mettre en place pour le traitement des images. Plusieurs approches ont été discutées, et une orientation commune a été définie pour la suite des traitements.

## Points discutés

### 1. Corrections radiométriques

- **Sophie F.** ne dispose pas de code spécifique pour le traitement des données issues de l’**ASD**. Toutefois, elle recommande l’utilisation de la bibliothèque **SpecDAL**, à condition de bien suivre les **trois étapes de l’exemple** qu’elle a fourni.

- Les **corrections radiométriques** doivent être appliquées **avant** les corrections géométriques si l’aspect radiométrique est prioritaire. Cependant, si les **bandes spectrales** du capteur sont **larges**, l’ordre d’application des deux corrections a peu d’influence. Dans le cas du projet FAGRESCUE chez DYNAFOR, l’ordre importe peu.

- L’utilisation d’un **ELM (Empirical Line Model)** est envisageable pour convertir les valeurs de **pixels bruts** en **réflectance**. Cela nécessitera la création d’un **nuage de points** reliant les valeurs brutes des **spectralons** (linos utilisés sur le terrain) aux mesures de l’ASD, sur deux **plages spectrales** différentes : **visible** et **NIR**.

- L’ELM suppose que les réflectances obtenues seront **relatives** (et non absolues). Cela implique que les images devront être utilisées **dans une logique temporelle cohérente**, et non analysées de manière isolée.

- Les valeurs de réflectance transmises par **Micasense** pour le **spectralon** seront **comparées à celles mesurées en laboratoire** par l’ONERA pour validation.

- La relation entre pixels bruts et réflectance est généralement **linéaire**.

- Sophie F. a validé l’utilisation du dispositif **DLS-CRP**. Toutefois, l’approche **ELM** apparaît également pertinente et méritera d’être explorée en parallèle.

### 2. Corrections géométriques

- Les **corrections géométriques** ont été peu abordées lors de cette réunion. Il a néanmoins été confirmé que le **traitement par date** en utilisant le **RTK/PPK** combiné aux **mires au sol** est la bonne approche.

- Pour affiner encore la précision, une **co-registration** sera nécessaire sur l’ensemble des dates. Le choix du **filtre de co-registration** est un point crucial. À ce stade, le **moyennage** semble être la meilleure option, alors que le **plus proche voisin** serait moins performant sur le plan géométrique.

- Une réunion dédiée entre **Sophie F.** et **Michel T.** sera organisée à la fin de l’été 2025 pour discuter de cette co-registration plus en détail.

### 3. Conclusion – traitements par projet

- Pour **Bionomeex**, les **corrections standards** déjà mises en œuvre sont parfaitement adaptées. Le traitement des données comprendra :
  - la transformation en **réflectance** via le **DLS-CRP** ;
  - le **géoréférencement individuel** à l’aide des données RTK/PPK et des **mires au sol** ;
  - la **co-registration**, avec un **filtre à déterminer**.

- Pour les futures analyses chez DYNAFOR, la mise en œuvre d’un **ELM** permettra d’évaluer sa **pertinence et sa précision**.

### 4. Divers

- Un **étudiant finlandais** rejoindra l’ONERA à partir de **septembre 2025** pour une durée d’un an. Il travaillera sur la **caractérisation des forêts** par drone en temps réel. Ayant déjà travaillé sur des problématiques de **segmentation**, il pourrait être une **ressource intéressante** pour la suite du projet.

- Une **présentation de l’ANR** est prévue à l’ONERA à la **rentrée 2025**. Afin d’illustrer les propos de **Sophie F.**, **Michel T.** s’est engagé à fournir :  
  - un **MNS** ;  
  - un **nuage de points LiDAR** issu de la mission réalisée sur le site du **FAUGA** (zone goudronnée) ;  
  - une **orthomosaïque multispectrale** de cette même zone serait idéale. À défaut, celle de la mission réalisée à **Lyons** pourra suffire.
