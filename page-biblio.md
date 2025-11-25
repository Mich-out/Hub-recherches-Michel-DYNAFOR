# Notes Bibliographie FAGRESCUE

#### NOTES GLOBALES
- En général, pas ou peu d'articles parlant de l'utilisation du LIDAR sur UAV dans le cadre de la phénologie
- Existence de plus articles portant sur les différentes corrections radiométriques possibles pour les capteurs micasense ainsi que leur impact


#### Zeng, Linglin; Wardlow, Brian D.; Xiang, Daxiang; Hu, Shun; and Li, Deren, "A Review of Vegetation Phenological Metrics Extraction Using Time-Series, Multispectral Satellite Data" (2020). Papers in Natural Resources. 1662. https://www.scopus.com/record/display.uri?eid=2-s2.0-85075212117&origin=inward&txGid=705038e56fdb1648f9c97ea3acc62595

- **Review**
- Discussion du protocole pour la mise en place d'une série temporelle par satellite pour phéno
- Etapes = acquisition - calcul d'indices - smoothing sur la série temp (description des possibilités) - récupération des métriques
- **Curve fitting smoothing"** = plus fréquente pour traitement données phéno

A CONTINUER A DECORTIQUER PLUS TARD 

#### Discrimination of Deciduous Tree Species from Time Series of Unmanned Aerial System Imagery Lisein J, Michez A, Claessens H, Lejeune P (2015) Discrimination of Deciduous Tree Species from Time Series of Unmanned Aerial System Imagery. PLOS ONE 10(11): e0141006. https://doi.org/10.1371/journal.pone.0141006

- Détermination des arbres (caduques vs conifères)
- Segmentation + 
- Discute de la difficulté de faire de la photogrammetrie sur des forêts -> utilisation d'un modèle de terrain fait lorsque pas ou peu de feuilles 
- Segmentation (à la main ou algo ?) puis RF pour discriminer caduques de conifères

### Corrections radiométriques

#### Yuxiang Wang, Gert Kootstra, Zengling Yang, Haris Ahmad Khan, UAV multispectral remote sensing for agriculture: A comparative study of radiometric correction methods under varying illumination conditions, Biosystems Engineering, Volume 248, 2024b, Pages 240-254, ISSN 1537-5110, https://doi.org/10.1016/j.biosystemseng.2024.11.005.

- Comparaison de plusieurs méthodes pour la correction radiométrique des images

| Méthode             | DLS utilisé | Panneaux utilisés         | Altitude de capture | Correction dynamique | Avantages principaux                                                                 | Limitations principales                                                               |
|---------------------|-------------|----------------------------|----------------------|-----------------------|----------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------|
| **CRP**             | ❌          | 1 CRP (MicaSense)         | Sol                  | ❌                    | Simple à mettre en œuvre, méthode officielle MicaSense                                | Très sensible aux variations d’éclairage, mauvaise précision                          |
| **ELM**             | ❌          | 3 panneaux faits maison    | Sol                  | ❌                    | Méthode bien établie, meilleure que CRP                                               | Ne gère pas les variations intra-vol, sensible aux nuages                              |
| **DLS-CRP**         | ✅          | 1 CRP (MicaSense)         | Sol                  | ❌                    | Améliore l’uniformité visuelle grâce au DLS                                           | Précision radiométrique moyenne, CRP capturé au sol peu représentatif                 |
| **DLS-LCRP**        | ✅          | 1 panneau gris clair       | Altitude de vol      | ❌                    | Très bonne précision, meilleure prise en compte des effets atmosphériques             | Plus complexe à mettre en œuvre, nécessite un grand panneau visible à 50+ m           |
| **MT-DLS-LCRP**     | ✅          | 1 panneau gris clair       | Altitude de vol      | ✅                    | Meilleure précision & homogénéité, mise à jour dynamique des coefficients             | Méthode la plus coûteuse et complexe à mettre en place                                 |
| **MRP**             | ❌          | Plusieurs panneaux         | Altitude de vol      | ✅                    | Bonne précision sans DLS, robuste aux changements lumineux                            | Moins homogène que les méthodes avec DLS, nécessite bonne répartition des panneaux     |
| **DLS-MRP**         | ✅          | Plusieurs panneaux         | Altitude de vol      | ✅                    | Combine données DLS & panneaux, bon compromis précision/homogénéité                   | Traitement complexe, coût élevé, nécessite gestion fine de l’irradiance                |

