Effibox
=======

Contents:

.. toctree::
   :maxdepth: 3

TODO: traduction et mise en forme !!!

Traduction RobotML → aroccam :
Application aroccam générée
Le traducteur crée une application aroccam complète, contenant :
	les abonnements aux capteurs utilisés dans la modélisation
	l'ensemble des classes du modèle qui concernent le middleware
	les datatypes standards et les datatypes personnalisés
Concernant l'organisation des fichiers de l'application, voici un exemple d'application générée :

.. figure:: Effibox_images/tree.png
   :width: 300px
   :align: center
 
Dans le répertoire « src » figure l'ensemble des fichiers sources c++ :
	RoboCabApplication.*pp est la classe principale
	Les structures de données (standard et personnalisées) sont rangées dans un sous-répertoire Datatypes
	Les composants du modèle sont rangés dans un sous-répertoire Software
Correspondance entre le modèle et le code généré :
Les composants :
Un composant proteus est traduis comme une classe c++. Les constituants du composant sont déclarés comme attributs de classe :
	instance de chaque sous composant
	inputs ports
	outputs ports
	connexions internes et externes entre composants
	machine d'état et transitions
Les ports :
Output port :
Chaque output port est traduit par un objet de communication Aroccam nommé TaskBuffer. A cet objet on associe une ou plusieurs fonctions de traitement. A chaque fois qu'une donnée est ajoutée au TaskBuffer (méthode push), toutes les fonctions de traitement associées sont exécutées en parallèle.

Input port :
un input port est traduis comme une méthode de la classe correspondant au composant. Cette méthode peut être associé à un output port comme fonction de traitement. Elle est ainsi automatiquement appelé sur un événement transmis par le output port connecté.
Connexions :
Interne :
A l'intérieur d'un macro-composant, plusieurs sous-composants peuvent voir leurs ports d'entrée/sortie connectées entre elles. La connexion consiste simplement à associer un input port à un output port, grâce à la méthode addFunctionToExecute de la classe TaskBuffer (voir output port).
Exemple :
//inner components connexions
pathPlanner.pathDef->addFunctionToExecute(boost::bind(&LocalisationModule::pathDefIn, &localisation, _1));

Externe :
Dans un macro-composant, une connexion externe est un lien entre une entrée d'un composant interne et une entrée du macro-composant, ou bien entre une sortie d'un composant interne et une sortie du macro-composant.
	Une connexion externe de type « entrée-entrée » est traduite en codant l'input port du macro-composant comme une méthode « tremplin » qui appelle la méthode correspondant à l'input port du sous-composant.
	Une connexion externe de type « sortie-sortie » est traduite en codant l'output port du macro-composant comme un pointeur vers l'input port du composant interne.
State Machine :
Les noms d'états sont traduis dans une structure enum. Les transitions sont implémentées comme des méthodes. Si une méthode contient déjà un contenu c++ dans la modélisation, ce contenu est copié.

Limitation :
	seuls les contenus c++ des fonctions de transition sont copiés. Si le contenus est écrit dans un autre langage il sera ignoré.
	Le changement d'état n'a pour le moment pas été correctement implémenté.
Datatypes :
	Datatypes proteus : les datatypes proteus sont convertis en structures c++, utilisant des type standards du langage c++. Ainsi il peut y avoir des différences entre les datatypes de la modélisation et les datatypes après traduction.
	Datatypes utilisateurs : les datatypes définis par l'utilisateur sont construits de la même manière, en se basant sur les datatypes proteus traduis.
Algorithmes externes :
Non gérés par le traducteur pour le moment.
Service Port
Non gérés par le traducteur pour le moment.
Déploiement :
-	Tous les composants contenant les stéréotypes suivants sont générés comme abonnement capteur : CameraSystem, GPSSystem, InertialMeasurementUnitSystem, InertialNavigationSystem, OdometrySystem (voir paragraphe suivant).
-	Tous les composants alloués sur la plateforme AROCCAM sont générés en temps que composant, quels que soient leur stéréotype.
Connexions aux capteurs :
Les connexions aux capteurs sont traduites comme des abonnements aroccam. Ils se retrouvent dans le fichier xml de description de l'application aroccam, le ficher .awp.
Les fonctions de traitement associés aux capteurs sont codées dans la classe principale de l'application. Dans chaque fonction, les types aroccam sont convertis en type RoboML. C'est ici que sont connectés les flux de données sur les entrées des composants instanciés.

Certaines contraintes sont à respecter pour que les connexions des données capteurs fonctionne correctement :
- Il faut qu'une Imu transmette le datatype Imu
- Il faut qu'une Gps transmette le datatype NavSatFix
- Il faut qu'un capteur odometrie transmette un CarLikeOdometry pour le vipalab ou bien un DifferentialOdometry pour le cas du wifibot
- Il faut qu'une Camera transmette une Image.
- Il faut qu'un télémètre laser transmette un LidarScan

