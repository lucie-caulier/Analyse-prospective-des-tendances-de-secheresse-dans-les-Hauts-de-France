  
Contenu du fichier t�l�charg�

Le fichier contient des sous-r�pertoires dont les noms sont compos�s des lettres de A � Y. Chaque lettre repr�sente le nom d�une r�gion hydrographique. La liste des r�gions hydrographiques est la suivante :
    � A : Rhin 
    � B : Meuse 
    � D : Affluents du Rhin 
    � E : Fleuves c�tiers (Escault, Somme, ...) 
    � F : H Seine 
    � G : Fleuves c�tiers hauts normands 
    � I : Fleuves c�tiers bas normands 
    � J : Bretagne 
    � K : Loire - Source � Vienne 
    � L : Loire - Vienne � Maine 
    � M : Loire - Maine � Mer 
    � N : Fleuves c�tiers du sud de la Loire 
    � O : Garonne 
    � P : Dordogne 
    � Q : Adour 
    � R : Charente 
    � U : Sa�ne 
    � V : Rh�ne 
    � W : Is�re 
    � X : Durance 
    � Y : Fleuves c�tiers et Corse 
Chaque sous-r�pertoire contient des fichiers CSV relatifs aux donn�es des indicateurs de d�bits pour une r�gion sp�cifique, en fonction d'un mod�le hydraulique et d�un sc�nario RCP.

Structure des fichiers CSV
Les fichiers CSV suivent une structure particuli�re, d�crivant � la fois le type de donn�es (simulation, spatialisation d�observations, etc.) et le projet concern�. Les grandes caract�ristiques des fichiers sont les suivantes :
    � Chaque fichier contient un seul indicateur, en plus des informations suivantes : latitude, longitude, coordonn�es L93, r�gion hydrographique ou domaine, surface du bassin versant, p�riode de calcul de l'indicateur et le temps. Ces donn�es correspondent � un seul fichier d'entr�e, par exemple la simulation d�un seul mod�le et d�une seule exp�rience (sc�nario ou p�riode historique). 
    � Chaque fichier couvre l'int�gralit� de la p�riode mod�lis�e pour l'exp�rience (sc�nario ou p�riode historique) et se limite � la r�gion d�finie dans le nom du fichier. 

Nom du fichier
Le nom du fichier est con�u de mani�re � fournir rapidement des informations sur la simulation et suit les �tapes de la cha�ne de calculs. Les �l�ments sont s�par�s par un underscore ('_') et suivent le format suivant :
Indicator_TimeFrequency_StartTime-EndTime_TIMEoperation_GEOdata_Domain_EXPLORE2-2024_DATASET.csv

    1. Position 1 � Indicator : Nom de l'indicateur. Une liste des indicateurs d�bits est disponible sur le site Drias-Eau. 

    2. Position 2 � TimeFrequency : Fr�quence temporelle du traitement des donn�es. 
        ? Pour un indicateur mensuel, un seul fichier contiendra tous les mois. 
        ? mon : Pour une fr�quence mensuelle. 
        ? seas-SSS : Pour une fr�quence saisonni�re, avec "SSS" repr�sentant la premi�re lettre des mois concern�s (par exemple, "seas-DJF" pour D�cembre-Janvier-F�vrier). 
        ? yr : Pour une fr�quence annuelle. 
        ? hyr : Pour une fr�quence annuelle selon l'ann�e hydrologique. 
          
    3. Position 3 � StartTime-EndTime : P�riode de couverture temporelle de la s�rie. 

    4. Position 4 � TIMEoperation : Op�ration temporelle appliqu�e aux donn�es. Cela peut �tre une s�rie temporelle ou une agr�gation. 
        ? TIMEseries : Pour les s�ries temporelles. 

    5. Position 5 � Domain : Couverture spatiale des donn�es, indiqu�e par la r�gion. Par exemple, "J" pour la r�gion Bretagne. 

    6. Position 6 � DATASET : Nom complet de la simulation, comprenant des acronymes pour les mod�les utilis�s.

       Jeu_Correction_Experiment_MODEL
        - Model�: Par exemple, pour un mod�le individuel GCM-RCM corrig�, le format est : MODEL = GCM-Model_RCM-Model.
Exemple : DRIAS-2020_MF-ADAMONT_historical_CNRM-CM5_ALADIN63
       - Jeu : Nom du projet dans lequel ont �t� produits ces simulations => nom, petit tiret, ann�e
       - Correction : Identifiant de la m�thode de correction de biais statistique = Institut-M�thode
       � MF-ADAMONT
       � LSCE-IPSL-CDFt
       
       - Experiment : Identifiant de l�exp�rience historique ou future via le sc�nario
       � donn�es historiques : historical
       � sc�narios : rcp26, rcp45 ou rcp85, ssp126, ssp245, �.
