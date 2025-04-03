import os
import py7zr
import shutil

def unzip_asc_files(zip_folder, extract_to, target_folder, file_extension):
 # Créer le dossier de destination si nécessaire
 if not os.path.exists(extract_to):
     os.makedirs(extract_to)
     print(f'Dossier de destination créé : {extract_to}')
 
 zip_files_found = False  # Pour savoir si des fichiers 7z ont été trouvés
 for file in os.listdir(zip_folder):
     if file.endswith('.7z'):
         zip_files_found = True
         file_path = os.path.join(zip_folder, file)
         print(f'\nOuverture de l\'archive 7z : {file_path}')
         
         try:
             with py7zr.SevenZipFile(file_path, mode='r') as archive:
                 # Extraire tous les fichiers dans le dossier temporaire
                 archive.extractall(path=extract_to)
                 print(f'Tous les fichiers extraits de {file} vers {extract_to}')
                 
                 # Parcours des fichiers extraits pour récupérer ceux qui correspondent
                 for root, dirs, files in os.walk(extract_to):
                     for file in files:
                         if target_folder in root and file.endswith(file_extension):
                             extracted_file_path = os.path.join(root, file)
                             print(f'Fichier .asc trouvé et extrait : {extracted_file_path}')
                             
                             # Déplacement du fichier vers le dossier cible
                             destination_path = os.path.join(extract_to, file)
                             shutil.move(extracted_file_path, destination_path)
                             print(f'Fichier déplacé vers : {destination_path}')
                 
                 # Nettoyage des fichiers temporaires après l'extraction
                 shutil.rmtree(extract_to)
                 print(f'Fichiers temporaires supprimés : {extract_to}')
         except Exception as e:
             print(f'Erreur lors de l\'extraction de {file}: {e}')

# Définition des chemins
zip_folder = os.getcwd()  # Dossier courant
extract_to = os.path.join(zip_folder, "asc_folder")  # Dossier où on extrait et rassemble les fichiers

# Dossier à vérifier et extension des fichiers
target_folder = 'MNT1m'  # Le sous-dossier dans lequel chercher
file_extension = '.asc'  # Extension des fichiers à extraire

# Exécution de la fonction
unzip_asc_files(zip_folder, extract_to, target_folder, file_extension)
