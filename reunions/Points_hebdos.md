# Points hebdomadaires FagRescue

---

## 28/05/2025

Voir avec droniste pour la chaine de traitement METASHAPE 

Se réunir avec Marc et David pour savoir ce qu'on peut produire -> faire biblio sur le sujet 

Reproduire chaine globale du projet FAGRESCUE et l'amender

Gérer le sous étage végétal ? -> réfléchir à une solution (LIDAR ? Une date de référence avec masque ?)

## 04/03/2025

### Effectué dans la semaine

- Scénarios de vol 
  - GSD au niveau de la surface cible gérée par DJI Pilot 2 dans params avancés
- Réunion avec David -> protocole plus clair
- Récap règles de compensation 
  - A voir si tout le monde veut l'utiliser et comment on applique ces règles
- Tableau récap hebdomadaire + compensation
- Traitement ortho ONERA 05/02 
  - Obligation de traiter en très haute qualité le MNE pour retrouver la résolution souhaitée -> possibilité d'utiliser le MNE/MNS du LiDAR embarqué
  - Cibles metashape = trop petites, inutilisables pour les vols drones -> METASHAPE peut reconnaitre automatiquement les cibles que l'on a mais elles sont peu perceptibles à 115m de haut
  - Recalage point bien assisté par Metashape -> moins de 5 min pour recaler toutes les photos de arbo_2 (??)
  - Plusieurs crashs de l'ordi 
    - Après crash PC licence plus trouvée sur serveur Metashape 
      - Contacter support
