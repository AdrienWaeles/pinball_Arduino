**Avant la séance :**

Tout d’abord j’ai pu tester l'écran LCD afin d'afficher des messages et d'actualiser le nombre de points. L'écran est branché à un module I2C ainsi il ne suffit que de 2 câbles de communication branchés aux entrées analogiques de l'arduino en plus de son alimentation: (sur une carte Arduino Uno la broche SDA est connectée au port analogique A4 de la carte et la broche SCL au port A5). Au début l’écran ne semblait pas fonctionner, aucun message ne s'affichait, mais il suffisait de tourner la petite vis au dos pour ajuster le contraste. Voici un programme simple de test :

<img src="Images des rapports/Images séance 5/code_test_lcd.jpg" width="500">

La fonction afficheScore(int score) permet d’afficher simplement n’importe quel score à l’écran. Elle est appelée dans le void setup avec la valeur 0 car toute partie commence avec 0 points. Pour effectuer des tests j’ai écrit une boucle for dans le void loop qui incrémente un nombre de points de 100 toutes les secondes jusqu'à 10000. Cette fonction pourra être optimisée par la suite.

<img src="Images des rapports/Images séance 5/test_lcd.jpg" width="300">



Pendant les vacances de Noël, j’ai travaillé sur la fabrication des flippers. Pour les modéliser j’ai utilisé les dimensions réelles d’un flipper. J’ai décidé de diviser le mécanisme en 3 pièces : le flipper qui est la pièce frappant la balle muni d'une tige hexagonale qui vient s'emboîter dans la pièce suivante.

<img src="Images des rapports/Images séance 5/flipper_modelisation.jpg" width="300">

La 2ème pièce est un “bras” de flipper, elle est située sous la planche et va permettre de transformer le mouvement de translation du solénoïde en mouvement de rotation. Elle est reliée au solénoide par une 3ème pièce qui tourne autour de son axe.

<img src="Images des rapports/Images séance 5/bras_flipper_modelisation.jpg" width="300">

La 3eme pièce permet de relier le solénoïde au bras du flipper.
Pour cela j'insère cette 3eme pièce dans la 2eme en effectuant une pause dans l'impression 3d pour que cette pièce soit prisonnière dans la 2eme et puisse tourner autour.  Cela permet d’éviter l’ajout de vis supplémentaires. Cette pièce est essentielle car je ne pouvais pas attacher facilement directement le solénoïde qui se déplace linéairement à une pièce qui effectue un mouvement de rotation.

<img src="Images des rapports/Images séance 5/attachebras_flipper_modélisation.jpg" width="300">

Voici une vue de la planche de dessous de l’ensemble solénoide + attache_bras + bras de flipper : 

<img src="Images des rapports/Images séance 5/flipper_mecanisme+solenoide.jpeg" width="300">

J’ai également modélisé une équerre permettant de fixer le solénoïde sous la planche. J'ai rencontré des difficultés pour placer correctement le solénoïde, en effet celui-ci doit être positionné précisément pour que l’axe de la pièce imprimée en 3d ne subisse aucune force supplémentaire, sans cela le solénoïde se bloque et ne revient pas en position initiale grâce à son ressort. Afin de régler le positionnement du solénoïde plus facilement j’ai décidé de remplacer les trous circulaires sur la modélisation de l’équerre pour les remplacer par des rainures. Il suffira alors d’utiliser des rondelles sous les vis pour s’assurer que la pièce soit correctement fixée. J'ai pu alors fixer le solénoïde sur la planche en y perçant un trou et en vissant l'équerre. 

<img src="Images des rapports/Images séance 5/flipper_equerre.jpg" width="300">



Voici le test du flipper dans une courte vidéo :
https://youtube.com/shorts/JcDkgeMB18o


J’ai ensuite ajouté une encoche circulaire dans la pièce de modélisation du bumper sur Blender qui permet d'y insérer un fil électrique sur lequel la bille va faire contact. J'ai également dû modifier la hauteur de la pièce pour que la bille soit bien en contact avec la planche et le fil du bumper. 

<img src="Images des rapports/Images séance 5/bumper_encoche_fil.jpeg " width="300">


Etant donné que le slingshot (pièce dotée d'un élastique qui va renvoyer la bille dans la zone de jeu en tendant l'élastique) ne renvoyait pas la bille assez fort en raison de la faible course du solénoïde utilisé (10mm) et de sa force peu élevée (8 Newton). 
Suite aux conseils de nos professeurs, j’ai complètement repensé le modèle 3d du slingshot pour y intégrer un système de levier. Celui-ci permet d’avoir une plus grande amplitude de mouvement et une force plus élevée. Pour cela j’ai d’abord réalisé un prototype dans lequel j’ai effectué plusieurs trous pour tester l’emplacement et la longueur optimaux de la barre sur laquelle le levier va effectuer son pivot. 
Voici le résultat après de nombreux essais et modifications de la pièce imprimée :
https://youtube.com/shorts/K7FTkk97wYo

J’ai finalement remodifié la pièce imprimée en tenant des compte des améliorations effectuées pour avoir une pièce propre que je puisse réimprimer également pour le 2ème slingshot. 
Voici l’équerre du solénoide du slingshot modélisée ainsi que le levier :

<img src="Images des rapports/Images séance 5/equerre_slingshot.jpg" width="300">

<img src="Images des rapports/Images séance 5/levier_slingshot.jpg " width="300">