#### Guo, Y.; Senthilnath, J.; Wu, W.; Zhang, X.; Zeng, Z.; Huang, H. Radiometric Calibration for Multispectral Camera of Different Imaging Conditions Mounted on a UAV Platform. Sustainability 2019, 11, 978. https://doi.org/10.3390/su11040978

- Discussion de la correction radiométrique pour les images multispectrales
- Utilisation de LRM (Linear Regression Model) entre DN et réflectance
![LRM principe](https://www.mdpi.com/sustainability/sustainability-11-00978/article_deploy/html/images/sustainability-11-00978-g008.png "Principe du LRM entre les nombres digitaux bruts et la réflectance")

- Calibration avec les données in situ puis validation avec cette dernière (mise en relation reflectance mesurée et reflectance calculée puis R² et RMSE)

- Ils conseillent de faire l**a correction radiométrique sur l'orthomosaïque** pour gagner du temps avec peu de différence de précision

- Ils évoquent la possibilité d'avoir une équation universelle pour le capteur dans les mêmes conditions : 

>> *"So far, there has never been a universal calibration equation for this camera. Therefore, a universal calibration equation should be given and assessed. The results show that a universal calibration equation could be well used in similar imaging conditions. It is quite satisfactory to perform radiometric calibration in agricultural and ecological applications. For example, if a series of experiments conducted over a few days and in similar weather conditions and imaging environment, the acquisition of reflectance from the calibration targets might be reduced, which is a real problem in field data collection. The adoption of this universal calibration equation has proposed an innovative idea for quick radiometric calibration, meanwhile, saving much time and human power."*


#### Wang, Y.; Yang, Z.; Khan, H.A.; Kootstra, G. Improving Radiometric Block Adjustment for UAV Multispectral Imagery under Variable Illumination Conditions. Remote Sens. 2024a, 16, 3019. https://doi.org/10.3390/rs16163019 

- Discute de deux façons de traiter des images acquises selon des conditions d'illumination changeantes
- Compare 2 techniques différentes, l'une orientée capteur (avec DLS donc) et l'autre orientée traitement image uniquement -> comparaison de ces deux approches selon 5 techniques différentes :

| Méthode       | Uniformité | Précision | Observations                                |
| ------------- | ---------- | --------- | ------------------------------------------- |
| **ELM**       | ❌          | ❌         | Forte sensibilité à l’éclairage variable    |
| **DLS-CRP**   | ✔️         | ❌         | Moyenne précision, amélioration par capteur |
| **DLS-LCRP**  | ✔️         | ✔️        | Très bon compromis si capteur disponible    |
| **RBA**       | ✔️✔️       | ✔️        | Très performant, même sans capteur          |
| **RBA-Plant** | **✔️✔️✔️** | **✔️✔️**  | Meilleure méthode globale dans ce contexte  |

- **Résumé RBA** :
> **Le Radiometric Block Adjustment (RBA)** consiste à utiliser à la fois :
> - des **panneaux de référence** à réflectance connue, placés dans la zone d’étude,
> - et des **points de concordance (tie points)** entre images, c’est-à-dire des pixels représentant la **même surface au sol observée dans deux images différentes**.
>
> Pour chaque panneau visible, une **zone centrale de 50×50 pixels** est utilisée pour extraire la radiance moyenne.  
> Ces valeurs sont associées à la **réflectance connue** pour générer des **équations de calibration linéaire** par image.
>
> Les tie points sont extraits automatiquement dans les zones de recouvrement des images.  
> Dans la variante **RBA-Plant**, seuls les tie points situés dans des **zones de végétation** sont conservés (filtrés avec un **NDVI > 0.6**).
>
> Un **système d’équations linéaires** est ensuite construit :
> - les panneaux apportent des équations où la réflectance est connue,
> - les tie points imposent que la **réflectance soit identique** pour une même surface vue dans deux images.
>
> Ce système est formulé comme un **problème d’optimisation quadratique contraint**, permettant d’estimer pour chaque image des **coefficients de conversion linéaire** (pente \(a\), offset \(b\)) entre radiance et réflectance.
>
> Ces coefficients sont ensuite appliqués à chaque pixel pour convertir toutes les images en **réflectance corrigée, homogène et comparable**, même en conditions d’éclairage variables.

- Cependant ici, pas de notion de série temporelle et surtout dans le cadre d'agriculture
- RBA très performant mais très chronophage et moins facile à mettre en place que DLS-LCRP (meilleur compromis)

#### Salas, E. A. L. (2020). Waveform LiDAR concepts and applications for potential vegetation phenology monitoring and modeling: a comprehensive review. Geo-Spatial Information Science, 24(2), 179–200. https://doi.org/10.1080/10095020.2020.1761763

- Review discutant de l'utilisation du LIDAR dans le cadre de la phénologie -> discute surtout des LIDAR Waveform (i.e. LIDAR dont l'intensité du signal est captée en continu - pas le cas du ZENMUSE qui est discret = 5 retours)
- En 2020, très peu d'articles sur le sujet (2 vraiment pertinent)
- Existence d'un indice de végétation LIDAR NDLI
- Utilisation du LIDAR dans un étude sur le débourremnt des arbres 

