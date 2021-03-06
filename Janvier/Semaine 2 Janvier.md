﻿# Semaine du 06/01/2020 au 10/01/2020

  

  

## 06/01/2020:

### *Objectifs et livrables du jour:*

- Présentation des droits d’admin et ses aspects
- Présentation des corrections d’exercices en lien avec les droits d’admin
- Présentation du Projet «Siren Open Data», Veille et documentation
- Création de la base de donnée
- Alimentation de la base de donné

'mysql+pymysql://scott:tiger@localhost/foo'

scott: root ou user1 exemple: Yacine
tiger: mon mdp
foo: ma bse de données ex «jeux_video»

### *Outils utilisé:*

- MySQL
- Workbench
- Anaconda
- JupyterNotebook

### *Difficultés rencontrés:*

- Importation en fichier csv
- Compréhension du programme qui réalise l’importation

## 07/01/2020:

_**Objectifs et livrables du jour:**_

-  Toujours sur le projet Open Siren Data, alimentation de la base de données
- Via la base de donnée crée sur MySQL Workbench
- Importation des fichiers «Stock_etablissement.csv» et «Hist_etablissement.csv»
- Prendre connaissance de la documentation
- Prise de connaissance sur l’indexation 

*Notes*:

 -import sqlalchemy
-import pandas as pd
-import time

engine = sqlalchemy.create_engine('mysql+pymysql://misterheinz:simplon@localhost/siren_open_data')

def importcsv(link, table, date):
 print("Lecture des données")
 start_time = time.time()
 csize = 2000
 df = pd.read_csv(link, compression = 'zip', chunksize = csize, parse_dates = date
Je spécifie les colonnes qui sont dans parses_dates pour date 
 print("Données lu")
 i = csize
 for chunk in df:
 chunk.to_sql(table, con = engine, if_exists='append', index = False)
 i += csize
 print(i)
 return print("Temps d execution : %s secondes ---" % (time.time() - start_time))

importcsv('https://www.data.gouv.fr/fr/datasets/r/377fd07c-e37f-491a-a507-7bf5b690804b','stock_etab', ['anneeEffectifsEtablissement','dateCreationEtablissement', 'dateDernierTraitementEtablissement', 'dateDebut'])
importcsv('http://files.data.gouv.fr/insee-sirene/StockEtablissementHistorique_utf8.zip')

### *Outils utilisés:*
- Anaconda
- Spyder

### *Difficultés rencontrés:*

- Difficultés sur l’importation des données, lecture des données ralenties du à la mémoire vive qui est que de 4go de RAM 
- Maladresse sur l’écriture du script

## 08/01/2020:

### *Objectifs et livrables du jour:*

- Retour sur le modèle entité association
- Sur les modèle de programmation orienté objet
- Atelier : Restitution projet micropousses db *4 groupes / cadrage, dictionnaire de données, mcd, mld, mpd, dump.sql, trello, etc.

_**Outils utilisé:**_

-Excel
-Google Sheets

_**Difficultés rencontré:**_

- A revoir dépendances fonctionnelles 
- Modèle logique des données (MLD)

## 09/01/2020:

### *Objectifs et livrables du jour:*

- Atelier : projet siren_open_data (remote) / Atelier en groupe : Git mode "team", dépôt Github partagé, Readthedocs, DevData * 6 groupes
- Importation des données des tables «stock_etab» et «hist_etab»
- Revenir sur l’explication du Git partagé branche master.. 
- Trouver au moins 10 offres d’emploi par jours (Stage, réalisation chaque jour jusqu’a Mars, Google Sheets) 

### *Outils utilisés:*

- Anaconda
- Spyder
- JupyterNotebook
- Google Sheets 

### *Difficultés rencontrés:*

- Difficultés de compréhension sur le Git partagé, blocage au niveau de la lecture des données pour le projet siren_open_data

## 10/01/2020:

### *Objectifs et livrables du jour:*

- Atelier Google Sheets: MCD Modèle conceptuelle d’une base de données, Entité → Attribut →    Instance
- liste de plage nommé correspondent à au trait entre les association et les entités ou autre entité
- comment faire une liste déroulante
- comment faire une liste de plage nommé
- une colonne correspond a un attribut 
 et les lignes dans la colonne sont des objets ou instance ou «tuples»
- base de données orienté objet: c’est-à-dire importation des instances dans les attributs 

### *Outils utilisés:*

- Google Sheets

### *Difficultés rencontrés:*

- Aucune à ce jour
