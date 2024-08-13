# Personalized-Automatic-Emails-Responses

Ce projet a pour objectif de fine-tuner le modèle Llama-2 pour qu'il puisse générer des mails de réponse personnalisés. Nous nous concentrons particulièrement sur le style d'écriture d'un employé de l'entreprise américaine Enron : Jeff Dasovich. Pour cela, nous allons effectuer deux expériences.

## Cloner le Dépôt 

Pour commencer, clonez le dépôt Git contenant les notebooks et les données nécessaires avec la commande : 
`git clone https://github.com/AndriamMiora/Personalized-Automatic-Emails-Responses.git`

Ensuite, naviguez dans le répertoire cloné : avec la commande `cd Personalized-Automatic-Emails-Responses`


Ce répertoire contient 3 dossiers et 2 notebooks :

- **Experience1** : 
  - 1 fichier : `Experience1.ipynb`
  - 5 fichiers CSV
  - 1 fichier TXT : `requirements.txt`

- **Experience2** : 
  - 1 fichier : `Experience2.ipynb`
  - 7 fichiers CSV
  - 1 fichier TXT : `requirements.txt`
 
- **small_dataset** : 
  - 2 fichiers CSV : `minitest.csv` et `minitrain.csv` qui contiennent un petit jeu de données (4 et 8 mails) pour tester rapidement si le code fonctionne
 
- **Test_Results_experience_1 et Test_Results_experience_2** : 
  - `Test_Results_experience_1.ipynb` : notebook pour tester les modèles générés après l'expérience 1 sur un exemple spécifique et voir les résultats
  - `Test_Results_experience_2.ipynb` : notebook pour tester les modèles générés après l'expérience 2 sur un exemple spécifique et voir les résultats
 

Vous pouvez ensuite déposer ces fichiers sur votre Drive car les notebooks ont été configurés pour fonctionner sur Google Collab.

## Experience1.ipynb : Entraînement sur plusieurs employés, test sur un employé spécifique

**Objectif :** Fine-tuner le modèle Llama-2 pour qu'il puisse générer des mails de réponses personnalisés grâce à 4 jeux de données contenant les mails de plusieurs employés, et tester sur les mails d'un employé spécifique : Jeff Dasovich. Pour tester si nous avons réussi à imiter de manière efficace le style de Jeff Dasovich, nous réalisons quatre expériences. Théoriquement, les métriques de l’expérience exp1.J-J devraient être supérieures à celles des autres.

Pour mieux structurer les données, quatre dossiers seront créés pour les quatre expériences, où seront stockés les modèles entraînés :
- **exp1.J-J** : Modèle entraîné sur les mails de Jeff Dasovich et testé sur ceux de Jeff Dasovich
- **exp2.K-J** : Modèle entraîné sur les mails de Kay Mann et testé sur ceux de Jeff Dasovich
- **exp3.C-J** : Modèle entraîné sur les mails de Chris Germany et testé sur ceux de Jeff Dasovich
- **exp4.R-J** : Modèle entraîné sur les mails de personnes aléatoires et testé sur ceux de Jeff Dasovich

Il suffit d’ouvrir le notebook, d’installer les packages et de suivre les instructions en indiquant les bons chemins vers les fichiers CSV et les bons dossiers.

**12 Fichiers obtenus après l'exécution du notebook :**
- 4 fichiers `results_summary.txt` avec les métriques obtenues après les 4 expériences
- 4 dossiers `log` pour tracer la courbe de perte d'entraînement
- 4 fichiers `training_duration.txt` avec la durée d'entraînement des modèles

**6 Fichiers nécessaires :**
- `requirements.txt` : Contient les versions des packages nécessaires
- `jeff_dasovich_train_625.csv` (625, 9) et `jeff_dasovich_test_157.csv` (157, 9) : Contient les 625 mails de Jeff Dasovich pour l'entraînement et les 157 mails pour le test
- `chris.germany_train_625.csv` (625, 9) : Contient les 625 mails de Chris Germany pour l'entraînement
- `kay_mann_train_625.csv` (625, 9) : Contient les 625 mails de Kay Mann pour l'entraînement
- `random_train_625.csv` (625, 9) : Contient les 625 mails d'employés pris de manière aléatoire pour l'entraînement

## Experience2.ipynb : Entraînement et test sur des mails d'un employé spécifique

**Objectif :** Tester si l'augmentation du nombre de mails améliore les performances du modèle. Fine-tuner le modèle Llama-2 pour qu'il puisse générer des mails de réponses personnalisés grâce à 6 jeux de données contenant les mails de Jeff Dasovich de tailles différentes (144, 288, 432, 576, 720, 863 mails) et tester sur des mails de Jeff Dasovich. Six expériences seront réalisées.

Pour mieux structurer les données, six dossiers seront créés pour les six expériences, où seront stockés les modèles entraînés :
- **exp1.144** : Modèle entraîné sur les 144 mails de Jeff Dasovich et testé sur 215 autres mails de Jeff Dasovich
- **exp2.288** : Modèle entraîné sur les 288 mails de Jeff Dasovich
- **exp3.432** : Modèle entraîné sur les 432 mails de Jeff Dasovich
- **exp4.576** : Modèle entraîné sur les 576 mails de Jeff Dasovich
- **exp5.720** : Modèle entraîné sur les 720 mails de Jeff Dasovich
- **exp6.863** : Modèle entraîné sur les 863 mails de Jeff Dasovich

Il suffit d’ouvrir le notebook, d’installer les packages et de suivre les instructions en indiquant les bons chemins vers les fichiers CSV et les bons dossiers.

**18 Fichiers obtenus après l'exécution du notebook :**
- 6 fichiers `results_summary.txt` avec les métriques obtenues après les 6 expériences
- 6 dossiers `log` pour tracer la courbe de perte d'entraînement
- 6 fichiers `training_duration.txt` avec la durée d'entraînement des modèles

**8 Fichiers nécessaires :**
- `requirements.txt` : Contient les versions des packages nécessaires
- `jeff_dasovich_train_863.csv` (863, 9) et `jeff.dasovich_test_215.csv` (215, 9) : Contient les 863 mails de Jeff Dasovich pour l'entraînement et les 215 mails pour le test
- `jeff_dasovich_train_144.csv` (144, 9) : Contient les 144 mails de Jeff Dasovich
- `jeff_dasovich_train_288.csv` (288, 9) : Contient les 288 mails de Jeff Dasovich
- `jeff_dasovich_train_432.csv` (432, 9) : Contient les 432 mails de Jeff Dasovich
- `jeff_dasovich_train_576.csv` (576, 9) : Contient les 576 mails de Jeff Dasovich
- `jeff_dasovich_train_720.csv` (720, 9) : Contient les 720 mails de Jeff Dasovich
