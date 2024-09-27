# GLOSSAIRE

- [Général](#général)
- [Front-end](#front-end)
- [UX / UI](#ux-ui)
- [Architecture](#architecture)
- [Modélisation / Base de données](#modélisation---base-de-données)
- [Symfony](#symfony)
- [Sécurité](#sécurité)
- [RGPD](#rgpd)
- [SEO](#seo)
- [Gestion de projets / DevOps](#gestion-de-projets---devops)
- [English](#english)

## Général
1.	Quel est l’environnement à installer pour exécuter un script PHP ? Citer 2 exemples de logiciels permettant ce contexte
- Laragon ou MAMP (Mac OS) permettent d'obtenir un serveur Apache, necessaire pour un langage comme PHP qui agit coté serveur

2.	Qu’est-ce qu’un algorithme ?  
- Un algorithme est une suite d'instruction visant à atteindre un certain objectif

3.	Qu’est-ce qu’une variable ? Par quel symbole est préfixée une variable en PHP ?
- Une variable est une valeur pouvant prendre plusieurs forme et pouvant changer au court du code, toujours précédé de $ en PHP

4.	Qu’est-ce que la portée d’une variable ?
- La portée d'une variable est la zone de code ou celle-ci peut être citée afin d'être utilisé sans pour autant être redéfinie

5.	Qu’est-ce qu’une constante ? Quelle est la différence avec une variable ?
- Une constante est une valeur mais qui elle ne change jamais

6.	Qu’est-ce qu’une superglobale, combien en existent-ils et donner un exemple d’utilisation 
- $_GET
Cette superglobale permet de récuperer les donnée passé dans l'URL. Par exemple, si l'URL est example.com?nom=Jean, alors $_GET['nom'] va afficher "Jean".

- $_POST
Utilisé pour récuperer les données envoyer via un formulaire en method POST. Par exemple, si un formulaire envoi un champ nommé "email", $_POST['email'] va permettre d'afficher ce qu'y à été saisie.

- $_FILES
Cette superglobale est utilisé pour gérer les fichiers uploadés. Par exemple, $_FILES['fichier']['name'] retourne le nom du fichier que l'utilisateur à téléversé.

- $_COOKIE
Elle permet d'acceder aux cookies stocker sur l'ordinateur de l'utilisateur. Si un cookie nommé "user" existe, $_COOKIE['user'] affiche sa valeur.

- $_SESSION
Les données de session sont stocké dans cette superglobale. Par exemple, $_SESSION['login'] permet d'accéder à la variable "login" stocké dans la session de l'utilisateur.

- $_SERVER
Cette superglobale contient des information sur le serveur et l'environement d'execution. Par exemple, $_SERVER['HTTP_USER_AGENT'] permet d'afficher des informations sur le navigateur de l'utilisateur.

- $_ENV
Utilisé pour accéder aux variables d'environement. Par exemple, $_ENV['PATH'] retourne la variable d'environement "PATH".

- $_REQUEST
C'est une superglobale qui contient les données des arrays $_GET, $_POST et $_COOKIE. Par exemple, $_REQUEST['nom'] peut retourner la valeur d'une donnée qu'y aurais été envoyé via l'un de ces methodes.

- $_GLOBALS
Cette superglobale contient toutes les variables globales de votre script. Par exemple, GLOBALS['variableGlobale'] permet d'accéder à une variable définie à l'extérieur d'une fonction.

7.	Quels sont les différents types (primitifs) que l’on peut associer à une variable en PHP ? Les citer et en donner des exemples (ne pas oublier le type d’une variable sans valeur)
- $string = "string"
- $integer = 10 integer
- $float = 1,01 float
- $pasDeValeur = null
- $array = [1,2,3,4,5]
- $boolean = true
- $object = new Object

8.	Existe-t-il plusieurs types de tableaux en PHP, si oui lesquels ?
- Oui Associative et Indexed, les tableaux associatifs possèdent des clés en string, et les indexed possedent des clés en int qui commencent à 0.

9.	Quelles sont les différentes structures de contrôles qu’il existe en algorithmie ? Donner un exemple pour chacune d’entre elles
- IF 

if($age >= 18) {

    $resultat = "majeur";
} else {

    $resultat = "mineur";
}

- WHILE 


while($j <= 10) {

    echo $j." ";
    $j++;
}

- FOR

for($i = 1; $i <= 10; $i++) {

    echo $i." ";
}

- FOREACH (tableau)

foreach(range(1,10) as $v) { 

    echo $v." "; 
}

- SWITCH 

switch($valeur) {

    case 0: echo "KO !<br>"; break;

    case 1: echo "OK !<br>"; break;

    default: echo "Valeur non gérée !<br>";
}

10.	Quelle est la fonction PHP permettant de demander la longueur d’une chaîne de caractères ?
- strlen()

11.	Qu’est-ce qu’une session ? Quelle fonction permet de démarrer une session en PHP ? Donner un exemple d’utilisation en PHP
- Une session est active quand un utilisateur utilise une application ou un site web, elle permet de garder des informations de l'utilisateur si par exemple il utilise le site web dans une autre page.  On ouvre une session en PHP avec la fonction session_start()

12.	Qu’est-ce qu’un cookie ? Donner un exemple d’utilisation en PHP
- Petit fichier texte stocké sur l'ordinateur de l'utilisateur par son navigateur.

- // Créer un cookie nommé "utilisateur" avec la valeur "Jean" qui expirera dans 7 jours
- setcookie("utilisateur", "Jean", time() + (86400 * 7), "/");

13.	Quelle est la différence entre les instructions « require » et « include » en PHP
- include : génère un avertissement et continue l'exécution du script si le fichier est manquant.
- require : génère une erreur fatale et arrête l'exécution du script si le fichier est manquant.

14.	Comment effectuer une redirection en PHP ?
- header("Location: lien");

15.	Définir la partie « front-end » et « back-end » d’une application
- Le front-end définit le code qui se refletera visuellement sur la page mettant en lien l'utilisateur au site web, le back-end lui définit le code mettant en lien le site web au serveurs

16.	Définir le contrôle de version ? Qu’est-ce que Git ?
- Contrôle de version : suivi des modifications de fichiers.
- Git : système de contrôle de version distribué qui permet de gérer les versions d'un projet, suivre les changements

17.	Qu’est-ce qu’un CMS ? Citer au moins 2 exemples
- Content Management System : logiciel qui permet de créer, gérer et modifier le contenu d'un site web sans nécessiter de connaissances en programmation,
WordPress, 
Joomla!

## Front-end
18.	Définir HTML
- Langage informatique qui nous permettra d'ajouter le contenu principal du site

19.	Définir CSS
- Langage informatique qui va reprendre le contenu de l'HTML et visuellement l'adapter pour le rendre plus esthétique, gérer la mise en page ainsi que la mise en forme de la vue

20.	Définir Javascript
-langage de programmation qui permet d'ajouter des interactions sur les pages web.

21.	Définir JSON. Dans quel contexte ce format est-il utilisé ? 
- JavaScript Object Notation : format de données textuelles utilisé pour échanger des informations entre serveurs et clients, principalement pour les API web et la configuration de données

22.	Peut-on interpréter du Javascript côté serveur ? Si oui, comment ?
- en utilisant Node.js, une plateforme qui permet d'exécuter JavaScript en dehors du navigateur.

23.	Qu’est-ce qu’un sélecteur CSS ?
- Un selecteur designe l'élément d'un document afin d'y apporter des modifications

24.	Quelle balise HTML permet de créer un lien hypertexte ?
- <.a href = "URL">Lien<./a> (pour Achor element).

25.	Qu’est-ce qu’une requête AJAX ?
- Asynchronous JavaScript and XML : permet de charger des données en arrière-plan sans recharger la page web avec des requetes HTTP en JS.

26.	Quel sélecteur CSS permet de sélectionner tous les éléments d’une classe spécifique ? D’un identifiant spécifique ?
- .nomDeClasse {} 
#nomID {}

27.	Définir le responsive design
- Permet d'adapter l'affichage à toute taille d'écran avec des mediaqueries en mettant en place des breakpoints pour modifier le CSS

28.	Qu’est-ce que le templating ?
- consiste à utiliser des modèles pour créer du contenu web de manière dynamique, en séparant le design des données

29.	Qu’est-ce qu’une fonction anonyme en Javascript ?
- c'est une fonction sans nom souvent utilisé comme argument d'une autre fonction

30.	Quelle méthode JavaScript est utilisée pour ajouter un élément à la fin d'un tableau ?
- push()

31.	Qu’est-ce qu’un « media query » ?
- fonctionnalité CSS qui permet d'appliquer des styles différents en fonction des caractéristiques du périphérique

32.	Qu’est-ce qu’un pseudo élément en CSS ?
- mot-clé ajouté à un sélecteur pour spécifier des parties particulières d'un élément, comme ::before ou ::after, permettant d'ajouter du contenu ou des styles supplémentaires sans modifier le HTML.

33.	Qu’est-ce que Bootstrap ? Donner d’autres exemples équivalent
- Bootstrap est un framework CSS open-source, Foundation, Bulma

34.	Quand un formulaire HTML est créé, quelles sont les 2 méthodes qui peuvent lui être associées ? Donner la différence entre ces 2 méthodes
- GET : Les données sont ajoutées à l'URL et sont visibles. Limité en taille.
- POST : Les données sont envoyées dans le corps de la requête, plus sécurisé et sans limite de taille.

## UX UI
35.	Quelle est la différence entre UX Design et UI Design ?
- UX Design : Optimisation de l'expérience et de l'usabilité. on parle ici de l'experience utilisateur, comme la disposition de la page
- UI Design : Conception visuelle et esthétique de l'interface. comme la direction artistique du site, les couleurs et les polices d'ecritures

36.	Qu’est-ce qu’un wireframe ? 
- Un wireframe est un croquis simplifié montrant la structure d'une page web ou d'une application.

37.	Qu’est-ce qu’un prototype ? 
- maquette interactive testant les fonctionnalités et le design.

38.	Qu’est-ce que la hiérarchie visuelle en UI Design ?
- La hiérarchie visuelle guide l'œil de l'utilisateur en mettant en avant les éléments importants

39.	Qu’est-ce que l’accessibilité en UX Design ? 
- rendre les interfaces utilisables par tous, y compris les personnes avec des handicaps.

40.	Qu’est-ce qu’une grille de mise en page ?
- système de lignes et de colonnes utilisées pour organiser et aligner les éléments d'une page web de manière cohérente et structurée.

41.	Qu’est-ce que la notion d’affordance en UX Design ?
- désigne la capacité d'un élément à suggérer sa fonction à l'utilisateur, par ses caractéristiques visuelles ou son design.

42.	Qu’est-ce qu’un « mobile first design » ?
- optimise d'abord la conception pour les appareils mobiles avant de l'adapter aux écrans plus grands.

## Programmation orientée objet (POO)
43.	Donner une définition de la programmation orientée objet 
- organise le code en objets avec attributs et méthodes pour améliorer la modularité et la réutilisabilité.

44.	Qu’est-ce qu’une classe ? Comment la déclare-t-on ?
- structure définissant les attributs (données) et les méthodes (fonctions) que les objets créés à partir de cette classe posséderont.

- class MaClasse {
-     public $attribut;
-     public function maMethode() {}
- }

45.	Qu’est-ce qu’un objet ?
- Un objet est une instance d'une classe, contenant des attributs (données) et des méthodes définis par la classe.

46.	Définir la notion de propriété / attribut / méthode
- Propriété / Attribut : Donnée ou caractéristique d'un objet.
- Méthode : Fonction ou comportement d'un objet.

47.	Qu’est-ce que la visibilité d’une propriété ou d’une méthode ? Citer les différents types de visibilité
- public : Accessible depuis n'importe où, à l'intérieur et à l'extérieur de la classe.
- protected : Accessible uniquement à la classe elle-même et à ses sous-classes.
- private : Accessible uniquement à la classe elle-même.

48.	Quelle est la méthode spécifique utilisée pour créer un nouvel objet à partir d’une classe ?
- Pour créer un nouvel objet, on utilise le constructeur : __construct()

49.	Qu’est-ce que l’encapsulation ?
- L'encapsulation regroupe les données et les méthodes dans une classe, en contrôlant l'accès aux données pour protéger et simplifier le code. Ex modifier une donnée privée d'un objet par une public function

50.	Que signifie « étendre une classe » ? Quelle est le concept clé mis en œuvre ? Donner un exemple
- création d'une nouvelle classe qui hérite des attributs et des méthodes d'une classe existante. Le concept clé mis en œuvre est l'héritage.
- ex : class VoitureElectrique extends Voiture

51.	Définir l’opérateur de résolution de portée
- L'opérateur de résolution de portée (::) en PHP est utilisé pour accéder aux membres statiques, aux constantes de classe, ou aux méthodes d'une classe. Il permet aussi de faire référence à la classe elle-même.

- Accéder à une méthode statique : NomClasse::methodeStatique();
- Accéder à une constante de classe : NomClasse::CONSTANTE;

52.	Définir une méthode / propriété statique
- éléments d'une classe accessibles sans créer d'instance, partagés entre toutes les instances.

53.	Définir le polymorphisme en POO
- permet à des objets de types différents d'être traités de manière uniforme via une interface commune, en utilisant des méthodes avec le même nom mais des implémentations différentes selon la classe.

54.	Définir une méthode / classe abstraite ?
- Classe abstraite : Une classe qui ne peut pas être instanciée directement et qui peut contenir des méthodes abstraites que les classes dérivées doivent définir.
- Méthode abstraite : Une méthode définie dans une classe abstraite sans corps, que les classes dérivées doivent implémenter.

55.	Définir le chaînage de méthodes
- Le chaînage de méthodes permet d'appeler plusieurs méthodes successivement sur le même objet

56.	Qu’est-ce que la méthode __toString() ? Existe-t-il d’autres méthodes « magiques »
- méthode magique en PHP qui permet de définir comment un objet doit être converti en chaîne de caractères lorsqu'on l'affiche
- __construct() : Constructeur de la classe.
- __destruct() : Destructeur de la classe.
- __get($propriete) : Accès aux propriétés non accessibles.
- __set($propriete, $valeur) : Définition des propriétés non accessibles.
- __call($nom, $arguments) : Appel de méthodes non définies.
- __callStatic($nom, $arguments) : Appel de méthodes statiques non définies.
- __isset($propriete) : Vérification de l'existence d'une propriété.
- __unset($propriete) : Suppression d'une propriété.
- __clone() : Clonage d'un objet.
- __invoke() : Appel d'un objet comme une fonction.

57.	Qu’est-ce qu’un « autoload » ?
- Autoload est un mécanisme qui charge automatiquement les classes nécessaires sans inclure manuellement les fichier

58.	Comment appelle-t-on en français les « getters » et les « setters » ?
- getters =  accesseurs
- setters = mutateurs

59.	Qu’est-ce que la sérialisation en PHP ? 
- convertit un objet ou une variable avec serialize() en chaîne de caractères pour le stockage ou la transmission, puis peut être reconverti en objet avec unserialize().

## Architecture 
60.	Qu’est-ce que l’architecture client / serveur ? Grâce à quel type de requête peut-on interroger le serveur. Définir l’acronyme de ce type de requête. Si on ajoute un « S » à cet acronyme, expliquer la différence
- Architecture client/serveur : Le client demande des données au serveur.
- HTTP : Protocole de communication non sécurisé
- HTTPS ajoute une sécurité avec chiffrement.

61.	Donner la définition d’un design pattern. Citer au moins 3 exemples de design pattern
- Un design pattern est une solution réutilisable à un problème courant de conception de logiciel.

62.	Qu’est-ce que l’architecture MVC ?
- Le pattern MVC permet de bien organiser son code source.

63.	Quel est le rôle de chaque couche du design pattern MVC : Model, View, Controller ?
- Modèle (Model) : Gère les données et la logique métier.
- Vue (View) : Présente les données à l'utilisateur et affiche l'interface.
- Contrôleur (Controller) : Gère les interactions de l'utilisateur, met à jour le modèle et rafraîchit la vue.

64.	Quels sont les avantages de l’architecture MVC ?


65.	Existe-t-il des variantes à l’architecture MVC ?
- Oui, MVP, MVVM, MVI

66.	Qu’est-ce qu’une API ? Définir l’architecture REST
- Application Programming Interface : 

## Modélisation - Base de données
67.	Qu’est-ce que la modélisation de données ? Définir la méthode Merise
- Modélisation de données : Création de modèles pour organiser et gérer les données.
- Méthode Merise : Méthode de modélisation en trois niveaux : MCD, MLD, et MPD.

68.	Quelles sont les 3 étapes principales de la méthode Merise ? 
a.	Analyse, conception et réalisation XXXXXXXXXXXXXXXX
b.	Planification, exécution et contrôle
c.	Création, modification et suppression

69.	Qu’est-ce qu’un modèle conceptuel de données (MCD) en Merise ?
- décrit les entités, leurs attributs et leurs relations de manière abstraite, sans se soucier de l'implémentation physique.

70.	Qu’est-ce qu’un modèle logique de données (MLD) en Merise ?
- Le MLD en Merise convertit le MCD en tables et relations spécifiques à une base de données relationnelle.

71.	Donner la définition des mots suivants :
a.	Entité : Objet avec des attributs, représenté par une table.
b.	Relation : Lien entre deux entités.
c.	Cardinalité : Nombre de relations entre entités
d.	Clé primaire / clé étrangère : Identifiant unique d'un enregistrement / Référence à la clé primaire d'une autre table

72.	Que devient une relation de type « Many To Many » dans le modèle logique de données ?
- Une relation "Many To Many" devient deux relations "One To Many" avec une table d'association dans le modèle logique.

73.	Qu’est-ce qu’une base de données ?
- c'est un ensemble organisé de données stockées et accessibles pour gestion et recherche.

74.	Définir les notions suivantes : 
a.	SQL : Langage de requête pour manipuler et interroger des bases de données relationnelles.
b.	MySQL : Système de gestion de base de données relationnelle utilisant SQL.
c.	SGBD (donner 2 exemples de SGBD) : : Logiciel pour gérer des bases de données. MySQL PostgreSQL

75.	Dans une base de données, les données sont stockées dans des tables. Celles-ci sont constituées de lignes appelées enregistrements et de colonnes appelées champs.

76.	Quelle est la différence entre une base de données relationnelle et non relationnelle ?
- Relationnelle : Données dans des tables avec relations, utilisant SQL.
- Non relationnelle : Données flexibles sans schéma fixe, utilisant divers formats.

77.	Qu’est-ce qu’une jointure dans une base de données ? En existe-t-il plusieurs ? Si oui lesquelles ?
- Une jointure combine des données de plusieurs tables en fonction de relations communes.

- INNER JOIN : Retourne les lignes avec des correspondances dans les deux tables.
- LEFT JOIN : Retourne toutes les lignes de la table de gauche, et les correspondances de la table de droite.
- RIGHT JOIN : Retourne toutes les lignes de la table de droite, et les correspondances de la table de gauche.
- FULL JOIN : Retourne toutes les lignes des deux tables, avec les correspondances quand elles existent.

78.	A quoi sert une vue dans une base de données ?
- 

79.	Qu’est-ce que l’intégrité référentielle dans une base de données ?
- assure que les relations entre les tables restent cohérentes en garantissant que les valeurs des clés étrangères correspondent aux valeurs des clés primaires dans les tables liées.

80.	Quelles sont les fonctions d’agrégation en SQL ?
- Les fonctions d'agrégation en SQL permettent de calculer des valeurs sur un ensemble de données. Les principales sont :

- COUNT() : Compte le nombre d'enregistrements.
- SUM() : Calcule la somme des valeurs.
- AVG() : Calcule la moyenne des valeurs.
- MIN() : Trouve la valeur minimale.
- MAX() : Trouve la valeur maximale.

81.	Qu’est-ce qu’un CRUD dans le contexte d’une base de données ?
- désigne les quatre opérations de base pour manipuler des données dans une base de données :

- Create : Ajouter de nouvelles données.
- Read : Lire ou récupérer des données.
- Update : Modifier des données existantes.
- Delete : Supprimer des données.

82.	Quelles sont les clauses qui permettent de :
a.	Insérer un nouvel enregistrement dans une table : INSERT INTO
b.	Modifier un enregistrement dans une table : UPDATE
c.	Supprimer un enregistrement dans une table : DELETE FROM
d.	Supprimer la base de données : DROP DATABASE 
e.	Filtrer les résultats d’une requête SQL : WHERE 
f.	Trier les résultats d’une requête SELECT : ORDER BY
g.	Regrouper les résultats d'une requête SELECT en fonction d'une colonne spécifique : GROUP BY
h.	Concaténer 2 chaînes de caractères : CONCAT()

83.	Comment se connecter à une base de données en PHP ? Quelle est la classe native utilisée ?
- on utilise la classe native PDO (PHP Data Objects).

## Symfony
84.	Qu’est-ce que Symfony ?
- Symfony est un framework PHP pour développer des applications web de manière rapide et structurée.

85.	Sur quel langage de programmation et design pattern repose Symfony ? 
- MVC et PHP

86.	Quelle est la dernière version en date de Symfony ?
- 7.1.4

87.	Qu’est-ce qu’un bundle ? 
- package ou un composant réutilisable qui regroupe des fonctionnalités, comme des contrôleurs, des services et des configurations, pour ajouter des fonctionnalités spécifiques à une application Symfony.

88.	Quel est le moteur de template utilisé par défaut dans Symfony ?
- Twig

89.	Qu’est-ce qu’un ORM ? Quel est son utilité et comment s’appelle-t-il au sein de Symfony ?
- Object-Relational Mapping : mappe les objets d'une application aux tables de la base de données. Doctrine.

90.	Qu’est-ce que l’injection de dépendances ? Quel est l’outil utilisé dans ce contexte et quel fichier contient l’intégralité des dépendances du projet ?
- L'injection de dépendances fournit des objets à une classe au lieu de les créer. Symfony utilise le Container de services, et les dépendances sont définies dans services.yaml

91.	Que permet le bundle Maker au sein de Symfony ? 
- Le bundle Maker génère automatiquement des composants de code dans Symfony via des commandes CLI.

92.	Quel est le langage de requêtage exploité au sein d’un projet Symfony ?
- DQL (Doctrine Query Language), qui est spécifique à Doctrine pour interroger les bases de données.

93.	Quel est le composant qui garantit l’authentification et l’autorisation des utilisateurs ?
- Le composant Security

## Sécurité
94.	Qu’est-ce que l’injection SQL ? Comment s’en prémunir ?
- attaque permettant de manipuler des requêtes SQL en injectant du code malveillant.
- il faut utiliser des requêtes préparées et des paramètres liés.

95.	Qu’est-ce que la faille XSS ? Comment s’en prémunir ?
- Cross-Site Scripting : permet à un attaquant d'injecter du code JavaScript malveillant dans une page web
- 

96.	Qu’est-ce que la faille CSRF ? Comment s’en prémunir ?
- Cross-Site Request Forgery : force un utilisateur authentifié à exécuter des actions non voulues sur un site.
- utiliser des tokens CSRF (des jetons uniques pour chaque requête) et vérifier ces tokens à chaque action sensible.

97.	Définir l’attaque par force brute et l’attaque par dictionnaire
- Attaque par force brute : Essai de toutes les combinaisons possibles pour deviner un mot de passe.
- Attaque par dictionnaire : Essai de mots de passe à partir d'une liste de mots courants.

98.	Existe-t-il d’autres failles de sécurité ? Citer celles-ci et expliquer simplement leur comportement
- Sécurité des sessions : Permet le vol ou la manipulation de sessions utilisateur, souvent par la capture de cookies.
- Inclusion de fichiers : Exploite des vulnérabilités pour inclure des fichiers malveillants dans une application.
- Déroutement d'URL : Redirige les utilisateurs vers des sites malveillants ou non sécurisés.

99.	A quoi servent l’authentification et l’autorisation dans un contexte d’application web ?
- Authentification : Vérifie l'identité de l'utilisateur.
- Autorisation : Définit les actions que l'utilisateur peut effectuer.

100.	Définir la notion de hachage d’un mot de passe et citer des algorithmes de hachage
- Hachage : Transforme un mot de passe en une chaîne fixe et sécurisée.
- Algorithmes : MD5, SHA-256, bcrypt, Argon2.

101.	Qu’est-ce qu’une politique de mots de passe forts ?
- critères comme longueur, diversité de caractères et complexité pour renforcer la sécurité.

102.	Qu’est-ce que l’hameçonnage ?
- fraude visant à obtenir des informations sensibles en se faisant passer pour une source fiable.

103.	Définir la « validation des entrées »
- Vérifie que les données utilisateur sont correctes et sécurisées avant traitement.

## RGPD
104.	Qu’est-ce que le RGPD ?
- Le RGPD est une loi de l'UE qui protège la vie privée en régulant le traitement des données personnelles.

105.	Quel est son objectif principal ?
- protéger la vie privée et contrôler le traitement des données personnelles.

106.	Quelle est la date d’entrée en vigueur du RGPD ?
- 25 mai 2018

107.	Quelles sont les sanctions possibles en cas de non-respect du RGPD ?
- amendes allant jusqu'à 20 millions d'euros ou 4 % du chiffre d'affaires annuel mondial de l'entreprise

108.	En France, quel est l’autorité administrative qui s’occupe de faire appliquer le RGPD ?
- CNIL (Commission Nationale de l'Informatique et des Libertés)

109.	Quel est le consentement valide selon le RPGD ?
- Selon le RGPD, un consentement valide doit être :

- Libre : Donné sans pression.
- Éclairé : Basé sur des informations claires et compréhensibles.
- Spécifique : Concernant des finalités précises.
- Univoque : Manifesté par une action claire (comme une case à cocher).

110.	Qu’est-ce qu’une politique de confidentialité ?
- décrit comment une organisation gère et protège les données personnelles des utilisateurs.

111.	Quelle est la durée de conservation maximale des données personnelles selon le RGPD ?
- conservées uniquement le temps nécessaire pour les finalités prévues

112.	Quels sont les droits des utilisateurs selon le RGPD ?
- Selon le RGPD, les droits des utilisateurs incluent :

- Droit d'accès : Accéder à leurs données personnelles.
- Droit de rectification : Corriger les informations inexactes.
- Droit à l'effacement : Demander la suppression de leurs données.
- Droit à la limitation du traitement : Restreindre l'utilisation de leurs données.
- Droit à la portabilité : Recevoir leurs données dans un format structuré.
- Droit d'opposition : S'opposer au traitement de leurs données.
- Droit de ne pas être soumis à une décision automatisée : Éviter des décisions basées uniquement sur des traitements automatisés.

113.	Qu’est-ce que le principe de minimisation des données selon le RGPD ?
- collecter uniquement les données nécessaires à la finalité du traitement.

## SEO
114.	Qu’est-ce que le SEO ? 
- Search Engine Optimization

115.	Quel est l’objectif principal du SEO ?
- optimisation pour améliorer le classement dans les moteurs de recherche

116.	Existe-t-il plusieurs types de référencement ? Lesquels ?
117.	Qu’est-ce que la densité de mots-clés en SEO ?
118.	Qu’est-ce qu’une balise « alt » ?
119.	Qu’est-ce que la balise « meta description » ?
120.	Qu’est-ce que le « nofollow » en SEO ?
121.	Quelle est l'importance du contenu de qualité pour le référencement d'un site web ?
122.	Pourquoi est-il important d'utiliser des balises de titre (h1, h2, h3, etc.) de manière structurée ?
123.	Quelle est la recommandation pour les URL d'un site web bien référencé ?
124.	Qu'est-ce que le maillage interne et pourquoi est-il important pour le référencement ?
125.	Qu'est-ce que l'optimisation des images pour le référencement ?
126.	Qu'est-ce qu'un plan de site (sitemap) et pourquoi est-il important pour le référencement ?

## Gestion de projets - DevOps
127.	Qu’est-ce que la gestion de projet ?	
128.	Qu’est-ce qu’une méthode Agile de gestion de projet ? 
129.	Expliquer la méthode MoSCoW en quelques lignes et citer ses avantages
130.	A quoi sert la méthodologie MVP ? Citer les caractéristiques clés
131.	Qu’est-ce que la planification itérative ?
132.	Citer 3 méthodes Agiles dans le cadre d’un projet informatique
133.	Qu’est-ce qu’une réunion de revue de projet ?
134.	Qu’est-ce qu’un livrable dans un projet ? 
135.	Quels sont les 3 piliers SCRUM ? Définir chacun d’entre eux
136.	Qu’est-ce que le DevOps et quel est son objectif principal ?
137.	Qu’est-ce que l’intégration continue ? 
138.	Qu’est-ce que Docker ? Et en quoi est-il utile dans le cadre du DevOps ?
139.	Qu’est-ce qu’un test unitaire ? 
140.	Quelle est l'unité de code testée lors d'un test unitaire ?
141.	Quelles sont les caractéristiques d'un bon test unitaire ?
142.	Qu'est-ce qu'une assertion dans un test unitaire ?
 
## English
1)	What does JavaScript enable you to do on a website ?
a.	Add interactive behavior and dynamic content x
b.	Define the layout and design of web pages
c.	Handle server-side operations
2)	Which programming language is primarily used for server-side web development ?
a.	PHP x 
b.	JavaScript
c.	HTML
3)	What is the purpose of a web browser ?
a.	To render and display web pages x
b.	To execute serve-side code
c.	To manage databases
4)	What is the difference between GET and POST methods in HTTP ?
a.	GET retrieves data from a server, while POST submits data to a server x
b.	GET submits data to a server, while POST retrieves data from a server
c.	GET and POST methods are interchangeable
5)	What is the purpose of version control systems (e.g., Git) in web development ?
a.	To track changes and manage collaborative development x 
b.	To optimize website loading speed
c.	To handle server-side scripting
6)	What is the purpose of a framework in web development ?
a.	To provide a structured environment for building web applications
b.	To handle network protocols and data transfer
c.	To create visual designs and layouts for websites
7)	What does NoSQL stand for ?
a.	Not Only SQL x
b.	Non-Structured Query Language
c.	New Object-Oriented Language
8)	Which of the following is a characteristic of NoSQL databases ?
a.	Strict schema enforcement
b.	Support for complex transactions
c.	Scalability and flexible data models
