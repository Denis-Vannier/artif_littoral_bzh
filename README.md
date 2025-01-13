# L'artificialisation du littoral breton de 2014 à 2024

**Vous trouverez ici les scripts de traitement et une partie des données utilisées dans le cadre de l'enquête ["Littoral breton, la tentation du béton"](https://splann.org/enquete/littoral-breton-tentation-beton/), publiée par Splann! et ses partenaires (Médiapart, France3, Médiacités, RadioBreizh, ...).**

**Nous avons mobilisé une grande diversité de sources : permis de construire, documents d’urbanisme, recensements Insee, BD Topo, transactions foncières, données brutes du Cerema… Cette approche nous permet d’offrir une vision à la fois très détaillée de l’évolution du littoral, au bâtiment près, tout en faisant ressortir des chiffres inédits sur l’ensemble du littoral breton.**

**Les données ont été traitées pour l’essentiel en langage Python. Nous avons également utilisé le logiciel libre QGIS et la librairie javascript Mapshaper. Les cartes interactives s’appuient sur la librairie MapboxGL.js. Les fonds de cartes sont issus le plus souvent de l’IGN et des contributeurs OpenStreetMap.**

<img src="(https://github.com/Denis-Vannier/artif_littoral_bzh/blob/main/img/accueil_enquete.png)" width="1000" />

## L’artificialisation
Il y a plusieurs manières d’évaluer l’artificialisation des sols. Le Cerema (Centre d'études et d'expertise sur les risques, l'environnement, la mobilité et l'aménagement) produit des indicateurs de consommation d’espaces sur son portail Mon Diagnostic Artificialisation, à partir des fichiers fonciers de l’administration fiscale (DGFIP). Un parcelle sur laquelle se trouve une construction est considérée comme artificialisée, quelque soit sa taille. Ces données sont progressivement complétées avec les cartographies très détaillées de l’occupation du sols tirées des images aériennes, l’OCS-GE, produit par l’IGN. 
En Région Bretagne, les professionnels de l’aménagement du territoire disposent maintenant d’une base précise de la consommation d’espaces, avec le MOS Foncier, issu d’interprétations d’images aériennes. Ces données servent de base de discussion pour l’application du Zéro artificialisation nette (ZAN) en Bretagne.   
Nous avons ajouté une autre méthode, en nous appuyant sur l’empreinte des bâtiments recensés par l’IGN dans sa BDTopo en 2014 et en 2024. Ces données nous permis de tracer des zones urbanisés, en suivant une méthode semblable à celle employée par l’IGN (dilatation-érosion). Ces chiffres correspondent donc à une estimation basse de l’artificialisation des sols, en mettant de côté les constructions réalisées sur des terrains nus déjà encerclées par l’urbanisation.

## Les bandes littorales
Notre analyse se concentre sur les 5 premiers kilomètres à partir du rivage. Nous avons sectorisé ce territoire par bandes tout le long de la côte bretonne, du Mont-Saint-Michel au Pays de Retz : 100 mètres, 200 mètres, 500 mètres, 1 km, 5 km. Pour réaliser ce découpage inédit de la manière la plus précise possible, nous nous sommes appuyés sur la “limite terre-mer”, tracé officiel des côtes françaises établie par le SHOM. La “bande des 100 mètres” que nous représentons ici, et qui n’avait jamais été cartographiée à cette échelle auparavant, respecte la définition qui en est donnée par la Loi Littoral. Ce tracé n’a toutefois aucune valeur légale. Les limites précises pouvant être remises en question devant un tribunal administratif avec des relevés de terrain. Le programme conçu pour réaliser ce découpage est disponible ici et peut être réutilisé librement.

## Les permis de construire
Nous sommes parvenus à identifier tous les permis de construire responsables de l’avancée des zones urbaines depuis 10 ans dans les 5 premiers kilomètres du littoral. 
Nous avons exploité la base de données SITADEL, maintenue par le ministère de la transition écologique, qui recense toutes les autorisations d’urbanisme délivrées par les communes depuis janvier 2013. De ces fichiers particulièrement volumineux, nous avons retenu uniquement les permis accordés entre le 1er janvier 2013 et le 30 septembre 2024 pour la construction d’un nouveau bâtiment. Nous avons ensuite filtré les permis délivrés en dehors des zones déjà urbanisées en 2014. Une seconde sélection a été aplliquée pour les permis représentés sur cette carte (lien carte exploratoire). Il s’agit unquement des quelque 7000 autorisations en cours de validité (en tenant compte de la possibilité de prolongation de deux fois 1 an, soit tous les permis délivrés après le 1er janvier ) pour des parcelles situées en dehors des zones déjà urbanisées en début d’année 2024. 

## Les documents d’urbanisme
Le zonage d’urbanisme que nous avons observé est extrait du Géoportail de l’urbanisme. Cette plateforme en accès libre regroupe les PLU, PLUI ou Cartes communales en vigueur, couvrant 370 communes littorales et rétro-littorales soit 88% du territoire (67 communes dépendent du RNU ou n’ont pas mis à disposition leur documenst d’urbanisme sous forme numérique).
Nous avons analysé en profondeur tous les PLU du littoral breton en vigueur à la date du 1er mai 2024. L’étude des règlements graphiques et écrits, comparés à l’urbanisation constatée des communes, nous a permis d’établir des listes des fragilités juridiques de ces documents d’urbanisme. Les dossiers constitués aux fins des enquêtes publiques après arrêté de ces documents et en vue de leur approbation ont été particulièrement riches d’enseignements, en ce qu’ils consignent tous les avis des Personnes Publiques associées (services de l’état, chambre d’agriculture, associations de protection de l’environnement, etc.) sur leurs potentielles irrégularités, faiblesses ou incohérences. Nous avons complété ce travail par la consultation des décisions de justice.

## Les sources
    • Localisation des bâtiments : BD Topo (millésimes 2014 et 2024)
    • Classement des communes littorales : Observatoire des territoires - ANCT
    • Contours des communes : Admin Express, IGN, décembre 2023
    • Documents d’urbanisme : Géoportail de l’urbanisme et OpenDataArchives
    • Population : Insee, recensements
    • Articificialisation par communes : Cerema
    • Modèle d'occupation du sol foncier : MOS Foncier de Bretagne 
    • Permis de construire : Ministère des territoires, de l’écologie et du logement, SITADEL
    • Transactions foncières :  Cerema, Demande des Valeurs Foncières (DVF).
    • Résidences secondaires : Insee, Recensement de la population, Logements et résidences principales en 2020 et Logements et résidences principales en 2014.
    • Evolution des effectifs scolaires : Ministère de l’Education nationale : Annuaire de l'éducation 2023 / Effectifs d'élèves des écoles 2015-2019 / Effectifs d’élèves 2019-2022