- Récupération de la tablette auprès de Richard 
  - Faire plus amples tests avec UGCS (version d'essai) - > semble pas indispensable pour ce printemps
- Suite du doc méthodo
- Sondage R3 
  - 11 mars aprem en fonction de la météo, au dessus parcelle ENSAT
  - ENVOYER mail gestionnaire parcelle pour demander
- Récupération et tests sur le Mavic à venir
- Points transférés à Hugo 
  - Répondre à Hugo pour points ou l'appeler (comment passer de WGS84 à RGF93v2b ?)
- Checklist matos

### Remarques

- Carnet batterie à posteriori avec logs drone ?
- Budget repas mission ? x
- Organisation transition mission ? à voir
- Congés validés du 5 au 10 juin x
- Congés souhaités de 6 au 16 mai (retour Normandie)
- Congés souhaités après première session FagRescue -> passage par Paris à voir pour OM (appeler Sandrine ?)

---

## 20/02/2025

Semaine passée sur l'étude du PPK et sa mise en place dans le protocole

### Effectué ces deux dernières semaines

- Documentation sur PPK et RTK -> application pour LiDAR et MS
- Documentation sur Dual Gimbal pour RTK/PPK ou Emlid
- Test traitements RTK -> résultats complexes à analyser
- Tests base Sparkfun RTK express -> concluant
- R1/R2 DYNAFOR FagRescue + CR + Réu FagRescue
- Abaques vol pour David
- Réunion OM avec Sandrine
- Liste de tâches

### Remarques

- Congés Juin
- Demande remboursement effectué
- Point avec David
- Zone test proche Castanet ?
- OM pour Onera ASD?

---

## 10/02/2025

Deux dernières semaines axées sur la mise en place du protocole en condition réelle (site de l'ONERA)

### Effectué ces deux dernières semaines

- Tests sur WebODM - peut être utile pour produire des orthophotos rapidement mais temps de traitement très longs pour de grandes zones en MS (à creuser davantage)
- Début documentation complète protocole de terrain avec photos installation des capteurs, procédure de collecte des points GPS, planification du vol et mesures d'urgence et/ou maintenance (changement de batterie)
- CR des vols de l'ONERA, premier terminé, second à commencer
- Recherche sur PPK et contact auprès d'Hugo TARDY
- Cartes SD reformatées en FAT32, test sur MicaSense qui indique que les cartes sont bien reconnues
- "Formation" prise de vue Gabriel + Jérôme
- Mise en place du sujet de CNUM v1 (recherches + rédaction)
- Stockage des données récoltées sur DD + PC
- Modification drone (sécurisation cable MicaSense, installation FTS + découpe mousse valise)
- Check dates DJI Care (sur le nextcloud drone)
- Logement Lyons
- Accueil prévention (fiche à remplir) + visite médicale
- Participation HCERES

### Remarques

- Le terrain s'est bien passé à l'ONERA malgré des dysfonctionnements du RTK - Will contacté pour plus de précisions + recherches sur PPK
- Dans les deux/trois semaines à venir, protocole sera achevé + topo complet à faire à Will
- Contacter maraichers pour tests sur une journée ? Ou trouver zone d'étude plus proche ?
- V2 de fiche checkup vol à rédiger en s'appuyant sur expérience terrain
- Trop de problème carte graphique PC actuel - attente du prochain PC pour débuter traitements
- Télétravail jeudi
- RDV Sandrine demain pour missions
- Enseignement avec Yousra dans l'année (Python) ?
- Thèse ? 
  - Quelle année ?
  - Quel projet ? Continuation FagRescue ? Possibilité de commencer sur FagRescue puis migrer sur second projet ?
  - Quand sera validé nouveau projet ?
  - Quelle rémunération/fonds de projet ?
  - Conditions ? (école doctorale ?)
  - CIFRE ?

### Liste de tâches pour la semaine à venir (et +)

- Finir protocole complet + envoyer une v1 à Marc pour validation
- Après validation, trouver zone d'étude pour entrainement, sondage auprès de l'équipe (priorité David et Wil) + journée de formation
- Modifier Carnet de vol de l'ONERA pour l'adapter à nos besoins et l'emmener sur le terrain
- Vérifier le formatage nécessaire pour le Zenmuse
- Retoquer checklist pré-vol
- Faire diapos pour présentation R1 FAGRESCUE
- Revoir carte mentale planif vol
- Faire point à Marc modalités missions RH
- CNUM - premiers RDV

---

## 24/01/2025

Semaine axée sur la prise en main de ZenMuse L2 pour préparer le vol à l'ONERA.

### Effectué dans la semaine

- Vol d'essai avec ZenMuse L2
- Bibliographie ZenMuse (paramètres d'acquisition, chaines de traitement..)
- Installation licence flottant MetaShape (serveur local + client)
- Documentation ZenMuse, Metashape, MicaSense, RTK
- Premiers pas sur MetaShape
- Vérifs images MicaSense + métadonnées exifs
- Connexion RTK au drone
- Prise en main FlightHub 2
- Livraison spectralon à l'ONERA
- Journée des non-permanents + visite médicale
- Préparation batteries pour vol ONERA (toutes les batteries à 100%)

### Remarques

- Vol impossible depuis le mercredi 22/01/25 -> installation du salon robotique agricole
- Conditions de vol mauvaises pour test ZenMuse + mauvais paramètres (nb de retours par exemple) -> autres tests à effectuer
- Impossible de télécharger logiciels DJI sous Linux -> dual boot sur futur PC
- DJI FlightHub 2 = pas utilisable pour Lidar, UGCS a l'air plus performant
- Congés lundi 27 et vendredi 31
- Remboursement mission MTP ?
- Logement Lyons-La-Lorêt

---

## 17/01/2025

### Effectué dans la semaine

- Deux vols : un d’essai pour les procédures RTH et l’autre pour tester MicaSense. L’installation du ZenMuse a été faite depuis la salle de stockage
- Edition du carnet de vol pour le M350 afin d'avoir une trace de tous les vols effectués
- Création d'une checklist pré-vol
- Création d'une checklist post-vol (même document que pour la précédente, dans une autre feuille)
- Listage du matériel manquant
- Documentation sur le M350, procédures d’importances et specs
- Documentation sur MicaSense (en cours)
- Renseignements sur le début des traitements des images MicaSense et leur influence sur les conditions de vol
- Compte rendu réunion avec Thomas Houet

### Remarques

- Compte nécessaire pour l’utilisation du ZenMuse
- Identification à distance pas encore paramétré sur le M350 + il faut coller le numéro d’exploitation sur le drone
- Aborder remboursement forfait MTP + examen drone
- Journée des non permanents le 21/01
- Visite médicale
- Rappel dates de congés

### Liste de tâches pour la semaine à venir

- Lundi 20 janvier 2025 : RDV avec Marc pour discuter du FTS, du compte pour Zenmuse ainsi que les démarches relatives aux scénarios français et européens + récupérer ancien PC de Gabriel
- Se renseigner sur la réglementation européenne auprès d’Escadrone (drone C3 + scénario)
- Faire de la documentation sur les paramètres avancés de MicaSense et leur possible impact sur les données
- Charger les données de MicaSense et vérifier s’il y a bien les données d’irradiance dans les exifs
- Faire des tests avec Centipede RTK puis débuter un protocole applicable sur le terrain
- Faire des tests et de la documentation sur ZenMuse L2
- Faire test complet capteur MicaSense (placement cibles + CentipedeRTK, prendre le panneau pour la reflectance et prévoir un vol complet au dessus des parcelles agricoles).

## 

## 

## 

## 