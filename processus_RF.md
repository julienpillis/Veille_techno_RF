# Principe de fonctionnement d’un système de reconnaissance faciale

Un système de reconnaissance faciale fonctionne selon deux modes principaux : le mode d'enrôlement et le mode d'authentification. (Belahcen Mébarka, 2013)

<ul>
<li><b>Mode d'enrôlement</b> : Tout comme le système visuel humain, un système de reconnaissance faciale doit comprendre une phase d’enrôlement au cours de laquelle il associe les caractéristiques d'un visage à l'identité d'un individu. Cette étape est réalisée chez les êtres humains d’une façon spontanée. Dans le contexte d'un système artificiel, cette phase consiste à créer une base de données des individus connus. Pour le faire, le système capture et convertit les traits discriminatoires d'un individu en une structure de données unique, appelée "signature". Cette signature est ensuite stockée dans la base de données.</li>

<li><b>Mode d'authentification</b> : Dans ce mode, le système décide si l’individu est connu ou non. Il compare alors la nouvelle signature obtenue avec celles présentes dans la base de données.</li>

</ul>


La reconnaissance faciale s'articule autour de quatre modules majeurs. Trois modules appliquent des traitements similaires, que l’on soit dans le mode enrôlement ou le mode authentifié.

Le premier module <b>‘Acquisition des images’</b> consiste à capturer des images d’un individu. Dans le deuxième module <b>‘Détection et prétraitement’</b> le système détecte le visage dans l'image brute fournie, réalise une série de prétraitements pour améliorer la qualité et supprimer le bruit, et ensuite il transmet au troisième module une image focalisée uniquement sur le visage. Dans le troisième module <b>‘Extraction des caractéristiques’</b>, le système extrait la signature discriminante du visage qui lui permet de distinguer un individu d’un autre. Selon le mode opératoire – enrôlement ou authentification – cette signature est soit conservée dans la base de données, soit transmise au quatrième module pour <b>classification</b>. Ce dernier émet alors une décision finale : soit le visage est identifié comme étant celui d'une personne enregistrée, soit il est considéré comme inconnu.


![unnamed](https://github.com/julienpillis/Veille_techno_RF/assets/73343827/5e8b4e41-46ab-4819-a121-19fe4b926873)
<br><i>Lien du graphe : <a href="https://go.stemic.app/maps/4eff94d3-1888-411c-a286-a972cce156a4">Processus de reconnaissance faciale</a> </i>

Nous présenterons par la suite, les principales méthodes proposées dans la littérature pour constituer chaque module.

