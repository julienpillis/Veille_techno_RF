# Extraction des traits discriminatoires

Un fois le visage détecté et éventuellement normalisé, il est nécessaire de le capturer afin de le comparer avec ceux d’une base de données pour 
authentification. Par capture, nous entendons extraction des points caractéristiques, que l’on appelle plus communément : <b>traits discriminatoires</b>,
puisqu’ils permettent de différencier un visage d’un autre. 

Cette extraction dépend généralement du format d’acquisition du visage à savoir si le modèle du visage est en 2D ou en 3D. 
Cependant, nous verrons que l’utilisation de réseaux de neurones peut convenir pour ces deux formats.