Etant donné qu’il il a fallu passer un temps énorme sur les prototypes pour placer correctement les composants sur la planche. J’ai décidé de créer une maquette en 3D du pinball sur Sketchup afin d’avoir toutes les mesures nécessaires et gagner en temps et précision sur la version finale. J’ai effectué de nombreuses mesures en me basant sur les différents prototypes réalisés lors des séances précédentes pour déterminer la position exacte de chaque composant. J’ai donc importé toutes les pièces précédemment modélisées afin de les placer. Il reste encore quelques éléments qui seront ajoutés bientôt à la maquette.

<img src="Images des rapports/Images séance 5/maquette_flipper_dessus.jpg" width="200"> <img src="Images des rapports/Images séance 5/maquette_flipper_dessous.jpg" width="200">


Finalement j'ai profité de ces vacances pour terminer la modélisation de la poignée sur blender, afin d’avoir une poignée adaptée avec une bonne prise en main.  Cette poignée est liée à une tige autour de laquelle on y place un ressort. Cependant l’imprimer avec sa tige en une seule pièce aurait nécessité beaucoup de supports à l’impression. J’ai donc divisé la pièce en 3 parties avec filetage pour éviter l'ajout de supports et cela permet également d’insérer la tige dans son futur cadre en bois sur la planche. Le filament utilisé est du PLA imitation bois d’où la forte ressemblance avec du bois. Voici les pièces modélisées imprimées en 3D avant montage :

<img src="Images des rapports/Images séance 5/poignee_demontee.jpeg" width="300">

Et voici le tout assemblé (sans utiliser de vis ou de colle puisque tout se visse parfaitement grâce aux filetages).

<img src="Images des rapports/Images séance 5/poignee_montee.jpeg" width="300">

Cette poignée m’a demandé beaucoup de temps car Fusion 360 n’est pas très adapté pour traiter des maillages avec beaucoup de points. J’ai donc dû faire le filetage à part puis l’importer dans blender pour l’insérer dans la poignée en comblant les trous dans la géométrie de la pièce. J’ai également appris à créer des filetages sur Fusion 360. Pour que les 2 pièces puissent se visser facilement après impression il est très important de modifier une des 2 pièces pour réduire l'épaisseur de son filetage (d’environ 1mm) car il y a des écarts de précisions entre une pièce usinée et l’impression en 3D.



**Pendant la séance :**

Pour commencer il a fallu découper la planche du jeu aux dimensions 414 x 800 x 0.5 cm qui correspondent à celles définies lors de l’élaboration de la maquette 3d. Cependant comme expliqué dans le compte rendu précédent, pour les bumpers nous avons besoin d’incruster de fines plaques métalliques à ras de la planche (permettant de détecter si la bille est à la fois en contact avec la plaque et le fil électrique du bumper), et notre planche est trop longue pour rentrer entièrement dans la découpeuse laser. Avec les conseils des gérants du FabLab nous avons décidé de coller 3 petites planches de bois d’une épaisseur de 3mm sur la grande planche afin de pouvoir graver chacune des planches au laser pour ensuite venir les coller sur la grande planche les unes à côté des autres.


Pour placer les capteurs infrarouges, nous utilisons une fine plaque de plexiglas posée à ras de la planche grâce à nouveau à une gravure. J’ai effectué des tests avec un capteur infrarouge en dessous de la plaque de plexiglas pour vérifier que la bille soit toujours détectée à travers la plaque transparente. La bille est correctement détectée si le capteur est positionné à ras de la plaque de plexiglass.

Puis j'ai déterminé les dimensions et la position de cette plaque en fonction de la position des séparateurs de colonnes (pièces noires en haut du flipper sur la maquette).
Redha a ensuite réalisé un fichier vectoriel svg sur Inkscape pour graver et perçer des trous dans la partie supérieure du flipper.

J’ai ensuite continué la modélisation de la maquette 3d du  pinball afin d’y dessiner le contour du flipper ainsi que la zone de lancement. Cela permettra de découper des morceaux de bois aux dimensions voulues plus facilement par la suite.
Pour cela je me suis aidé de différents schémas de construction de vrais flippers afin de créer les arrondis en haut du flipper qui permettront à la balle de sortir de la zone de lancement pour arriver dans la zone de jeu.



J’ai ensuite dessiné la rampe de sortie de billes, celle-ci doit permettre de diriger les billes jusqu’à la zone de lancement. Etant donné que la sortie de jeu des billes (située au niveau des flippers) est bien plus basse que l’emplacement de la bille avant lancement (juste au dessus de la tige de la poignée), nous avons décidé d’utiliser un solénoïde pour pousser la bille et l’amener jusqu’à la zone de lancement. Ce solénoïde sera déclenché à chaque sortie de bille (qui sera détectée grâce à un capteur infrarouge). Celui ci poussera la balle grâce au même bras imprimé en 3d utilisé dans l'ancien prototype du slingshot (pièce noire sur l'image ci dessous) et sera placé au niveau du trou en bas à droite de la maquette.

<img src="Images des rapports/Images séance 5/rampe_sortie_bille.jpg" width="300">



Finalement j’ai modélisé les pièces qui permettront de tendre l'élastique des slingshots en respectant la forme emblématique que l’on retrouve sur tous les flippers. Voici la modélisation sur Fusion 360 : 

<img src="Images des rapports/Images séance 5/slingshot_tendeur.jpg" width="300">
