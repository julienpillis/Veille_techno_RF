# Extraction à partir de modèles 3D

Plus récemment, les systèmes RF intègrent de plus en plus de capteurs 3D. La raison principale est la baisse du coût de ces capteurs,
et l’augmentation du taux de réussite d'authentification. Effectivement, la reconnaissance 3D de visages constitue une alternative prometteuse à 
la reconnaissance 2D puisqu'elle permet de collecter les données de profondeur, et d’obtenir des mesures précises. Les systèmes 2D doivent notamment
faire face au  problème A-PIE ( ge, Pose, Émotions, Intensité (éclairage))( BBC EARTH LAB, 2015).
Il semble donc cohérent de dire que les modèles 3D offrent une meilleure résistance aux variations d'éclairage et à la pose.
Cependant, les algorithmes de reconnaissance de visage en 3D sont généralement plus complexes. Il est difficile de les intégrer dans les
systèmes embarqués ou à temps réel.


Les méthodes 3D combinent en général les données 3D récupérées et les techniques d’extraction 2D présentées précédemment. 
On retrouve majoritairement des techniques s’appuyant sur le profil (le profil de visage fournit des informations complémentaires de 
structure et de forme qui ne sont pas visibles sur la vue frontale) sur les caractéristiques géométriques et sur la couleur et la profondeur.
Un tel système est présenté par Tsalakanidou, F., Malassiotis, S., & Strintzis, M. G (2005). Les algorithmes se basent très souvent sur le même
principe. Ils utilisent un modèle Hidden Markov Model (HMM) pour l’extraction des traits caractéristiques du visage. Pour rappel, c’est une méthode 
que l’on utilise sur des images 2D. Cependant, ici, la méthode proposée simplifie le traitement des données 3D en les considérant comme une image 2D,
avec des valeurs de pixels correspondant à la distance de la surface de la tête humaine par rapport au plan de la caméra. Le modèle HMM sera 
directement appliqué sur cette image 2D, qui comporte en plus des données 3D.
