En arrivant à cette séance, nous avions reçu de nouveaux solénoïdes: (modèle KK-0630B, 24V, 8 Newton, 400 mA, 10 mm de course) plus puissants que les solénoïdes que nous utilisions pour les slingshots. Ces solénoïdes seront utilisés pour créer nos 3 bumpers. Ce sont des pièces que l’on retrouve sur tous les flippers qui sont situées en haut de la table de jeu disposées en triangle et qui permettent de marquer des points. Leur fonctionnement est le suivant, lorsque la bille touche un bumper, le joueur va marquer des points et la bille va être renvoyée dans la direction opposée grâce à un mécanisme qui s'abaisse sur la bille et remonte immédiatement ensuite (voir schéma ci-dessous).

<img src="Images des rapports/Images séance 3/schema_explicatif_bumpers.jpg" width="300">

Ceux-ci sont disposés assez proches les uns des autres de manière à ce que la bille fasse des aller retours d’un bumper à un autre plusieurs fois afin de marquer des points à la suite. 


Ainsi durant cette séance nous avons effectué de nombreuses recherches sur les différents mécanismes possibles pour les fabriquer. Pour les réaliser, nous avons décidé d’utiliser un solénoïde placé verticalement sous la planche (maintenu par une équerre) et attaché à une pièce plastique passant à travers la planche qui va s'abaisser sur la balle lorsqu’il y a un contact. Pour détecter ce contact, nous pensons utiliser du scotch de cuivre collé en dessous des bumpers (utilisé comme conducteur) et créer un petit anneau métallique relié au 5V de l’arduino et attaché à la partie haute du bumper. Ainsi quand la bille métallique sera en contact à la fois avec le scotch de cuivre et l’anneau métallique, la bille fermera le circuit . La lecture du courant dans ce petit circuit sur une entrée digitale de l’arduino permettra de détecter lorsque le circuit est fermé. Suite à ce contact ou pourra alors incrémenter les points du joueur et enclencher le solénoïde correspondant pour renvoyer la balle.  


Nous avons trouvé ce modèle 3d qui correspond exactement à ce que l’on souhaite faire : https://www.thingiverse.com/thing:3286052.
Nous devrons cependant l’adapter pour que les dimensions des pièces et des trous permettent d’y fixer nos solénoïdes qui ne sont pas les mêmes.

<img src="Images des rapports/Images séance 3/solenoide_KK0630B.jpeg" width="300">

Nous avons mis un certain temps à trouver une alimentation pour ces nouveaux solénoïdes, en effet la première alimentation utilisée indiquait une tension de 24V alors que sa tension réelle mesurée avec un multimètre était de 60V. Nous avons finalement trouvé une alimentation délivrant une tension réelle de 24V et un courant de 2.2A, ce qui nous a permis de tester les nouveaux solénoïdes reçus. Cependant il y a un mauvais contact au niveau du connecteur de la nouvelle alimentation, nous devons donc trouver une solution à ce problème d’ici la prochaine séance. 


Nous avons aussi rencontré une petit difficulté avec les nouveaux solénoïdes, la documentation de ceux-ci affichait une course de 10mm mais en réalité les moteurs ne pouvaient effectuer qu’un mouvement de 5mm, pour régler cela il suffisait de retirer un des 2 écrous et caoutchoucs restreignant la course du solénoïde présents au bout de la tige du solénoïde.


J’ai ensuite pu tester et imaginer le fonctionnement d’un bumper à l’aide d’un de ces solénoïdes. Voici le résultat avec cette petite vidéo montrant simplement comment celui-ci fonctionnera (pour le moment le solénoïde est déclenché manuellement). Le circuit électronique est toujours le même que pour le solénoïde des slingshots à l’exception que l’alimentation utilisée fourni une tension de 24V au lieu de 12V) : https://www.youtube.com/shorts/0AeFL3rPPoE.

Pour les prochaines séances, je vais essayer d’imprimer des pièces en plastiques permettant de fixer ces solénoïdes sous la planche et d’adapter les modélisations 3D des bumpers à nos solénoïdes pour pouvoir effectuer des premiers tests.


En fin de séance, j’ai décidé du placement des micro-interrupteurs sur le prototype du slingshot créé à la séance précédente et j'ai trouvé des vis à bois adaptées permettant de viser directement les micro-interrupteurs sur la planche sans nécessairement avoir besoin de perçer des trous.


Finalement j’ai modifié le fichier 3d de la poignée utilisée pour le lanceur manuel de billes afin d’y ajouter une tige qui rentre dans le ressort. Nous avions initialement prévu de coller à la poignée une tige en bois mais n’ayant pas trouvé de tige aux bonnes dimensions et pour avoir un ensemble poignée + tige plus robuste nous allons l’imprimer en plastique sur la même pièce que la poignée. Le petit cube au bout de la tige permettra d’y emboîter une autre pièce qui va frapper la bille. Remarque : la pièce sera peut être encore modifiée pour la rendre plus facile à imprimer en 3D et éviter l’impression de supports. Voici la nouvelle poignée modélisée en 3d : 

<img src="Images des rapports/Images séance 3/poignee+tige.jpg" width="300">


Après la séance, j’ai reçu un solénoïde qui servira à faire bouger les flippers (modèle KK64B, 24V, 2A, 20mm de course, 65Newton). J’ai pu le tester avec l’alimentation de 24V et voici le résultat en vidéo ( le code utilisé est le même que celui de la première séance (disponible sur le github) : lorsque le bouton est appuyé une tension est envoyée au solénoïde pour l’activer jusqu’à ce que le bouton soit relâché). https://www.youtube.com/shorts/n7QumtdJi2Y


