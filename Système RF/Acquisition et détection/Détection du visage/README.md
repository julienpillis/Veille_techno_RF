# Détection des visages
La détection des visages est étroitement liée à la qualité de l'acquisition de l'image : une image correctement capturée facilitera une analyse plus précise. Le processus de transition entre les deux est appelé codage, et il consiste à pré-représenter numériquement un visage si l'image contient un objet de la classe 'visage'.

## Objectifs et enjeux 
La détection du visage répond à deux objectifs : la localisation et l'identification d'un visage. Cependant, les enjeux associés sont nombreux. En effet, de nombreuses solutions sont conçues pour fonctionner exclusivement dans un environnement contrôlé, c'est-à-dire lorsque des conditions précises d'acquisition de l'image sont remplies. Plusieurs critères peuvent ainsi influencer l'efficacité de la détection dans un environnement externe :
l’illumination (l’apparence d’un visage change considérablement avec la variation de l’éclairage
le changement de position du visage (frontal, profil), des personnes,
les expressions faciales différentes,
les occultations (en effet, sur une image, un visage peut être masqué ou partiellement masqué par un objet ou un un autre visage),

De plus, certains éléments structuraux du visage peuvent également poser des défis:

présence d’accessoires : lunettes, chapeau, ..,
composantes intrinsèques: barbe, moustache, ..,
maquillage, déguisement.


## Techniques de détection
De nombreuses méthodes et techniques de traitement ont été développées, et la littérature abonde en la matière. Celles-ci se basent sur cinq principales approches que nous allons expliciter afin de comprendre leurs avantages et leurs limites. Ces techniques sont les suivantes : 
Approche basée sur les connaissances acquises
Approches basées sur le “Template Matching”
Approche basée sur l’apparence
Approches basées sur des caractéristiques invariantes

### Approche basée sur les connaissances acquises
Cette méthode est particulièrement utilisée pour la localisation du visage. Elle repose sur la détection des principales composantes du visage telles que les yeux, le nez, la bouche, etc. De plus, elle peut être basée sur un ensemble de règles prédéfinies qui doivent être satisfaites pour localiser un visage.
Ces méthodes ont été pionnières dans la détection des visages et sont basées sur les travaux réalisés par Yang et Huang en 1994, ainsi que sur ceux de Kotropoulous et Pitas en 1997. Ces chercheurs se sont appuyés sur les méthodes de calcul de Kanade datant de 1973. 
Yang et Huang proposent de s'appuyer sur la résolution du visage pour identifier les points caractéristiques en utilisant une méthode dite "descendante" ou "top-down". En effet, en réduisant progressivement la résolution d'une image, les traits majeurs du visage disparaissent, transformant le visage en une forme plus uniforme. C'est le principe de leur méthode, qui peut être décrite comme suit :
“En commençant par les images à faible résolution, un ensemble de candidats de visage est déterminé à l’aide d’un ensemble de règles permettant de rechercher les régions uniformes dans une image. Les candidats de visage sont ensuite vérifiés en cherchant l’existence de traits faciaux proéminents grâce au calcul des minimas locaux à des résolutions supérieures.”, Guerfi 2011.
Cette méthode permet de réduire le temps de calcul en utilisant des images sous-échantillonnées, mais elle entraîne de nombreuses fausses détections.
En 1997, Kotropoulous et Pitas ont introduit une méthode basée sur des règles. La localisation du visage repose sur les travaux de Kanade, qui vise à détecter les contours d'un visage en se basant sur l'intensité de la luminance des pixels d'une image 2D. Cependant, cette méthode n’est pas optimale lorsque le visage est présent dans un environnement complexe en arrière-plan.
Ainsi, bien que les méthodes basées sur les connaissances acquises aient été largement utilisées à une époque, elles sont de moins en moins courantes. Cependant, le principe des connaissances acquises a été repris et amélioré dans les systèmes de réseaux de neurones.
Approches basées sur le “Template-Matching” 
Cette méthode repose sur des templates paramétrés, en calculant la corrélation entre le template et l'image candidate pour identifier les différentes parties du visage sur l'image. Ces templates sont partitionnés en régions. La méthode se fonde ensuite sur la détermination d'invariants aux changements de luminosité pour caractériser les différentes parties du visage, telles que les yeux, le front, etc., comme décrit ci-dessous :
“Cet algorithme calcule ainsi les rapports de luminance entre les régions du visage et retient les directions de ces rapports (par exemple, la région 1 est-elle plus claire ou plus sombre que la région 2). La figure ci-dessous montre un modèle prédéfini correspondant à 23 relations. Ces relations prédéfinies sont classifiées en 11 relations essentielles (flèches) et 12 relations confirmations (gris). Chaque flèche représente une relation entre deux régions. 
Une relation est vérifiée si le rapport entre les deux régions qui lui correspond dépasse un seuil. Le visage est localisé si le nombre de relations essentielles et de confirmation dépasse lui aussi un seuil.”, Solofoniaina Nomenjanahary Sarobidy, 2022.

![Image1](https://github.com/julienpillis/Veille_techno_RF/assets/73343827/40cf471b-122c-4147-a00f-0463a5818f86)
<br><i>Modèle de visage composé de 16 régions (les rectangles) associées à 23 relations (flèches).</i>

### Approche basée sur l’apparence
Ces approches utilisent des techniques d'apprentissage automatique. On fournit à l'algorithme une bibliothèque d'images comprenant de nombreuses images de visages différents. Le principe de cet algorithme est ensuite de classer l'image candidate dans la catégorie "visage" ou "non visage".
Pour ce fait, une des méthodes les plus connues de détection est l’Eigenface développée par Turk et Pentland en 1991 qui consiste à “à projeter l’image dans un espace et à calculer la distance euclidienne entre l’image et sa projection  Si cette perte d’information est grande (évaluée à partir de la distance, que l’on compare à un seuil fixé a priori), l’image n’est pas correctement représenté dans l’espace : elle ne contient pas de visage”, Guerfi 2011. Cette méthode est très intéressante de par les résultats qu’elle propose mais nécessite un temps de calcul important. Elle a d’ailleurs été ré-utilisée et adaptée aux besoins par la suite. 
En 1998, avec Rowley et al., les réseaux de neurones sont apparus dans leurs formes initiales. Leur technique repose sur la localisation des visages à l'aide de réseaux de neurones, suivie de la vérification des résultats pour les optimiser. Une étape de prétraitement consiste à égaliser l'histogramme (considérant l'objet numérique comme un signal), cette étape pouvant également être effectuée dans d'autres systèmes lors de la normalisation. Ce système est très robuste, résistant aux bruits et facilement extensible. En effet, le système a par la suite été enrichi d'un système d'analyse multi-résolutions, ainsi que d'un système capable de détecter les visages ayant subi des rotations dans le plan et de différentes échelles. Les limites des neurones résidaient alors dans leur complexité de construction, mais ils sont devenus très courants en 2023. De plus, la phase d'apprentissage est très coûteuse et nécessite une bonne alimentation en modèles (le choix des modèles joue un rôle fondamental).
Les modèles de neurones continuent donc d'évoluer depuis le début du XXIe siècle, avec les contributions de Féraud et al. (2001), qui ont permis de mettre en œuvre l'Analyse en Composantes Principales (ACP) non linéaire, une technique précieuse pour l’étape d'extraction des caractéristiques en reconnaissance faciale. Garcia et Delakis ont poursuivi cette avancée avec les réseaux convolutifs, qui ont atteint un taux de détection de 90,3% en 2004. 
En 2005, Bradski, Kaehler, et Pisarevsky ont développé la bibliothèque OpenCV, qui demeure l'une des plus importantes en 2023. En effet, associée aux algorithmes de Viola et Jones en 2001, cette méthode s'est révélée être un véritable succès, reposant sur "l'utilisation de « classifieurs de Haar » montés en cascade (boostés) au moyen d’un algorithme AdaBoos”. [...]  Le principe de cette méthode est d’obtenir un algorithme complexe de classification, composé de classifieurs élémentaires qui éliminent au fur et à mesure les zones de l’image qui ne sont pas compatibles avec l’objet recherché. Ces classifieurs binaires reposent sur des primitives visuelles qui dérivent des fonctions de Haar ( Haar- like features).”, Guerfi 2011.
En septembre 2022, Sumanto, Bamban, Wijonarko, Muhammad Qommarudin, Aji Sudibyo, Pudji Widodo, Afit Muhammad Lukman propose s’appuie sur les algorithmes de Viola-jones  pour développer une technique de détection avec un taux de réussite de 100%. Cette technique se base sur l’analyse des couleurs et du contraste de l’image et a été testé sur la base de données d’images Wider Face. Le choix de la base de données n’est pas anodin : c’est une banque qui permet d’avoir diverses tailles d’images, de positions, de caractéristiques, différents ce qui permet de mieux apprécier la technique développée. Le modèle s’appuie sur la détection de motif de Haar, qui sont des échantillons de visage rectangulaires de l’ordre du pixel qui permettent de distinguer tous les points et caractéristiques du visage. Cette distinction se fait en analysant les contrastes de couleur entre deux parties distinctes et peuvent prendre toutes les nuances du blanc au noir. Si deux motifs ont la même nuance de couleur, ils fusionnent pour former un plus grand rectangle. Une image intégrale (integral image) est créée en se basant sur la conversion de ces motifs de Haar en utilisant l’algorithme/framework Viola_jones (codé sur MATLAB) préalablement entraîné pour la détection des visages sur une photo donnée. 

### Approche basée sur des caractéristiques invariantes
“Ces approches sont utilisées principalement pour la localisation du visage. Les algorithmes développés visent à trouver les caractéristiques structurales existantes même si la pose, le point de vue ou la condition d’éclairage changent. Puis ils emploient ces caractéristiques invariables pour localiser les visages. Nous pouvons citer deux familles de méthodes appartenant à cette approche : les méthodes basées sur la couleur de la peau suivante et les méthodes basées sur les caractéristiques (deux yeux, deux narines et la jonction nez/lèvre) pour écrire un visage typique.”  Solofoniaina Nomenjanahary Sarobidy, 2022.

Ces techniques de détection mènent à une pré-représentation du visage qui doit ensuite être numérisé. On parle de pré-traitement. 

![Image2](https://github.com/julienpillis/Veille_techno_RF/assets/73343827/4b373e7e-f753-475a-8e02-3c4755179484)

<br><i>Synthèse graphique des méthodes d’acquisition et détection des visages 
</i>

