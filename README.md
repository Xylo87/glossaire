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
    
    => Environnement de développement PHP. 
    Compilateur/moteur d'exécution (Zend Engine) + Serveur Web HTTP (Apache) + Serveur de base de données (MySQL) = technologie AMP
    => Logiciels qui permettent ce contexte : Laragon, WAMP

2.	Qu’est-ce qu’un algorithme ?  

    => Suite d'instructions et/ou d'opérations, finie et non ambiguë, pour résoudre un problème et en obtenir une solution. 
    Traduit dans un language informatique pour élaborer un programme.

3.	Qu’est-ce qu’une variable ? Par quel symbole est préfixée une variable en PHP ?

    => Espace mémoire qui associent un nom (identifiant) à une valeur; utilisées par programme pour mémoriser des données nécessaires au fonctionnement du programme.
    Peuvent être statiques ou dynamiques (changement de valeur sans la redéclarer).
    => Préfixe en PHP : $

4.	Qu’est-ce que la portée d’une variable ?

    => Champ d'accessibilité dans laquelle elle peut être utilisée. 
    Variable disponible que dans le contexte dans lequel elle a été déclarée.
    Portée se limite à son bloc. 
    Syn. : Scope
    Hoisting = variable a une portée hors de son Scope (ex. Var en JS)

5.	Qu’est-ce qu’une constante ? Quelle est la différence avec une variable ?

    => Variables peuvent être statiques ou dynamiques (changement de valeur sans la redéclarer).
    Constante = variable statique.

6.	Qu’est-ce qu’une superglobale, combien en existent-ils et donner un exemple d’utilisation 

    => En PHP, variables permettant d'accéder aux informations transmises par le client au serveur.
    Toutes de type tableau (regrouper des infos sous forme de clé/valeur).
    Natives au script PHP + accessibles depuis n'importe quel fichier .php si définies
    => 8 ($_GET, $_POST, $_COOKIE, $_REQUEST, $_SESSION, $_FILES, $_ENV et $_SERVER)
    => ex. $_GET > méthode HTTP > contient tous les paramètres transmis au serveur via l'URL de la requête (Query String Parameters)

7.	Quels sont les différents types (primitifs) que l’on peut associer à une variable en PHP ? Les citer et en donner des exemples (ne pas oublier le type d’une variable sans valeur)

    => - Entier (Integer) => ex. 7
    - Réel (Float ou Double) = ex. 3.5
    - Booléen (Boolean) = True/False
    - Chaîne de caractère (String) = "Ce foie gras n'est quand même vraiment pas terrible Charles-Édouard"
    - Variable sans valeur = null

8.	Existe-t-il plusieurs types de tableaux en PHP, si oui lesquels ?

    => - Tableaux indexés (..., ..., ...)
    - Tableaux associatifs (
                        clé => valeur
                        clé => valeur
                        clé => valeur
                        )
    - Tableaux multidimensionnels (..., ..., (..., ..., ...))

9.	Quelles sont les différentes structures de contrôles qu’il existe en algorithmie ? Donner un exemple pour chacune d’entre elles

    => - Structure séquentielle (instructions exécutées l'une après l'autre selon un ordre) = ex. Permuter deux entiers
    - Structure alternative (instructions exécutées selon les réponses à des conditions) = ex. If, If/Else, Switch etc.
    - Structure itérative (portion de code à exécuter plusieurs fois de suite - boucles) = ex. While, For, ForEach
    - Fonctions (série d'opérations à partir d'arguments-valeurs, passés en paramètres > la fonction renvoie ensuite un résultat, qui est une valeur) = ex. Function/Method en JS

10.	Quelle est la fonction PHP permettant de demander la longueur d’une chaîne de caractères ?

    => strlen($CdC)

11.	Qu’est-ce qu’une session ? Quelle fonction permet de démarrer une session en PHP ? Donner un exemple d’utilisation en PHP

    => Moyen de stocker des donnnées côté serveur pour chaque utilisateur, avec un identifiant de session unique (lié aux cookies côté navigateur).
    Utilisées pour faire persister des infos entre plusieurs pages.
    Durée limitée (180min par défaut > modulable).
    => session_start() > démarrer une session pour l'utilisateur ou récupérer une session préexistante.
    => ex. Enregistrement de produits en session sur un site d'achat ("Panier").


12.	Qu’est-ce qu’un cookie ? Donner un exemple d’utilisation en PHP

    => Mécanisme d'enregistrement et de lecture d'informations sur un client.
    Fichier texte envoyé par le serveur sur la machine utilisateur (navigateur).
    Contient l'identifiant d'une session unique, pour faire le lien avec la session utilisateur côté serveur (PHPSESSID).
    Expire par défaut à la fermeture du navigateur.
    => Si cookie suppr. ou modif., prochaine requête du client devra démarrer une nouvelle session.

