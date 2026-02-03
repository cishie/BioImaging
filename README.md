# Deep Learning for Computer Vision – Travaux Pratiques

Ce dépôt regroupe plusieurs travaux pratiques consacrés aux **tâches fondamentales de la vision par ordinateur** à l’aide du **Deep Learning**.  
Les notebooks proposent une approche progressive, depuis la **classification d’images**, jusqu’à la **détection d’objets** et la **segmentation sémantique**, avec des applications sur des jeux de données standards et réels.
## Contenu du projet

Le projet est structuré autour de trois notebooks principaux :

- `classification.ipynb`  
- `detection.ipynb`  
- `segmentation.ipynb`  

Chaque notebook est autonome et contient :
- des explications théoriques,
- la préparation des données,
- l’implémentation des modèles,
- l’entraînement,
- l’évaluation et l’analyse des résultats.

## 1️.Classification d’images – `classification.ipynb`

### Objectif
Introduire les bases du **Deep Learning pour la classification d’images**, en comparant des architectures simples (MLP) à des architectures adaptées aux images (CNN).

### Jeux de données utilisés
- **MNIST** : chiffres manuscrits (images 28×28 en niveaux de gris)
- **CIFAR-10** : images couleur 32×32 réparties en 10 classes

### Méthodes abordées
- Implémentation d’un **Multi-Layer Perceptron (MLP)**
- Implémentation d’un **réseau de neurones convolutif (CNN)**
- Comparaison MLP vs CNN
- Analyse des performances via :
  - précision,
  - matrices de confusion,
  - visualisation des prédictions
- Étude de l’impact de la **data augmentation** sur la généralisation

### Points clés
- Les MLPs sont adaptés aux images simples mais échouent sur des images complexes
- Les CNN exploitent la structure spatiale des images et offrent de meilleures performances
- La data augmentation agit comme un régularisateur efficace

---

## 2.Détection d’objets – `detection.ipynb`

### Objectif
Découvrir la **détection d’objets**, qui consiste à **localiser et classifier plusieurs objets** dans une même image à l’aide de **boîtes englobantes (bounding boxes)**.

### Jeu de données
- **MinneApple Dataset** : images de vergers avec détection de pommes

### Méthodes et concepts abordés
- Différences entre classification, segmentation et détection
- Notions clés :
  - bounding boxes,
  - Intersection over Union (IoU),
  - Non-Maximum Suppression (NMS),
  - seuils de confiance
- Préparation des données au **format YOLO**
- Entraînement d’un modèle **YOLOv8 (nano)** avec transfert d’apprentissage
- Évaluation avec :
  - précision,
  - rappel,
  - mAP@0.5 et mAP@0.5:0.95
- Analyse qualitative des prédictions et des erreurs

### Points clés
- YOLO permet une détection rapide en une seule passe
- Le seuil de confiance influence le compromis précision / rappel
- La qualité et la densité des annotations impactent fortement les performances

---

## 3.Segmentation sémantique – `segmentation.ipynb`

### Objectif
Mettre en œuvre la **segmentation sémantique**, qui consiste à attribuer une **classe à chaque pixel** d’une image.

### Application
- **Segmentation de tumeurs cérébrales** à partir d’images d’IRM

### Jeu de données
- Dataset médical annoté au format **COCO**

### Méthodes abordées
- Création d’un **Dataset personnalisé PyTorch**
- Extraction des masques de segmentation depuis les annotations COCO
- Implémentation d’un **réseau U-Net**
- Entraînement avec la **Binary Cross-Entropy avec logits**
- Évaluation via :
  - Dice Score,
  - IoU,
  - Pixel Accuracy
- Mise en place de **data augmentation synchronisée image / masque**

### Points clés
- Les skip connections du U-Net permettent une segmentation précise
- Les métriques Dice et IoU sont mieux adaptées aux données déséquilibrées
- En segmentation, toute transformation spatiale doit être appliquée **simultanément à l’image et au masque**
## Technologies et bibliothèques utilisées

- Python  
- PyTorch / Torchvision  
- Ultralytics (YOLOv8)  
- NumPy  
- Matplotlib  
- tqdm  
- pycocotools  
## Objectifs pédagogiques globaux

- Comprendre les différences entre **classification, détection et segmentation**
- Implémenter et entraîner des modèles de Deep Learning pour la vision
- Manipuler des jeux de données images réels et annotés
- Évaluer et analyser les performances des modèles
- Appréhender les enjeux liés à la data augmentation et à la généralisation
## Remarque

Ces travaux ont été réalisés dans un **cadre académique** à des fins d’apprentissage et d’expérimentation autour du **Deep Learning appliqué à la vision par ordinateur**.

---
