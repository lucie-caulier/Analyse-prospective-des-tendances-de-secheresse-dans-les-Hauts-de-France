## rapports_analyse_prospective_tend_sech_HdF

# Objectif
Ce projet permet,  grâce à Rmarkdown,  de créer des rapports automatisés de l'analyse prospective des tendances de sécheresse par département des Hauts-de-France. Les analyses sont menées à partir des débits non influencés récupérés sur le portail Drias-eau d'explore2. 
Pour ces rapports, il a fallu faire des choix quant aux scénarios que nous allions utiliser. 
Chaque modélisation est composée d'un modèle hydrologique (SIM2, Orchidée, SMASH...), complété par un modèle climatique global (couvrant l’ensemble du globe avec une grande résolution, de 200-300km), ainsi que d'un modèle climatique régional (d’une résolution plus importante de 12.5km). 

Pour notre étude, nous avons sélectionné le modèle hydrologique SIM2 (particulièrement haute résolution spatiale et généralisation plus solide à des situations nouvelles ou extrêmes). Concernant les modèles climatiques, nous avons sélectionné les 4 mêmes que les scientifiques d'explore2, caractérisés par des modélisations contrastées du futur. Ces 4 scénarios, aussi appelés narratifs, sont les suivants : CNRM-CERFACS-CNRM-CM5 / CNRM-ALADIN63 (numéroté 1 dans notre travail), ICHEC-EC-EARTH / MOHC-HadREM3-GA7-05 (numéroté 2 dans notre travail), MOHC-HadGEM2-ES / CNRM-ALADIN63 (numéroté 3 dans notre travail) et MOHC-HadGEM2-ES / CLMcom-CCLM4-8-17 (numéroté 4 dans notre travail).

# Arborescence du projet

**assets**

Un document world servant de modèle pour le knit sous world. R recopie sa mise en page. 
Un sous-dossier vcn10 contenant différents documents excell. Ces derniers étaient nécessaires pour mon analyse, puisqu'ils contiennent les surfaces des bassins versants des stations étudiées. Elles permettent donc de calculer le vcn10 en fonction de la période étudiée. 
Un excell drias_hdf contenant les stations drias dans les Hauts-de-France dont on va se servir. 
Le fichier geopackage station_DRIAS_Hdf à l'origine du excell juste au-dessus (sélection des stations des Hauts-de-France grâce au logiciel QGIS). 

**functions**

Deux fichier R, chargés dans le programme principal, et contenant les fonctions dont nous avons besoin.

**raw_data**

Contient les fichiers texte SIM2 pour les différents narratifs et les différentes périodes de temps. Nous y trouvons les débits journaliers non influencés par station hydrométrique. 

**script**

Le dossier Rmarkdown principal, contenant les scrips et les textes à l'origine des rapports automatisés. 

