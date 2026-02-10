# Fine-tuning de YOLOv8 pour la Détection de Véhicules

## Description du Projet
Ce projet consiste à adapter le modèle de détection d'objets YOLOv8 pour reconnaître spécifiquement les véhicules dans des scènes de trafic routier. Le fine-tuning a été effectué sur le dataset UA-DETRAC, permettant au modèle d'atteindre une haute précision dans des conditions variées (météo, éclairage, densité du trafic).

## Objectifs
- **Adapter** YOLOv8 à la détection de véhicules dans un contexte routier
- **Optimiser** les performances pour différents types de véhicules (voitures, bus, camions)
- **Créer** un pipeline complet de préparation des données et d'entraînement
- **Évaluer** les performances avec des métriques pertinentes (mAP50, précision, rappel)

## Technologies Utilisées
- **YOLOv8** (Ultralytics) - Modèle de détection d'objets
- **PyTorch** - Framework d'apprentissage profond
- **OpenCV** - Traitement d'images et visualisation
- **Pandas/Numpy** - Analyse et manipulation de données
- **Kaggle NoteBook** - Environnement d'entraînement avec GPU
- **Kaggle Datasets** - Source des données d'entraînement

## Dataset
**UA-DETRAC** : Dataset spécialisé pour la détection et le tracking de véhicules
- 84,000+ images annotées
- Conditions variées (jour/nuit, météo changeante)
- 4 classes originales : car, van, bus, truck
- Conversion en format YOLO pour l'entraînement

## Fonctionnalités Implémentées
1. **Préparation des données**
   - Conversion des annotations au format YOLO
   - Nettoyage et validation des labels
   - Création de sous-ensembles équilibrés
   - Répartition train/val/test (70%/20%/10%)

2. **Configuration du modèle**
   - Adaptation des classes (regroupement van/car → "car")
   - Création du fichier `data.yaml`
   - Configuration des hyperparamètres d'entraînement

3. **Entraînement**
   - Fine-tuning de YOLOv8s
   - Optimisation sur GPU
   - Augmentation de données
   - Early stopping et sauvegarde des meilleurs poids

4. **Évaluation**
   - Métriques de performance (mAP50, précision, rappel)
   - Visualisation des résultats
   - Matrice de confusion
   - Tests sur données de validation

## Métriques de Performance
- Le modèle est évalué sur plusieurs indicateurs clés :
- **mAP50** : Mean Average Precision à IoU=50%
- **Précision** : Proportion de détections correctes
- **Rappel** : Capacité à détecter tous les véhicules

## Résultats
Le modèle fine-tuné atteint des performances élevées sur le dataset UA-DETRAC :
- **mAP50** = 0.99364
- **Précision** = 0.98244
- **Rappel** = 0.98219
- Détection robuste dans diverses conditions

## Applications Futures
- Tracking des véhicules avec DeepSORT
- Comptage automatique du trafic
- Prédiction de la densité du trafic
- Détection d'anomalies routières
- Intégration avec des systèmes de surveillance
