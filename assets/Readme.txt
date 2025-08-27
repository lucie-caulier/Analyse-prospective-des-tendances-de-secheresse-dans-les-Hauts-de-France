  
Contenu du fichier téléchargé

Le fichier contient des sous-répertoires dont les noms sont composés des lettres de A à Y. Chaque lettre représente le nom d’une région hydrographique. La liste des régions hydrographiques est la suivante :
    • A : Rhin 
    • B : Meuse 
    • D : Affluents du Rhin 
    • E : Fleuves côtiers (Escault, Somme, ...) 
    • F : H Seine 
    • G : Fleuves côtiers hauts normands 
    • I : Fleuves côtiers bas normands 
    • J : Bretagne 
    • K : Loire - Source à Vienne 
    • L : Loire - Vienne à Maine 
    • M : Loire - Maine à Mer 
    • N : Fleuves côtiers du sud de la Loire 
    • O : Garonne 
    • P : Dordogne 
    • Q : Adour 
    • R : Charente 
    • U : Saône 
    • V : Rhône 
    • W : Isère 
    • X : Durance 
    • Y : Fleuves côtiers et Corse 
Chaque sous-répertoire contient des fichiers CSV relatifs aux données des indicateurs de débits pour une région spécifique, en fonction d'un modèle hydraulique et d’un scénario RCP.

Structure des fichiers CSV
Les fichiers CSV suivent une structure particulière, décrivant à la fois le type de données (simulation, spatialisation d’observations, etc.) et le projet concerné. Les grandes caractéristiques des fichiers sont les suivantes :
    • Chaque fichier contient un seul indicateur, en plus des informations suivantes : latitude, longitude, coordonnées L93, région hydrographique ou domaine, surface du bassin versant, période de calcul de l'indicateur et le temps. Ces données correspondent à un seul fichier d'entrée, par exemple la simulation d’un seul modèle et d’une seule expérience (scénario ou période historique). 
    • Chaque fichier couvre l'intégralité de la période modélisée pour l'expérience (scénario ou période historique) et se limite à la région définie dans le nom du fichier. 

Nom du fichier
Le nom du fichier est conçu de manière à fournir rapidement des informations sur la simulation et suit les étapes de la chaîne de calculs. Les éléments sont séparés par un underscore ('_') et suivent le format suivant :
Indicator_TimeFrequency_StartTime-EndTime_TIMEoperation_GEOdata_Domain_EXPLORE2-2024_DATASET.csv

    1. Position 1 – Indicator : Nom de l'indicateur. Une liste des indicateurs débits est disponible sur le site Drias-Eau. 

    2. Position 2 – TimeFrequency : Fréquence temporelle du traitement des données. 
        ? Pour un indicateur mensuel, un seul fichier contiendra tous les mois. 
        ? mon : Pour une fréquence mensuelle. 
        ? seas-SSS : Pour une fréquence saisonnière, avec "SSS" représentant la première lettre des mois concernés (par exemple, "seas-DJF" pour Décembre-Janvier-Février). 
        ? yr : Pour une fréquence annuelle. 
        ? hyr : Pour une fréquence annuelle selon l'année hydrologique. 
          
    3. Position 3 – StartTime-EndTime : Période de couverture temporelle de la série. 

    4. Position 4 – TIMEoperation : Opération temporelle appliquée aux données. Cela peut être une série temporelle ou une agrégation. 
        ? TIMEseries : Pour les séries temporelles. 

    5. Position 5 – Domain : Couverture spatiale des données, indiquée par la région. Par exemple, "J" pour la région Bretagne. 

    6. Position 6 – DATASET : Nom complet de la simulation, comprenant des acronymes pour les modèles utilisés.

       Jeu_Correction_Experiment_MODEL
        - Model : Par exemple, pour un modèle individuel GCM-RCM corrigé, le format est : MODEL = GCM-Model_RCM-Model.
Exemple : DRIAS-2020_MF-ADAMONT_historical_CNRM-CM5_ALADIN63
       - Jeu : Nom du projet dans lequel ont été produits ces simulations => nom, petit tiret, année
       - Correction : Identifiant de la méthode de correction de biais statistique = Institut-Méthode
       • MF-ADAMONT
       • LSCE-IPSL-CDFt
       
       - Experiment : Identifiant de l’expérience historique ou future via le scénario
       • données historiques : historical
       • scénarios : rcp26, rcp45 ou rcp85, ssp126, ssp245, ….
