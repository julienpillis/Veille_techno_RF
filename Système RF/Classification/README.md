# Méthodes d’authentification et de décision

Nous décrivons dans cette section le module “authentification et prise de décision” d’un système de reconnaissance de visages. Après avoir détecté le visage dans l’image et extrait ses attributs caractéristiques, nous présentons ici les méthodes qui permettent de le classifier et de fournir la décision finale : personne inconnue ou personne connue et qui. Les approches proposées dans la littérature pour résoudre ce problème relèvent de la classification automatique de données, champ de recherche largement exploré durant les dernières décennies pour de nombreuses applications.

Les méthodes pouvant être appliquées dans cette étape dépendent principalement de la technique utilisée lors de l’étape d’extraction des signatures. On distingue les méthodes qui sont basées sur le calcul des distances entre les signatures stockées dans la base (mode d'enrôlement) et celle qui a été calculée sur le visage en cours de traitement (en-ligne).

D’autres méthodes interviennent d’une part dans la phase d’enrôlement afin de déterminer a priori, dans l’espace des signatures, les frontières entre les classes correspondant aux différents individus. Cette phase d’enrôlement est qualifiée d’apprentissage. Il s’agit ici d’un apprentissage supervisé du fait que les étiquettes des visages de la base de données sont connues. Une technique de discrimination associée intervient ensuite durant la phase d’authentification, assurant la classification du visage cible à partir des connaissances acquises durant l’apprentissage. Parmi ces méthodes, nous décrirons les deux plus utilisées, à savoir les classifieurs exploitant un réseau de neurones et les séparateurs à vastes marges (SVM).


## Méthode de distance : 
La méthode de calcul des distances est utilisée dans les méthodes linéaires d’extraction des données. Elle s’applique pour déterminer les degrés de ressemblance. Selon le cas, la distance peut être calculée entre deux signatures, ou entre une signature et un ensemble de signatures. La première option s’applique dans les méthodes qui assignent une signature unique à chaque individu durant la phase d’enrôlement, indépendamment du nombre d’images disponibles pour cet individu. La deuxième option s’applique lorsqu’une signature est assignée à chaque image de la base et non à chaque individu durant la phase d’enrôlement. 

Dans le domaine de la reconnaissance de visages, les distances entre deux signatures les plus utilisées sont les suivantes (P. N. Belhumeur, J. P. Hespanha and D. J. Kriegman,1997 ) : 
Distance Euclidienne est plus utilisée pour les vecteurs.
Distance City Block  
Distance Mahalanobis
Distance Cosine
Mesure de l’angle
Distance de Yang , version améliorée de distance Euclidienne et spécifique pour les matrices .

Une fois que la distance a été choisie, le problème de la reconnaissance d’un visage cible à partir des signatures stockées dans la base est résolu par la méthode du plus proche voisin.
On calcule ensuite toutes les distances entre la signature du visage cible et les signatures ou ensembles de signatures des individus de la base.
Avec cette technique basique, le visage cible est toujours reconnu, car il existe toujours un individu de la base pour lequel la distance est minimale. Pour pallier ce problème, un seuil de rejet est introduit, c'est-à-dire une borne supérieure pour la valeur de la distance. Si la distance minimale déterminée en balayant la base est inférieure à ce seuil, on considère que l’image de visage a été reconnue, sinon on considère qu’elle ne correspond pas à un individu de la base. 
La distance euclidienne et la distance de Mahalanobis figurent parmi les plus utilisées pour déterminer la similarité entre une signature et un ensemble de signatures. Elles ont été employées conjointement avec toutes les méthodes globale dans l’extraction de signatures, les méthodes Eigenface (Nicolas Morizet; Frederic Amiel; décembre 2007). Quant à la technique de FisherFaces, la distance euclidienne est la plus utilisée pendant la phase de reconnaissance (P. N. Belhumeur, J. P. Hespanha and D. J. Kriegman,1997).

### Cas de K Plus Proches Voisins « KPPV » ou K Nearest Neighbor KNN
C’est une approche très simple et directe. Elle ne nécessite pas d’apprentissage mais simplement le stockage des données d’apprentissage. L’algorithme KNN figure parmi les plus simples algorithmes d’apprentissage artificiel. L’objectif de l’algorithme est de classer les exemples sur la base de leur similarité avec les exemples déjà classés.
Les données sont représentées à travers des points, les points qui sont proches les uns des autres présentent des éléments en commun. (Guerfi, Souhila,2008)
Avec le jeu de données en entier précédemment fourni, l'algorithme va pouvoir effectuer une prédiction en cherchant les K instances du jeu de données les plus proches de l'observation souhaitée. Ainsi une distance est calculée entre le vecteur à classer et tous les vecteurs déjà classés, puis les k vecteurs pour lesquels la distance est la plus petite sont déterminés, après détermination de la classe la plus représentée parmi ces k vecteurs, le vecteur est  affecté à cette dernière.

### Description d’un scénario d’authentification  : 
<ol>
<li> Le client introduit son signature (une ou plusieurs image du clients est prises pour identifier son signature) </li>
<li> La sauvegarde de l'identifiant dans la base de données </li>
<li> Acquisition de l’image du visage du client. </li>
<li> Application des prétraitements sur les deux dimensions. </li>
<li> Calcul du vecteur propre en appliquant les prétraitements. </li>
<li> Calcul de la valeur par un classificateur. </li>
<li> Chargement du seuil. </li>
<li> Comparer la valeur avec le seuil. </li>
<li> Client connu ou imposteur. </li>
</ol>

## Support Vector Machine (SVM) : 
Un SVM  est une méthode de classification supervisée, particulièrement bien adaptée pour traiter des données de grande dimension. Les SVM ont été introduits par Vapnik en 1995 (Sang-Ki Kim, Youn Jung Park, Kar-Ann Toh, Sangyoun Lee ,2010).
Le fonctionnement d'une machine à vecteurs de support repose sur une idée simple : trouver un hyperplan qui permet de diviser de façon optimale un jeu de données en deux ou plusieurs classes différentes. 
Dans un SVM, les données sont séparées en différentes classes en ayant recours à la notion de marge maximale. La marge représente la distance entre la ligne de séparation des données et le point le plus proche de l'un des ensembles. La frontière de séparation des classes est choisie de façon à maximiser la distance entre les groupes de données.
Ce classificateur est utilisé pour les techniques non linéaires présentées dans la partie précédente (Kernel-PCA, Kernel LDA…).





## Corrélation de Pearson : 
Plusieurs systèmes dépendent de leur coefficient de corrélation de Pearson pour la reconnaissance faciale. Dans ces systèmes, l'étape de reconnaissance se fait en calculant la corrélation de Pearson Coefficients entre les mesures géométriques de l’image test et les mesures stockées dans la base de données d’entraînement. Le système acceptera une image faciale de la personne comme authentifiée si le pourcentage de corrélation est supérieur à un seuil choisi sinon il rejette l'image. [Kamel Hussein Rahouma a, Amal Zarif Mahfouz , 2021].

## Cas de méthode LBP : 
Dans le cas de LBP (Local Binary Pattern) , les caractéristiques des images sont représentées sous forme d’histogrammes. Si le vecteur de caractéristiques de test d’entrée correspond au modèle formé, il reconnaît le visage et récupère les informations sur cette image à partir de la base de données. Le classificateur formé vise à faire correspondre l'image avec les images du modèle formé qui est calculé par l'une des méthodes suivantes: l'intersection d'histogrammes, statistique log-vraisemblance, statistique Chi-deux(X2). [Solofoniaina Nomenjanahary Sarobidy, Edouard, 2022]

## Cas des réseaux de neurones artificiels :  
Les classifieurs des réseaux de neurones se distinguent des autres classifieurs. En effet, les réseaux des neurones n’ont pas besoin d’une méthode de mesure de distance entre les signatures puisque  eux-mêmes permettent de calculer implicitement une distance entre les signatures.  

Dans cette méthode , un réseau de neurones identifie un individu, alors il existe autant des réseaux de neurones que d'individus. Durant la phase d'enrôlement , le système adapte les paramètres de chaque réseau de neurones. Ensuite, durant l’authentification de visage cible , le système présente celui-ci en entrée du réseau de neurones du visage proclamé. 

Les caractéristiques sont transmises à travers des couches entièrement connectées (fully connected layer), qui effectuent la tâche de classification. Ces couches produisent une probabilité pour chaque classe possible,c'est-à-dire pour chaque personne présente dans notre base de données. Cette sortie est ensuite comparée à un seuil, pour prendre la décision finale. Ce seuil permet de décider de la précision que l’on souhaite pour prendre la décision. Par exemple, si le seuil est à 0.9, le modèle effectue la tâche de reconnaissance faciale uniquement lorsque sa performance lors de l’association de l’image à une personne en particulier est supérieure à cette valeur. 

L’architecture discriminante RNA a été utilisée par de nombreux auteurs. Mazloom et Ayat (2008) ont développé une architecture multi-couches pour classifier des signatures issues d’une analyse en composantes principales . D’autres chercheurs ont utilisé un RNA discriminant dont les fonctions d’activation sont à base radiale (réseau RBF), sur des signatures extraites par une transformée en ondelettes [I. Paliy, A. Sachenko, V. Koval, et Y. Kurylyak 2005], ou encore par une transformée en cosinus [, M. J. Er, W. Chen, et S. Wu. , 2005].
