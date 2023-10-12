# Réseaux de neurones convolutifs

Il s’agit de la première catégorie de réseaux à être introduite dans le domaine de la RF, mais également la plus utilisée. Brièvement, un réseau de neurones utilise des filtres appelés couches de convolution permettant d’extraire les caractéristiques de l’image. Ces filtres sont progressivement déplacés sur l’image pour rechercher des motifs (par exemple des textures) et des traits discriminants. Des techniques présentées précédemment peuvent être utilisées en tant que filtres (filtre de Gabor, K-PCA,...). Ces traits sont passés à travers une fonction d’activation non linéaire (ReLU, Sigmoid ou encore Softmax), c’est-à-dire que l’on “borne” les données (normalisation) pour éviter leur dispersion. Le processus est itéré, étant donné que chaque couche comprend un filtre. Ensuite, des couches de regroupement ou pooling, diminuent la dimensionnalité des caractéristiques apprises par le réseau tout en conservant des informations importantes. Ces couches rendent le CNN moins sensible aux petits changements de position du visage dans l’image. 

Il y a également des couches supplémentaires de classification.

Ces réseaux existent depuis longtemps et sont très nombreux : LeNET, Inception, ResNet, EfficientNet…(Mebarka Belahcen, 2013).
Parmi les CNN, certains se démarquent par leur architecture d’apprentissage multi-tâches (MTL). Ces architecture ont des branches distinctes pour chaque tâche:  (reconnaissance faciale et identification du sexe par exemple), tout en partgeant les mêmes couches de convulsion. Ces réseaux permettent de renforcer la sécurité de l'authentification et la rapidité des systèmes (X. Yin et  X. Liu, 2018).

![unnamed](https://github.com/julienpillis/Veille_techno_RF/assets/73343827/38b010fc-60c7-45b0-bc91-868d32b52544)