**PAS ADAPTE A NOTRE CAS, LECTURE NON TERMINEE**

#### Elias Fernando Berra, Rachel Gaulton, Stuart Barr, Assessing spring phenology of a temperate woodland: A multiscale comparison of ground, unmanned aerial vehicle and Landsat satellite observations, Remote Sensing of Environment, Volume 223, 2019, Pages 229-242, ISSN 0034-4257, https://doi.org/10.1016/j.rse.2019.01.010.

- Vol environ tous les 7 jours

- Suite d'un article faisant suite à un autre par les mêmes auteurs dans lequel ils mettaient en place un régression linéaire unique pour traiter l'ensemble d'une série temporelle avec NDVI (pas de traitement en réflectance)

- Ici, le but est de faire la sigmoide (phenometrics) des individus de la zone d'étude en utilisant le NDVI et le GCC

- Pour mitiger effet négatif du sous-sol, ils n'ont récupéré qu'une fraction des pixels d'une même couronne dont la DN value > percentile 80% -> utile en période de leaf-off puisque ces pixels représente surtout branche et tronc et permet d'éviter de trouver de la végétation sous canopée (et donc de déterminer à tort que ce sont des arbres précoces)

- GCC calculé direct sur raw DN et NDVI = passage par reflectance via ELM  

- Watershed pour segmentation -> fonctionne plutot bien sur conifères mais beaucoup moins bien sur feuillus

- Deux caméras différentes pour RGB et NIR -> problème de coregistration entre les deux

- LANDSAT très influencé par sous sol

- Erreur de 8 jours pour débourrement -> relié à la fréquence de leurs images


### Q. Yang, L. Shi, J. Han, J. Yu, et K. Huang, « A near real-time deep learning approach for detecting rice phenology based on UAV images », Agricultural and Forest Meteorology, vol. 287, p. 107938, juin 2020, doi: 10.1016/j.agrformet.2020.107938.

- Utilisation de CNN sur image seule pour classifier stade phénologique

- Utilisation du SMF : 
>C’est une méthode basée sur l’ajustement d’un modèle de courbe VI théorique (forme standard) à des observations temporelles de VI (ici, le SWDRVI).
>Ce modèle est spécifique à une culture donnée (ici, le riz).
>Il représente la forme typique de la courbe d’un indice de végétation sur le cycle de croissance complet (du tallage à la sénescence).
>L’idée est que la forme (shape) de cette courbe est stable pour une espèce, même si le moment exact où elle commence ou atteint un pic varie selon les conditions locales

- Phéno du riz sur plus de 160 ha


## Papiers possibles
- DATA Paper sur acquisition, traitement et mise à disposition de la donnée
- Multispectral vs RGB pour phéno du débourrement -> segmentation + classification
- Papier Méthodologie avec sensibilité paramètres de vol (altitude et météo) + capteurs (L2 RGB et RGB Multispec)
- Impact de la correction radiométrique sous différentes conditions d'illumination dans le cadre de la phénologie (calcul d'indices etc.)
- Comparaison de différentes techniques de correction radiométrique dans le cadre de forêt 
- Impact de la correction radiométrique sur la détection phénologie (sigmoïde VS classif supervisée)

- *Effets de la densité d'arbre sur la segmentation des couronnes pour images multispectrales ?*