13.	Quelle est la différence entre les instructions « require » et « include » en PHP

    => Permettent toutes deux d'inclure le contenu d'un autre fichier appelé dans un fichier PHP. 
    Différence si le fichier ne peut être inclus pour une quelconque raison (fichier introuvable, indisponible etc.).
    - Include = simple avertissement de PHP, reste du script s'exécute.
    - Require = erreur fatale, l'exécution du script est stoppée.
            > include_once, require_once (fichier externe ne peut être inclus qu'une seule fois).

14.	Comment effectuer une redirection en PHP ?

    => Fonction header("Location:xxx")
    Envoi d'une nouvelle entête HTTP (réponse) au client.
        > Redirection = status code HTTP 302

15.	Définir la partie « front-end » et « back-end » d’une application

    => Front-End : Partie interactive d'une application Web, via l'interface utilisateur
    => Back-End : Couche d'accès aux données d'une application : élaboration d'un espace de stockage pour le projet, création d'une base de données, 
    fournir les informations demandées par les utilisateurs/enregistrer les informations soumises par eux 
    (ex. communication entre serveurs et applications par le biais d'interfaces => API)

16.	Définir le contrôle de version ? Qu’est-ce que Git ?

    => Suivi et gestion des changements apportés à un système de fichiers. Peut être linéaire et chronologique ou élaboré en structure arborescente.
    => Git = outil de dévelopemment qui gère les changements apportés au code source d'une application. Garde une trace de chaque changement apporté au code.

17.	Qu’est-ce qu’un CMS ? Citer au moins 2 exemples

    => Content Management System = permet de créer et d'éditer un site web sans connaissances techniques, le but étant la mise en ligne rapide.
    => Ex. WordPress, Drupal

## Front-end
18.	Définir HTML

    => HyperText Markup Language = language de balises pour l'hypertexte. Créer et représenter le contenu d'une page web et sa structure. 
    Hypertexte = liens qui relient les pages entre elles (internes et externes). Toile, Web.
    Balises permettent d'afficher les éléments dans un navigateur web. 

19.	Définir CSS

    => Feuilles de style en cascade. Language utilisé pour décrire la présentation d'un document HTML. Décrit la façon dont les éléments doivent être affichés à l'écran.

20.	Définir Javascript

    => Language de programmation qui permet de créer du contenu mis à jour de façon dynamique.
    Sites Web interactifs.
    S'applique à un document HTML.
    Troisième couche de technologie standard du Web.

21.	Définir JSON. Dans quel contexte ce format est-il utilisé ?

    => JavaScript Object Notation > Format de données et de fichier > Échange de données d'une application web entre un navigateur et un serveur > Format lisible, représente les données structurées sous forme de paires clés/valeurs (valeur = nb, bool, null, obj, array, CdC...)
    => Transmettre des données du serveur au navigateur pour afficher du contenu / Transmettre au serveur des données entrées par un utilisateur sur une appli web
        > S'apparente à un obejt JS ou un tableau associatif PHP > Grand volume de données 

22.	Peut-on interpréter du Javascript côté serveur ? Si oui, comment ?

    => NodeJS > développement de serveurs web ou d'API > notamment basé sur des boucles d'évènements (Event Loop) qui permettent plusieurs opérations simultanées (asynchrone) > Promesses, remédier au "Callback Hell" > Gestion d'un grand nombre de connexions simultanées de manière non-bloquante (ex. Apps en temps réel comme les chats, jeux en ligne et services de streaming)
        > Frameworks : Adonis, Express etc.

23.	Qu’est-ce qu’un sélecteur CSS ?

    => Expression qui indique au navigateur à quelle entité HTML s'applique la règle CSS correspondante

24.	Quelle balise HTML permet de créer un lien hypertexte ?

    => <a> => attribut "href=" = destination du lien

25.	Qu’est-ce qu’une requête AJAX ?

    => Permet une requête HTTP directement depuis du code JavaScript et sans recharger toute la page > Performance : limiter le temps d'attente lorsqu'une ou plusieurs infos de la page doivent être mises à jour par le serveur > Asynchrone > Renvoie d'une promesse (pas données directement)

26.	Quel sélecteur CSS permet de sélectionner tous les éléments d’une classe spécifique ? D’un identifiant spécifique ?

    => ".class"
    => "#id"

27.	Définir le responsive design

    => Approche de la conception web visant à ce que les pages s'affichent correctement pour toutes les tailles et résolutions d'écran, avec une utilisabilité correcte.

28.	Qu’est-ce que le templating ?

    => Utilisation d'un modèle pour générer du contenu HTML dynamique > Ex. Insertion de variables dynamiques dans le Template, ensuite remplacées par des données spécifiques au moment de l'execution => Séparation de la structure de la page des données qui la remplissent
    Ex. Templating PHP : mise en mémoire tampon avec ```ob_start``` + ```ob_get_clean``` > sauvegarde dans une variable > ```require_once``` de *template.php* 
    Ex. Twig (moteur de template) + *base.html.twig*/*extends 'base.html.twig'*
    

29.	Qu’est-ce qu’une fonction anonyme en Javascript ?

    => Utilisée lorsque fonction est temporaire et spécifique (ex. setTimeout, map, filter, forEach > fonction fléchée); on peut alors, par exemple, simplement la stocker dans une variable > fonction locale, légère et simple (encapsuler les logiques qui ne seront pas utilisées ailleurs)

30.	Quelle méthode JavaScript est utilisée pour ajouter un élément à la fin d'un tableau ?

    => tableau.push("element")

31.	Qu’est-ce qu’un « media query » ?

    => Une requête média permet de modifier l'apparence d'une application en fonction du type d'appareil (ex. écran etc.) 
    et de ses caractéristiques (ex. résolution d'écran, largeur de la zone d'affichage etc.).
        > Permet d'appliquer certains styles CSS de façon conditionnelle grâce à des règles.

32.	Qu’est-ce qu’un pseudo élément en CSS ?

    => Mot-clé ajouté à un sélecteur qui permet de mettre en forme certaines parties de l'élément ciblé par la règle.
    Ex. ::first-line permet de ne cibler que la première ligne d'un élément visé par le sélecteur.
    Autre ex. ::before / ::first-letter / ::selection (appliquer des règles CSS à une portion du document sélectionné par l'utilisateur, via la souris ou un dispositif de pointage).

33.	Qu’est-ce que Bootstrap ? Donner d’autres exemples équivalent

    => Framework (librairie) de développement front-end/
    Ensemble d'outils comme des modèles de boutons, barres de navigation, éléments de formulaire déjà stylisés et prêts à être utilisés.
    Permet de gagner du temps en s'assurant que le site gère le Responsive Design.
    => - Foundation
    - Bulma
    - Tailwind CSS
            > chacun a ses propres caractéristiques et approches

34.	Quand un formulaire HTML est créé, quelles sont les 2 méthodes qui peuvent lui être associées ? Donner la différence entre ces 2 méthodes

    => Méthodes GET et POST. Requêtes HTTP.
        > GET = données envoyées au serveur sont écrites directement dans l'URL. Demande de représentation de la ressource spécifiée; utilisée pour récupérer des données.
        > POST = données envoyées au serveur sont écrites dans la requête elle-même (corps de la requête HTTP). Utilisée pour envoyer une entité vers la ressource indiquée.

## UX UI
35.	Quelle est la différence entre UX Design et UI Design ?

    => - UI = Interface utilisateur (design graphique) > interface agréable > position des éléments graphiques et textuels > faciliter navigation
    - UX = Expérience utilisateur (interface ergonomique) > analyse du ressenti des utilisateurs avec l'interface web (divers parcours possibles des utilisateurs) > expérience agréable + faciliter la recherche d'infos > accessibilité (apparence cohérente, fonctionnalités intuitives...) > Responsive en fait partie intégrante 

36.	Qu’est-ce qu’un wireframe ? 

    => Maquette fil de fer d'une interface > Schéma de la structure et des fonctionnalités d'une application > Recherche d'ergonomie 

37.	Qu’est-ce qu’un prototype ? 

    => Maquette fonctionnelle > permet de simuler le fonctionnement d'une application web (UX, expérience utilisateur)

38.	Qu’est-ce que la hiérarchie visuelle en UI Design ?

    => Objectif de guider l'utilisateur à travers l'application > Éléments de design tels que la taille, la couleur et la position pour l'importance des éléments de l'interface utilisateur (ex. parcours en F ou en E de l'application > lecture en E pour un blog)

39.	Qu’est-ce que l’accessibilité en UX Design ? 

    => Conception d'interfaces compéhensibles et opérables par le plus grand nombre, y compris les utilisateurs ayant des besoin spécifiques (handicaps visuels, physiques...) 
        > principes POUR = perceptible, opérable (interface), compréhensible (contenu), robuste (compatibles avec diverses techologies d'assistance)
        (((> textes alt. pour les images, compat. lecteurs d'écran, couleurs contrastées, compat. techno. futures...)))

40.	Qu’est-ce qu’une grille de mise en page ?

    => Axes horizontaux et verticaux pour structurer le contenu > Armature que laquelle organiser textes et images

41.	Qu’est-ce que la notion d’affordance en UX Design ?

    => Capacité d'un objet ou d'un système à évoquer son utilisation, sa fonction > Réaction spontanée entre un environnement et son utilisateur > Rendre utilisation intuitive dans le cadre du design d'interfaces > Offrir les moyens à l'utilisateur de se servir d'un objet, si possible sans mode d'emploi => "Call to action"

42.	Qu’est-ce qu’un « mobile first design » ?

    => Concevoir une application en priorisant la version mobile et en adaptant progressivement le web design pour les écrans plus larges, au delà du Responsive Design
        > concept contraire à l'approche qui consistait à "dégrader" progressivement un site web pour l'adapter à l'affichage sur Smartphone 

## Programmation orientée objet (POO)
43.	Donner une définition de la programmation orientée objet 

    => Modèle qui repose sur le concept de classes et d'objets > Structurer un programme en éléments de codes simples, modulables et réutilisables (classes) utilisés pour créer des instances individuelles d'objets
        > Objets = "choses" modélisées dans des programmes; but est de représenter le monde réel en code

44.	Qu’est-ce qu’une classe ? Comment la déclare-t-on ?

    => Ensemble d'attributs et de méthodes communs à des objets > Attributs représentent l'état des objets et les méthodes représentent leurs comportements > Catégorie d'objets > Modèles
    => Utilisation du mot-clé "Class" suivi du nom de la classe

45.	Qu’est-ce qu’un objet ?

    => Instance d'une classe > Contient ses données/propriétés/attributs/caractéristiques et ses méthodes (état et comportement)

46.	Définir la notion de propriété / attribut / méthode

    => Propriétés/Attributs = caractéristiques d'une classe (ex. couleur, marque, modèle pour un objet "voiture")
    => Méthodes = comportements possibles d'un objet, définis dans une classe > S'apparentent à une fonction

47.	Qu’est-ce que la visibilité d’une propriété ou d’une méthode ? Citer les différents types de visibilité

    => Portée d'accès des attributs et méthodes d'une classe (intérieur et extérieur d'une classe)
    => - Public = accessibles de n'importe où (sans restriction)
    - Private = accessibles uniquement à l'intérieur de la classe > ne peuvent être modifiés (set) ou utilisés en dehors de la classe
    - Protégé = accessibles à l'intérieur de la classe et dans classes qui en héritent (sous-classes, classes-"enfants", classes dérivées) > inaccessibles à l'extérieur

48.	Quelle est la méthode spécifique utilisée pour créer un nouvel objet à partir d’une classe ?

    => Mot-clé "new" permet d'instancier une classe, créer un objet à partir d'elle

49.	Qu’est-ce que l’encapsulation ?

    => Mécanisme qui empêche de modifier des objets ou de leur faire adopter tel ou tel comportement (accès aux méthodes) autrement que par les moyens proposés (portée des attributs et méthodes) 
        > But = garantir l'intégrité des objets

50.	Que signifie « étendre une classe » ? Quelle est le concept clé mis en œuvre ? Donner un exemple

    => Permet à une classe (appelée classe fille ou sous-classe) d'hériter des propriétés et des méthodes d'une autre classe (appelée classe parent ou superclasse).
    Permet réutilisation du code et la création de hiérarchies de classes.
    Utilisation des méthodes et propriétés "publiques" ou "protégées" > Classe fille peut redéfinir ou ajouter de nouvelles méthodes et/ou propriétés.
    
    Ex. 
        namespace App;

        class Controller
            
            public function parler() {
                code...
            }

        
        use App\AbstractController

        class HomeController extends Controller
            
            public function parler() {
                rédéfinition du code si besoin...
            } 

51.	Définir l’opérateur de résolution de portée
52.	Définir une méthode / propriété statique

    => Associées à la classe elle-même, et non à l'instance de la classe > Peuvent être utilisés sans créer d'objet
        > Méthodes peuvent être appelées directement sur la classe
        > Ex. utilisation = - Class::$variable = ? (réassigner la variable définie dans la classe)
        - Class::methode() (utiliser la méthode définie dans la classe)

53.	Définir le polymorphisme en POO
54.	Définir une méthode / classe abstraite ?

    => Classe qui ne peut être directement instanciée mais qui peut contenir des méthodes utilisables (par héritage notamment).
    => Méthode déclarée mais non implémentée > Doivent être implémentées par les classes filles.

55.	Définir le chaînage de méthodes

    => *INCOMPLET*

56.	Qu’est-ce que la méthode __toString() ? Existe-t-il d’autres méthodes « magiques »

    => Permet de définir des éléments d'une classe qui seront convertis en chaîne de caractères > Personnaliser l'affichage d'un "$objet" avec un echo > Méthode doit être définie dans la classe
    => Autre ex. = __construct() > Appel de cette méthode à chaque création d'une nouvelle instance de l'objet (initialisations de l'objet)

57.	Qu’est-ce qu’un « autoload » ?

    => Fonction qui permet aux classes définies dans des fichers externes d'être automatiquement chargées dans le script principal en PHP, sans avoir à les inclure manuellement.

58.	Comment appelle-t-on en français les « getters » et les « setters » ?

    => Getters = Accesseurs
    Setters = Mutateurs

59.	Qu’est-ce que la sérialisation en PHP ? 

## Architecture 
60.	Qu’est-ce que l’architecture client / serveur ? Grâce à quel type de requête peut-on interroger le serveur. Définir l’acronyme de ce type de requête. Si on ajoute un « S » à cet acronyme, expliquer la différence

    => - Le client (navigateur ou autre application) demande des services (exécuter des actions) ou des ressources (informations > récupérer des données) à des serveurs > Client envoie des requêtes
    - Le serveur reçoit les requêtes et y répond en fournissant les ressources demandées ou en exécutant les actions nécessaires > Gestion des données et de la sécurité > Serveur peut être spécilisé (base de données, web (fournisseur de pages web > fichiers HTML), application etc.)
            > Client reçoit le réponse et l'affiche à l'utilisateur ou l'utilise pour d'autres actions
    => Une requête HTTP > HyperText Transfer Protocol > URL (Uniform Resource Location) = adresse de la ressource sur le serveur > Réponse du serveur = code HTML d'une page web (par ex.)
        > méthode HTTP = GET, POST, PUT (MàJ), DELETE (par ex.) > en-têtes requête (cookies (clé d'une session) par ex.) > corps requête (HTML ou formulaire par ex.) > ex. code statut HTTP :
        - 200 OK (requête réussie, réponse envoyée)
        - 404 NOT FOUND (ressource demandée introuvable)
        - 500 INTERNAL SERVER ERROR
    => Version sécurisée de l'HTTP > Ajout d'un chiffrement pour protéger les données lors de l'échange > Chiffrées avant d'être envoyées; interception ou manipulation difficiles par un tiers

61.	Donner la définition d’un design pattern. Citer au moins 3 exemples de design pattern

    => Solution réutilisable pour la conception d'applications > Approche standardisée/générique et bonnes pratiques pour des situations similaires > Rendre le code flexible (faciliter sa maintenance et son évolution) > Indépendante d'un language spécifique

62.	Qu’est-ce que l’architecture MVC ?

    => Séparation des différentes responsabilités d'une application > Approche pour organiser le code > Utilisée principalement pour des applications web > Destinée aux interfaces graphiques

63.	Quel est le rôle de chaque couche du design pattern MVC : Model, View, Controller ?

    => - Model : donne une représentation des données liées > Responsable de l'accès aux données (lecture, écriture et MàJ)
    - View : affichage des données fournies par le modèle > Affichage utilisateur, partie visible de l'interface graphique
    - Controller : traite les actions de l'utilisateur > contrôle les modifications des données et met à jour la vue > Intermédiaire entre Model et View

64.	Quels sont les avantages de l’architecture MVC ?

    => Séparation des préoccupations (composants) > Facilite la gestion du code, sa maintenance et les tests > Modèle réutilisable avec différentes vues/interfaces (sans toucher à la logique de gestion des données)

65.	Existe-t-il des variantes à l’architecture MVC ?
66.	Qu’est-ce qu’une API ? Définir l’architecture REST

    => Ensemble de règles et de méthodes qui permettent à différentes applications de communiquer entre elles.
    Permet à une application d'envoyer des demandes à une autre application et de recevoir des données en réponse (sans explication de la procédure de traitement), données qui peuvent ensuite être exploitées au sein de la première application.
    => Architecture REST repose sur l'utilisation des méthodes HTTP "GET, POST, PUT, DELETE" pour communiquer avec un serveur API.
    Les ressources sont identifiables par des URLs.
    Les données sont généralement récupérées au format JSON.
    Ex. Récupération des derniers tweets d'un utilisateur donné sur une application (envoi d'une requête à l'API de Twitter, renvoi des tweets sous forme de données que la première appli peut afficher).

## Modélisation - Base de données
67.	Qu’est-ce que la modélisation de données ? Définir la méthode Merise

    => Concevoir un système d'informations en mettant l'accent sur la gestion des données > Création d'une représentation structurée des données nécessaires au système
    => Approche étape par étape pour garantir l'efficacité et la cohérence des données tout au long du processus de conception du système > Décrire les données, leurs relations et les organiser de façon à faciliter leur gestion et leur exploitation

68.	Quelles sont les 3 étapes principales de la méthode Merise ? 
a.	Analyse, conception et réalisation *<=*
b.	Planification, exécution et contrôle
c.	Création, modification et suppression
69.	Qu’est-ce qu’un modèle conceptuel de données (MCD) en Merise ?

    => Permet de décrire les données de manière abstraite, en mettant l'accent sur les entités, leurs attributs et leurs relations > Représentation globale du système

70.	Qu’est-ce qu’un modèle logique de données (MLD) en Merise ?

    => Traduit le MCD en un modèle plus détaillé, en précisant notamment les contraintes logiques (ex. clés étrangères) > Proche de la manière dont les données seront stockées en base

71.	Donner la définition des mots suivants :
a.	Entité

    => Représente un objet/concept/chose du monde réel que l'on souhaite modéliser en système d'informations > Objet identifiable (id) et doté d'attributs > Succeptible d'interagir avec d'autres entités > Unité d'information avec une existence propre > Point de départ pour construire BdB et son organisation

b.	Relation

    => Lien/interaction entre plusieurs entités > modélisation des associations/dépendances entre plusieurs objets

c.	Cardinalité

    => Type de relation > Décrit le nombre de fois qu'une entité peut être liée à une autre dans une relation (1,1 - 1,N - N,N)

d.	Clé primaire / clé étrangère

    => Organisation et liaison logique des données
    - Clé primaire = identifiant unique pour chaque entité
    - Clé étrangère = attribut de liaison d'une entité avec une autre entité > Référence de la clé primaire d'une autre entité

72.	Que devient une relation de type « Many To Many » dans le modèle logique de données ?

    => Donne lieu à une table associative entre deux entités > Relation intermédiaire > Clés étrangères pour chacune des deux entités impliquées dans la relation

73.	Qu’est-ce qu’une base de données ?

    => Système qui permet d'accéder à une ensemble organisé de données 

74.	Définir les notions suivantes : 
a.	SQL

    => Structured Query Language > language utilisé pour interroger, modifier et gérer les données dans une base

b.	MySQL

    => Outil logiciel qui permet de stocker et de gérer les données en utilisant SQL

c.	SGBD (donner 2 exemples de SGBD)

    => Système de gestion de base de données
    => MongoDB (NoSQL orientée documents) / Oracle Database (relationnel)

75.	Dans une base de données, les données sont stockées dans des tables. Celles-ci sont constituées de lignes appelées *enregistrements* et de colonnes appelées *champs*.
76.	Quelle est la différence entre une base de données relationnelle et non relationnelle ?

    => Manière dont les données sont organisées et stockées
        > - Relationnelle = données stockées sous forme de tables (lignes/colonnes) (> table = entité / colonne = attribut / enregistrement = valeur) (> relations = clés primaires et étrangères) (> language = SQL) > Orga structurée et intégrité garantie par les contraintes mais moins flexibles pour données non structurées (documents, données multimédias) et moins perf pour volumes de données important
        - Non-relationnelle = stockage flexible (ex. documents, clés-valeur) (> languages spécifiques à chaque BdD NoSQL) > Moins de support pour les requêtes complexes (moins de structure)
        > Choix dépend des besoins du projet et de la structure des données

77.	Qu’est-ce qu’une jointure dans une base de données ? En existe-t-il plusieurs ? Si oui lesquelles ?

    => Commande qui permet de joindre 2 tables pour une requête qui nécessite des données contenues dans l'une et l'autre
    => - "Inner Join" > Combiner les données de 2 tables au moyen, généralement, d'une colonne partagée
    - "Left Join" > Récupérer toutes les lignes de la table de gauche (la 1ère mentionnée) et les lignes correspondantes dans l'autre table > Si aucune correpsondance, la requête renvoie quand même les lignes de la table de gauche, avec des valeurs NULL pour l'autre table => garder les données de la table de gauche, même sans correspondance

78.	A quoi sert une vue dans une base de données ?
79.	Qu’est-ce que l’intégrité référentielle dans une base de données ?

    => Garantit que les relations entre les tables sont cohérentes.
    Situation dans laquelle pour chaque information d'une table A qui fait référence à une information d'une table B, l'information référencée existe dans la table B.
    Compatible avec le fait qu'une clé étrangère puisse être "null" (si un "id" n'est pas "null", il DOIT simplement correspondre à un "id" dans l'autre table).

80.	Quelles sont les fonctions d’agrégation en SQL ?

    => Opérations sur une ensemble d'enregistrements > 
    - AVG() = calculer moyenne sur un ensemble d'enregistrements
    - COUNT() = compter le nombre d'enregistrements sur une table ou une colonne
    - MAX() = récupérer la valeur maximum d'une colonne sur un ensemble de lignes
    - MIN() = récupérer la valeur minimum
    - SUM() = calculer la somme sur un ensemble d'enregistrements
                > Prennent leur sens avec l'utilisation d'un GROUP BY

81.	Qu’est-ce qu’un CRUD dans le contexte d’une base de données ?

    => 4 opérations de base dans la gestion de BdD > 
    - Create (INSERT en SQL)
    - Read (SELECT en SQL)
    - Update (UPDATE en SQL)
    - Delete (DELETE en SQL)

82.	Quelles sont les clauses qui permettent de :
a.	Insérer un nouvel enregistrement dans une table

    => INSERT INTO table (...) VALUES ('valeur1', 'valeur2', 'valeur3'...)

b.	Modifier un enregistrement dans une table

    => UPDATE table (...)
    SET champ/nom_colonne (...) = 'nouvelleValeur'
    WHERE

c.	Supprimer un enregistrement dans une table

    => DELETE FROM

d.	Supprimer la base de données

    => DROP DATABASE

e.	Filtrer les résultats d’une requête SQL

    => WHERE

f.	Trier les résultats d’une requête SELECT

    => ORDER BY

g.	Regrouper les résultats d'une requête SELECT en fonction d'une colonne spécifique

    => GROUP BY

h.	Concaténer 2 chaînes de caractères

    => CONCAT

83.	Comment se connecter à une base de données en PHP ? Quelle est la classe native utilisée ?

    => Utilisation de l'extension PDO (PHP Date Objects) > Méthode flexible qui utilise des exceptions pour gérer les erreurs de connexion > Interface orientée objet pour effectuer des requêtes SQL (méthodes spécifiques) > Utilisation des requêtes préparées pour se protéger contre les attaques par injection SQL
    => PDO est une classe native à PHP


## Symfony
84.	Qu’est-ce que Symfony ?

    => Framework PHP open-source.
    Ensemble de composants pour développer des applications robustes, sécurisées et maintenables.
        > - Modularité (composants réutilisables)
        - Flexibilité (personnaliser et étendre les fonctionnalités en fonction des projets)
        - Performance (rapide, optimisé)
        - Écosystème (communauté + bundles/extensions)

85.	Sur quel langage de programmation et design pattern repose Symfony ?

    => Symfony repose sur le PHP et le design pattern Model View Controller.

86.	Quelle est la dernière version en date de Symfony ?

    => 7.2.2 (31 décembre 2024)

87.	Qu’est-ce qu’un bundle ? 

    => Paquet de fonctionnalités ou de composants modulaires (code, contrôleurs, routes, templates, services, configurations etc.).
    Réutilisation de code ou de fonctionnalités entre différentes applications.
    Ex. "Verify Email Bundle" > Bundle pour gérer l'authentification et la gestion des utilisateurs d'une application.

88.	Quel est le moteur de template utilisé par défaut dans Symfony ?

    => Twig

89.	Qu’est-ce qu’un ORM ? Quel est son utilité et comment s’appelle-t-il au sein de Symfony ?

    => ORM - Object Relationnal Mapper
    *INCOMPLET*

90.	Qu’est-ce que l’injection de dépendances ? Quel est l’outil utilisé dans ce contexte et quel fichier contient l’intégralité des dépendances du projet ?
91.	Que permet le bundle Maker au sein de Symfony ? 
92.	Quel est le langage de requêtage exploité au sein d’un projet Symfony ?

    => DQL (Doctrine Query Language) > language propre à Doctrine pour interagir avec la BdD
        > Similaire à SQL mais travaille directement avec les objets et entités définies dans le PHP (plutôt qu'avec les tables en BdD)

93.	Quel est le composant qui garantit l’authentification et l’autorisation des utilisateurs ?

## Sécurité
94.	Qu’est-ce que l’injection SQL ? Comment s’en prémunir ?

    => Attaquer une base de données en injectant du code SQL malveillant dans une requête (CRUD).
    Importance de filtrer correctement les entrées utilisateurs (ici, notamment, les URL via un champ de recherche).
    => Utilisation de requêtes préparées > séparent la logique/structure de la requête SQL ("placeholders") et les données ("prepare" > "execute").

95.	Qu’est-ce que la faille XSS ? Comment s’en prémunir ?

    => "Cross-Site Scripting" > injection de code malveillant (généralement du JavaScript) dans une page web vue par d'autres utilisateurs > code exécuté par le navigateur victime (ex. manipuler le contenu de la page).
    => Le filtrage des champs de formulaires HTML en PHP permet notamment de se prémunir des injections XSS, en validant ou en assainissant les données saisies par l'utilisateur avant de les utiliser, afin de s'assurer qu'elles respectent un format attendu et qu'elles ne contiennent pas de code malveillant.

96.	Qu’est-ce que la faille CSRF ? Comment s’en prémunir ?
97.	Définir l’attaque par force brute et l’attaque par dictionnaire

    => Attaque qui consite à essayer toutes les combinaisons possibles de mot de passe de manière automatisée > Efficace si MdP est faible ou court.
    =>  Méthode d'attaque avec essais d'une liste préétablie de mots courants, de combinaisons ou de phrases pour deviner un mot de passe > Plus rapide qu'une attaque par force brute car l'attaque se concentre sur des mots de passe probables (mots simples, combinaisons courantes etc.).

98.	Existe-t-il d’autres failles de sécurité ? Citer celles-ci et expliquer simplement leur comportement
99.	A quoi servent l’authentification et l’autorisation dans un contexte d’application web ?

    => Authentification = processus de vérification de l'identité d'un utilisateur lors de la connexion à une application, pour pouvoir accéder aux fonctionnalités de cette dernière > Demande d'un identifiant (nom d'utilisateur, e-mail etc.) et d'un mot de passe.
    => Processus qui détermine les permissions (fonctionnalités) et les ressources auxquelles un utilisateur donné a accès. Ex. Utilisateur/Modérateur/Administrateur

100.	Définir la notion de hachage d’un mot de passe et citer des algorithmes de hachage

    => Processus qui transforme un MdP en une série de caractères appelée "empreinte" ou "hash". 
    Processus irréversible (du moins pour les algorithmes de hachage forts...) > Sécuriser un mot de passe de sorte que même si quelqu'un accède à la base de données où il est stocké et haché, il ne puisse
    retrouver le mot de passe original.
    => - Algorithmes de hachage faibles : + md5
    + sha256
    - Algorithmes de hachage forts : + bCrypt

101.	Qu’est-ce qu’une politique de mots de passe forts ?

    => Ensemble de règles et de recommandations pour garantir que les MdP choisis par les utilisateurs soient suffisamment complexes et difficiles à casser par des attaques.
    Renforcer la sécurité des comptes et des systèmes.
    La CNIL recommande la création d'un mot de passe selon certains critères : - 12 caractères ou plus
    - au moins un nombre
    - au moins un signe de ponctuation ou caractère spécial
    - au moins une majuscule
    Le mot de passe ne doit pas contenir d'informations "évidentes" (infos personnelles faciles à deviner).
    Les mots de passe doivent être changés régulièrement (3 à 6 mois par exemple).
    Il est déconseillé de réutiliser les mots de passe pour un même compte (en cas de réinitialisation).

102.	Qu’est-ce que l’hameçonnage ?
103.	Définir la « validation des entrées »

## RGPD
104.	Qu’est-ce que le RGPD ?
105.	Quel est son objectif principal ?
106.	Quelle est la date d’entrée en vigueur du RGPD ?

    => Entrée en application dans tous les pays membres de l'Union Européenne le 25 mai 2018

107.	Quelles sont les sanctions possibles en cas de non-respect du RGPD ?
108.	En France, quel est l’autorité administrative qui s’occupe de faire appliquer le RGPD ?

    => La CNIL (Commission nationale de l'Informatique et des Libertés)
    - Surveille et contrôle > Conformité des entreprises et orgas avec le RGPD > Audits, enquêtes et demandes d'infos
    - Conseil et sensibilisation > Aide aux entreprises pour son application correcte > Informe la public sur ses droits en matière de protection des données
    - Sanctions > amendes et mesures correctives (ex. imposition d'un changement dans la gestion/traitement des données)

109.	Quel est le consentement valide selon le RPGD ?
110.	Qu’est-ce qu’une politique de confidentialité ?
111.	Quelle est la durée de conservation maximale des données personnelles selon le RGPD ?
112.	Quels sont les droits des utilisateurs selon le RGPD ?
113.	Qu’est-ce que le principe de minimisation des données selon le RGPD ?

## SEO
114.	Qu’est-ce que le SEO ? 
115.	Quel est l’objectif principal du SEO ?
116.	Existe-t-il plusieurs types de référencement ? Lesquels ?
117.	Qu’est-ce que la densité de mots-clés en SEO ?
118.	Qu’est-ce qu’un attribut « alt » ?

    => Obligatoire > Contient une description textuelle de l'image > Utile pour les outils de lecture d'écran et si l'image ne peut pas être chargée (ex. lien périmé ou blocage de contenu)

119.	Qu’est-ce que la balise « meta description » ?

    => Balise + attribut HTML qui décrivent le contenu d'une page web.
    Placé dans l'entête de la page > Offrir un résumé clair et concis du contenu de la page pour les moteurs de recherche et inciter les utilisateurs à visiter l'application lorsque la descritpion
    apparaît dans les résultats (peut améliorer le taux de clics > CTR) > Pertinente et engageante pour attirer l'attention de l'utilisateur.
    Ex. <meta name="description" content="ceci est une description">


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

    => Technique des priorités en gestion de projets > Permet de classer les tâches et leur exigence en 4 catégories :
    - Must Have > Absolument nécessaire pour les succès du projet
    - Should Have > Important, mais pas indispensable
    - Could have > Souhaitable mais non essentielle
    - Won't Have > Éléméents non-inclus dans cette phase du projet
    => - Clarté de priorisation des tâches
    - Ajustement flexible des priorités en fonctions des ressources et des nouvelles contraintes
    - Bonne gestion des attentes des parties prenantes en établissant des critères clairs sur le livrable

130.	A quoi sert la méthodologie MVP ? Citer les caractéristiques clés
131.	Qu’est-ce que la planification itérative ?
132.	Citer 3 méthodes Agiles dans le cadre d’un projet informatique
133.	Qu’est-ce qu’une réunion de revue de projet ?
134.	Qu’est-ce qu’un livrable dans un projet ? 

    => Produit ou résultat qui doit être fourni à la fin d'une phase ou du projet lui-même.
    Répond à un besoin ou une exigence définie > Peut être remis à un client/partenaire/partie prenante du projet.
        > Mesurer les progrès d'un projet et leur acceptation/validation pour déterminer si un projet avance selon les attentes et les objectifs fixés. 
        > Ex. Version d'une application web

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
a.	Add interactive behavior and dynamic content *<=*
b.	Define the layout and design of web pages
c.	Handle server-side operations
2)	Which programming language is primarily used for server-side web development ?
a.	PHP *<=*
b.	JavaScript
c.	HTML
3)	What is the purpose of a web browser ?
a.	To render and display web pages *<=*
b.	To execute serve-side code
c.	To manage databases
4)	What is the difference between GET and POST methods in HTTP ?
a.	GET retrieves data from a server, while POST submits data to a server *<=*
b.	GET submits data to a server, while POST retrieves data from a server
c.	GET and POST methods are interchangeable
5)	What is the purpose of version control systems (e.g., Git) in web development ?
a.	To track changes and manage collaborative development *<=*
b.	To optimize website loading speed
c.	To handle server-side scripting
6)	What is the purpose of a framework in web development ?
a.	To provide a structured environment for building web applications *<=*
b.	To handle network protocols and data transfer
c.	To create visual designs and layouts for websites
7)	What does NoSQL stand for ?
a.	Not Only SQL *<=* (Structured Query Language)
b.	Non-Structured Query Language
c.	New Object-Oriented Language
8)	Which of the following is a characteristic of NoSQL databases ?
a.	Strict schema enforcement
b.	Support for complex transactions
c.	Scalability and flexible data models *<=*
