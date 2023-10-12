# Méthodes locales
Ainsi, les experts en reconnaissance faciale se sont également intéressés à d’autres méthodes dites locales. Ces méthodes sont moins sensibles aux variations d’environnement, mais obligent cependant la localisation de certains points du visages (appelés points nodaux). Elles sont ainsi dites model-based puisqu’elles s’intéressent non plus à des caractéristiques globales, mais locales du visage. Le principe est de détecter des points clés importants sur le visage,  tels que les coins des yeux, le bout du nez et les coins de la bouche.  Ces points clés servent à définir la géométrie du visage et sont  utilisés pour aligner et identifier les visages ( on parle de modèle).

Nous avons identifié cinq techniques locales largement utilisées.
La première est celle des Modèles de Markov cachés (HMM, modèles probabilistes). Chaque modèle de HMM représente un individu spécifique. Les états cachés du HMM peuvent correspondre à différents états du visage de cet individu, tels que la pose, l'expression, ou d'autres caractéristiques faciales. Le modèle apprend à partir des séquences d'images comment ces états cachés évoluent dans le temps. À chaque état caché, le HMM génère des observations (caractéristiques faciales) qui sont spécifiques à cet état. Ces observations peuvent être des vecteurs de caractéristiques extraites des images du visage, comme les distances entre les points de repère faciaux. Cette méthode est complexe mais elle peut s’adapter lors de l’absence de donnée (partie du visage manquante), et gère efficacement l’évolution du visage (âge) (Ferdinando Samaria, Steve Young, 1994).

Une autre technique connue est celle du Local Binary Patterns. Le principe général est la comparaison de luminance d'un pixel avec les niveaux de ses voisins. Ce concept permet la reconnaissance de motifs réguliers, à savoir des textures et des zones spécifiques du visage. Un procédé similaire appelé Active Appearance Model (AAM) produit un modèle statistique de la forme et de l’apparence des niveaux de gris des zones d'intérêt (Mebarka Belahcen, 2013).

Nous avons également identifié des techniques de transformation mathématique telles que la transformation en ondelettes (filtre de Gabor) et la transformation en curvelettes. 
La méthode des ondelettes permet de décomposer une image en différentes échelles de détail.  Elle permet de représenter une image sous forme de coefficients  d'ondelettes, qui capturent les variations d'intensité et de texture à  différentes résolutions spatiales.
La méthode des curvelettes représente des images de manière éparse dans le domaine des fréquences et des directions. Elle est particulièrement adaptée pour extraire des caractéristiques directionnelles à différentes échelle, en particulier les contours du visage et les motifs directionnels.
Nous verrons un exemple concret d’application de ces méthodes au sein d’un système de reconnaissance faciale.


![unnamed](https://github.com/julienpillis/Veille_techno_RF/assets/73343827/e75bf8b0-2bf1-4cba-9f05-87e6019d2724)
<br><i>Lien du graphe : <a href="https://go.stemic.app/maps/1bf0a933-a027-426c-95fa-daad89119f85">Extraction des caractéristiques</a> </i>
