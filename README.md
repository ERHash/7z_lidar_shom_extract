# 7z_lidar_shom_extract
Ce projet permet d'extraire et de rassembler les thuiles des données LIDAR partagées par le SHOM dans des formats 7z.
Voir ici : https://diffusion.shom.fr/donnees/altimetrie-littorale.html

## 📝 Description
Ce script Python extrait des fichiers .asc à partir de fichiers .7z dans un dossier spécifié et les déplace dans un dossier cible. 

## 🚀 Prérequis

Python 3.x

Bibliothèque py7zr pour décompresser les archives .7z

Bibliothèque shutil pour déplacer les fichiers extraits

```
bash
pip install py7zr
```


## 💻 Utilisation
Variables à définir
Avant d'exécuter le script, voici les variables importantes à configurer dans le fichier Python :

- **zip_folder**: Dossier où se trouvent les fichiers .7z à extraire. Par défaut, le script cherche les fichiers .7z dans le même dossier où il est exécuté.
    
* **extract_to**: Dossier où les fichiers extraits seront placés temporairement avant d'être déplacés.
    
+ **target_folder**: Nom du sous-dossier où les fichiers .asc seront extraits à l'intérieur de chaque archive .7z.
    
- **file_extension** : L'extension des fichiers à extraire (dans ce cas, .asc).

Lancer le script
Une fois les variables configurées, tu peux lancer le script pour extraire et déplacer les fichiers :

```
python 7z_lidar_shom_extract.py
```

## 🔧 Fonctionnement du script
Extraction des fichiers .7z et déplacelement des fichiers asc: 

1. Le script ouvre chaque fichier .7z trouvé dans le dossier spécifié et extrait tous les fichiers à l'intérieur dans un dossier provisoire (supprimé par la suite)

2. Filtrage des fichiers .asc : Après extraction, le script cherche les fichiers avec l'extension .asc dans les sous-dossiers spécifiés (ici, MNT1m). 

3. Déplacement des fichiers : Les fichiers .asc trouvés sont ensuite déplacés dans le dossier de destination spécifié (extract_to).

Exemple de structure de dossier avant et après extraction :
Avant extraction

```
/mon/dossier/7z
    ├── fichier1.7z
    ├── fichier2.7z
    └── fichier3.7z
```
    
Après extraction et déplacement

```
/mon/dossier/extracted
    ├── fichier1.asc
    ├── fichier2.asc
    └── fichier3.asc
```
    
## 🔑 License
Ce projet est sous la Licence MIT. Libre.

## 🙏 Remerciements
SHOM pour la fourniture des données LIDAR.

La bibliothèque py7zr pour l'extraction des fichiers .7z.

