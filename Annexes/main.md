# Annexes et résumés

## Belahcen Mebarka, “Authentification et Identification en Biométrie”. 
(2013) Université Mohamed Khider Biskra, Thèse de doctorat, thesis.univ-biskra.dz/id/eprint/944.


Résumé : 

Le chapitre 2 est le chapitre qui nous permet d’en apprendre plus sur l’étape que nous étudions. L’auteur effectue un état de l'art de la reconnaissance faciale dans lequel il présente deux principales approches pour la reconnaissance faciale : les approches locales et les approches globales.
Les approches locales se concentrent sur des caractéristiques locales du visage et traitent différentes régions de l'image du visage séparément. Elles utilisent souvent la détection/extraction de caractéristiques faciales locales. Par exemple, certaines techniques extraient automatiquement un ensemble de caractéristiques géométriques d'une image de visage, tandis que d'autres se basent sur des cartes de contours pour mesurer la similarité entre les visages. Ces méthodes sont plus flexibles pour modéliser les variations de pose, d'illumination et d'expression faciale, mais elles nécessitent souvent un placement manuel de points d'intérêt.
Quant aux approches globales, elles considèrent le visage dans son ensemble et utilisent des techniques d'analyse statistique pour projeter l'image du visage dans un espace de dimension réduite. Par exemple, la technique des "Eigenfaces" utilise l'Analyse en Composantes Principales (ACP) pour réduire la dimension des images de visages. Cependant, ces méthodes sont sensibles aux variations de luminosité, de pose et d'expression faciale.
Les approches globales peuvent être linéaires ou non linéaires. Les méthodes linéaires, telles que les "Eigenfaces" et la "Fisherfaces," réalisent une projection linéaire des visages dans un espace de dimension réduite. Les méthodes non linéaires, telles que l'Analyse en Composantes Principales à Noyaux (Kernel-PCA) et d'autres techniques, utilisent des projections non linéaires pour réduire la dimension des données.
Les approches hybrides combinent à la fois des caractéristiques locales et globales. Elles cherchent à tirer parti des avantages des deux types de méthodes en combinant la détection de caractéristiques locales avec l'extraction de caractéristiques globales. Par exemple, l'Analyse en Composantes Locales (LCA) réalise une projection linéaire des visages en utilisant plusieurs ACP pour extraire différentes caractéristiques locales, puis les combine pour la reconnaissance.
En résumé, la reconnaissance faciale peut être réalisée en utilisant diverses approches, qu'elles soient locales, globales, linéaires ou hybrides, en fonction des besoins spécifiques de l'application et de la complexité des données. Chaque approche présente ses avantages et ses inconvénients en termes de robustesse, de précision et de flexibilité.
Ces approches s’effectuent sur des modèles/images 2D. Cependant, les modèles 3D les utilisent en combinant d’autres données.
Les méthodes présentées dans cette thèse sont disponibles sur le graphe associé à cette partie.

## Tsalakanidou, F., Malassiotis, S., & Strintzis, M. G. "Face localization and authentication using color and depth images." 
IEEE transactions on image processing : a publication of the IEEE Signal Processing Society, 14(2), (2005) 152–168. https://doi.org/10.1109/tip.2004.840714

Résumé : 

L'article présente un système qui combine des données 3D de portée avec des images 2D en couleur ou en niveaux de gris pour améliorer la détection et l'authentification des visages.
Le système propose des algorithmes innovants pour la détection et la localisation des visages, exploitant des informations de profondeur pour garantir la robustesse face aux environnements complexes, aux occlusions, aux variations de pose et d'éclairage.
Ces algorithmes utilisent un modèle dit Hidden Markov Model pour l’extraction des traits caractéristiques du visage. C’est une méthode que l’on utilise sure des images 2D. Cependant, ici, la méthode proposée simplifie le traitement des données 3D en les considérant comme une image 2D, avec des valeurs de pixels correspondant à la distance de la surface de la tête humaine par rapport au plan de la caméra. Le modèle HMM sera directement appliqué sur cette image 2D, qui reporte en réalité des données 3D.
Les résultats expérimentaux montrent que la performance de l'approche basée uniquement sur les données de profondeur n'est pas meilleure que celle des approches 2D standard. Des problèmes liés à la résolution et à l'exactitude du système d'acquisition d'images de profondeur sont identifiés comme des facteurs limitants.
La combinaison de données de profondeur et d'images couleur ou en niveaux de gris améliore en revanche considérablement les performances par rapport aux approches 2D standard.
Les résultats expérimentaux montrent que l'approche 2D est considérablement améliorée par l'utilisation de données 3D de profondeur. Les auteurs estiment que l'approche 3D pourrait être intégrée dans n'importe quel système 2D actuel pour obtenir des performances supérieures en matière d'authentification faciale.

## BBC Earth Lab “How Does Facial Recognition Work”
Youtube, 26 Nov 2015, https://www.youtube.com/watch?v=1aHub80AHFk


Cette vidéo fait un état des lieux général sur l’évolution de la détection des traits discriminatoires au sein d’un système de reconnaissance faciale.
La première tentative fut d’identifier les points nodaux (caractéristiques spécifiques du visage) tels que la profondeur de l'orbite oculaire, la distance entre les yeux ou encore la largeur du nez. Ce procédé bio-mimétique s’inspire directement de la reconnaissance d’un individu chez l’Homme. Cela permet de créer un code unique, que l’on appelle : empreinte faciale. Cependant, cette méthode n’est pas la plus précise puisque les photos doivent se ressembler, sinon le système doit se confronter au problème A-PIE ( ge, Pose, Émotions, Intensité (éclairage)).
Des systèmes plus sophistiqués ont donc émergé, tels que les systèmes de reconnaissance en 3D comme Deepface. A partir de photos 2D prises sous différents angles, le système est capable de créer un modèle 3D du visage. Dans cet exemple, le vieillissement et la pose ne posent plus de problème.
Enfin des solutions avec une meilleure précision ont récemment vu le jour par le développement des réseaux de neurones. Les méthodes de Deep Learning ont très bien trouvé leur place dans ce domaine puisqu’elles permettent de reconnaître automatiquement un visage, et peuvent s'entraîner pour acquérir plus de précision.
