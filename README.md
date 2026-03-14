# Clustering d’activités humaines

Ce projet explore différentes méthodes de classification non supervisée pour regrouper des activités humaines à partir de signaux de capteurs de smartphones. Les activités considérées sont : la marche(1), la montée d’escaliers(2), la descente d’escaliers(3), la position assise(4), la position debout(5) et la position allongée(6).

## 🎯 Objectif
Évaluer la capacité de plusieurs méthodes de clustering à distinguer automatiquement des activités humaines à partir de séries temporelles multidimensionnelles. 

## 📊 Données
Les données proviennent du dataset public *Human Activity Recognition Using Smartphones* (Anguita et al., 2013).  
Chaque individu est représenté par **9 séries temporelles de 128 points**, correspondant à une fenêtre de 2,5 secondes.

## 🧠 Méthodologie

### 1. Extraction de caractéristiques
Pour chaque série temporelle :
- moyenne, variance, minimum, maximum  
- skewness, kurtosis  
- coefficient AR(1)  
- amplitude dominante de la FFT  

→ 72 caractéristiques par individu.

### 2. Standardisation
Normalisation Z‑score pour harmoniser les échelles.

### 3. Réduction de dimension
Méthodes testées :
- ACP (PCA)  
- Kernel PCA (RBF)  
- t‑SNE  

t‑SNE offre la meilleure séparation visuelle et est retenu pour le clustering.

### 4. Méthodes de clustering
- **K‑Means**  
- **Classification Ascendante Hiérarchique (Ward)**  
- **Clustering Spectral**

### 5. Évaluation
- ARI (Adjusted Rand Index)  
- NMI (Normalized Mutual Information)  
- Matrices de confusion  

## 📈 Résultats
- La **CAH (Ward)** obtient les meilleurs scores :  
  - ARI = 0.684  
  - NMI = 0.822  
- Les activités dynamiques sont bien séparées.  
- Les postures statiques restent difficiles à distinguer.

## 🛠️ Technologies utilisées
- Python  
- Scikit‑learn  
- Matplotlib / Seaborn  
- Jupyter Notebook  

## 📁 Structure du dépôt
```human-activity-clustering/
├── README.md
└── notebook/
  └── clustering_activites_humaines.ipynb
```

## 🚀 Exécution
Ouvrir le notebook dans Jupyter et exécuter les cellules dans l’ordre.

## 📚 Références
[1] Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra, Jorge L. Reyes-Ortiz (2013).  
A Public Domain Dataset for Human Activity Recognition Using Smartphones.  
21st European Symposium on Artificial Neural Networks, Computational Intelligence and Machine Learning (ESANN 2013), Bruges.


