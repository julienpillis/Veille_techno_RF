# Pré-traitement du visage
Après avoir détecté le visage sur l'image, il est nécessaire de la traiter afin de normaliser les signaux numériques obtenus et de faciliter l'extraction des traits caractéristiques du visage. L'objectif du prétraitement est d'éliminer le bruit et les signaux parasites dus à la qualité des dispositifs optiques ou électroniques lors de l'acquisition de l'image.

Les processus de pré-traitement commencent par la correction des défauts courants liés à la capture d'image. Ces processus peuvent être de deux types :
D'ordre géométrique : ils visent à corriger l'échelle. En effet, la taille du visage dans l'image acquise peut varier en fonction de la distance entre le module d'acquisition et la personne. Le système corrige donc les déformations et extrait alors le visage pour l’aligner et le mettre en forme pour l’étape d’après.
D'ordre photométrique : ils permettent de réduire les effets de l'illumination de l'image.
Ces techniques réalisent une première normalisation des images de la classe "visage". Les visages se dirigent ensuite vers la deuxième étape pour être corrigés. 
Au sein de notre étude, nous nous sommes intéressés aux méthodes de pré-traitement les plus courantes, parmi lesquelles figurent la correction Gamma ou l’égalisation d’histogramme.

Les notions de ces méthodes sont principalement issues des différentes thèses étudiées, portées sur le sujet : Guerfi 2011,  Belahcene 2013, Béchairia 2019, Solofoniaina Nomenjanahary Sarobidy 2022.


Correction Gamma

La correction gamma est un type de traitement d'image couramment utilisé pour corriger les différences de réponse en luminosité entre les capteurs d'image et les écrans d'affichage. Cette technique est largement employée dans le domaine de l'audiovisuel car elle confère aux images un aspect plus réaliste. Elle a été développée en 1970 par l'informaticien Peter G. Oliphant et repose sur la formule suivante :

  = D log H
où gamma représente le facteur de contraste (émulsion), D l’opacité et H la lumination/exposition reçue. Le gamma s'évalue à partir d'un sensitogramme par la pente de partie rectiligne de la courbe de Hurter-Driffield. 
Le contraste apparent d'un tirage papier en photographie ou d'un tirage positif en cinématographie résulte du gamma de l'émulsion utilisée à la prise de vue et de celui du support de tirage. 
Au niveau de l’image numérique, la formule de correction gamma est : 
luminosité = 255* (données de l'image 255)

où gamma est une valeur comprise entre 0,1 et 5,0. Une valeur gamma de 1,0 n'entraîne aucune modification de l'image. (ref : tech-lib.fr/correction-gamma) 

Égalisation d’histogramme

L'égalisation d'histogramme est une technique de traitement d'images largement utilisée dans de nombreux secteurs nécessitant l'utilisation d'images numériques, tels que l'audiovisuel et la médecine. Cette méthode permet de répartir de manière plus uniforme les valeurs des pixels en appliquant une transformation à chaque pixel de l'image. Elle contribue à mieux répartir les intensités, réduisant ainsi la variabilité.Les histogrammes sont particulièrement utiles en photographie pour la retouche d'images. 

Cependant, d'autres méthodes, plus ou moins complexes, sont également disponibles :
Lissage anisotropique : 
Cette méthode relativement complexe permet de réduire le bruit et d'éliminer les détails indésirables tout en préservant les caractéristiques essentielles de l'image.
Méthode Retinex : 
Elle se base sur un algorithme inspiré des mécanismes biologiques de l'œil. Cette méthode ajuste automatiquement les couleurs en fonction de l'environnement, garantissant une perception cohérente des couleurs.
Filtrages : 
Il existe plusieurs types de filtres, à savoir les filtres linéaires et non linéaires. Les filtres linéaires incluent le filtre passe-haut pour l'accentuation des détails et le filtre passe-bas pour le lissage, ce qui implique un compromis entre la réduction du bruit et la conservation des détails et des contours significatifs. Les filtres non linéaires, tels que le filtre minimum, médian ou maximum, remplacent la valeur du pixel central par la valeur minimale, médiane ou maximale des pixels environnants, en fonction de la technique utilisée.
Segmentation : 
Cette technique consiste à regrouper les pixels ayant des propriétés caractéristiques similaires en régions connectées, facilitant ainsi l'extraction d'informations. La segmentation peut se faire en fonction de différentes caractéristiques, telles que la couleur, les contours, ou l'intensité des pixels.
Convolution : 
Cette méthode repose sur le remplacement de la valeur d'un pixel par une combinaison linéaire de ses voisins.

Ces méthodes sont utilisées pour traiter les images, les normaliser et faciliter l'extraction des caractéristiques. Chaque système de reconnaissance faciale est équipé d'une ou plusieurs de ces méthodes. 

