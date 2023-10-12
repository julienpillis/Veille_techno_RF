# Méthodes globales
Également appelées méthodes holistiques, les méthodes globales sont des modèles mathématiques capables de relever les caractéristiques géométriques du visage. Ces caractéristiques sont dites globales puisqu’il s’agit de l’ensemble du visage qui est étudié : on parle d’appareance-based model.

Ces méthodes se divisent également en deux catégories : les techniques linéaires et les techniques non linéaires. 

Les premières utilisées sont les <b>techniques linéaires</b>. En effet, elles supposent que les caractéristiques du visage sont des combinaisons linéaires simples des pixels de l'image. En d'autres  termes, elles considèrent que les variations dans les données du visage peuvent être expliquées par des relations mathématiques linéaires, comme une somme ou une multiplication des valeurs de pixel. 
La première évoquée dans la littérature est l’Analyse en Composantes Principales (P.C.A), évoquée dès 1991. Une méthode très connue utilisant le PCA porte le nom de EigenFaces. Plusieurs images d’un visage sont collectées et pré-traitées (généralement converties en niveau de gris, et redimensionnées). Les images sont représentées par des matrices de pixels, qui sont converties en vecteurs et forment une nouvelle matrice où chaque ligne représente une image et chaque colonne un pixel. C’est à ce moment précis que la technique du PCA est utilisée. Elle permet d’extraire des combinaisons linéaires de pixels pour capturer les variations les plus importantes entre les différentes images du visage. Ces variations sont appelées composantes principales (eigenfaces), capables de représenter le visage d’un individu. 
De cette méthode, en découlent de nombreuses autres. C’est le cas de l’Analyse Discriminante Linéaire (LDA, méthode des FisherFaces) (P. N. Belhumeur, J. P. Hespanha and D. J. Kriegman, 1997) ou encore de l’Analyse en Composantes Discrétionnaires Hiérarchiques (HDCA) (D. L. Swets et Juyang Weng, 1999).

D’autres techniques existent, comme celles des Vecteurs Communs Discriminants (DCV), l’Analyse Discriminante Bilinaire (BDA), la Factorisation de matrices non-négatives (NMF) ou encore l’Analyse en Composantes indépendantes (ICA) (Mebarka Belahcen, 2013). 

Vous trouverez sur la figure suivante un liste des techniques linéaires les plus courantes : 


![unnamed](https://github.com/julienpillis/Veille_techno_RF/assets/73343827/c6fd1748-30c8-4241-991f-32c237353366)
<br><i>Lien du graphe : <a href="https://go.stemic.app/maps/1bf0a933-a027-426c-95fa-daad89119f85">Extraction des caractéristiques</a> </i>


De l’autre côté, nous retrouvons les <b>techniques non linéaires</b>. Celles-ci n'imposent pas cette contrainte de  simplicité et de prédictibilité. Elles permettent d'explorer des relations plus complexes et moins prévisibles entre les caractéristiques  du visage, pouvant inclure des courbes, des interactions non linéaires etc… Ces techniques peuvent réutiliser des concepts de techniques linéaires comme le fait le Kernel-PCA (K-PCA). Après obtention de la matrice des images, la Kernel PCA utilise une fonction noyau (kernel) pour transformer la matrice dans un espace de dimension supérieure. Cette transformation permet de traiter des données non linéaires. Les noyaux couramment utilisés en reconnaissance faciale sont le noyau gaussien (RBF) ou encore le noyau polynomial (Y. Wang and Y. Zhang, 2010).
Bien évidemment, il existe d’autres techniques comme le Kernel-LDA, Locally Linear Embedding (LLE) ou encore la Local Tangent Space Analysis (LTSA). Les plus connues sont représentées sur la figure suivante, et présentées au sein de la thèse doctorale de Mebarka Belahcen (2013).

![unnamed](https://github.com/julienpillis/Veille_techno_RF/assets/73343827/ad32ce46-82b8-4efe-826f-8f34b46c9ad1)
<br><i>Lien du graphe : <a href="https://go.stemic.app/maps/1bf0a933-a027-426c-95fa-daad89119f85">Extraction des caractéristiques</a> </i>

L’avantage des techniques non-linéaires est qu’elles permettent (généralement) d’obtenir de meilleurs résultats que les techniques linéaires (Y. Wang and Y. Zhang, 2010).

Les méthodes globales sont rapides et permettent de représenter un visage, en d’en extraire les caractéristiques, assez simplement. Cependant, leur sensibilité aux variations d’éclairement, de pose ou encore d’expression faciale peut rendre l’authentification difficile.
