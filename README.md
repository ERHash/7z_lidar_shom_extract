# 7z_lidar_shom_extract
Ce projet permet d'extraire et de rassembler les données LIDAR fournies par le SHOM.

# Script de décompression et de déplacement de fichiers .asc

Ce script extrait des fichiers `.asc` à partir de fichiers `.7z` dans un dossier spécifié et les déplace dans un dossier cible. Il est utile pour travailler avec des fichiers lidar.

## Prérequis

- Python 3.x
- Bibliothèque `py7zr`
- Bibliothèque `shutil`

## Installation

Clone ce repository et installe les dépendances :

```bash
pip install py7zr
