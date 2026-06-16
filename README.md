# Projet Deep Learning — EMSI Casablanca 2025-2026

**Etudiante :** Aya Haffari  
**Module :** Deep Learning  
**Filiere :** Informatique  
**Annee universitaire :** 2025-2026  

---

## Idee generale du projet

Ce projet de fin de module couvre la conception, l'implementation, la comparaison et l'analyse critique de modeles de deep learning pour trois types de donnees :

| Partie | Architecture | Dataset | Resultat |
|--------|-------------|---------|----------|
| **Partie I** | MLP (Perceptron Multicouche) | Breast Cancer Wisconsin | Accuracy : 94.19% |
| **Partie II** | CNN (LeNet) | MNIST | Accuracy : ~99% |
| **Partie III** | RNN / LSTM / GRU / Seq2Seq | Corpus Sentiment & Traduction FR-EN | Perplexite basse |

L'objectif est de montrer comment le deep learning adapte ses architectures a la structure des donnees : tabulaire, image et sequentielle.

---

## Structure des dossiers

```
projet_deep_learning/
│
├── partie1_MLP/
│   ├── partie1_mlp.ipynb          # Notebook MLP complet
│   └── models/
│       └── meilleur_modele.pth    # Modele sauvegarde (Xavier, 94.19%)
│
├── partie2_CNN/
│   ├── partie2_cnn.ipynb          # Notebook CNN complet
│   ├── mnist_exemples.png         # Visualisation dataset MNIST
│   ├── feature_maps_conv1.png     # Feature maps Conv1 (6 filtres)
│   ├── feature_maps_conv2.png     # Feature maps Conv2 (16 filtres)
│   ├── mlp_vs_cnn.png             # Comparaison MLP vs CNN
│   └── comparaison_cnn.png        # Influence hyperparametres
│
├── partie3_RNN/
│   ├── partie3_rnn.ipynb          # Notebook RNN/LSTM/GRU/Seq2Seq
│   ├── comparaison_rnn_lstm_gru.png
│   ├── loss_seq2seq.png
│   └── evaluation_seq2seq.png
│
├── rapport/
│   ├── courbes_initialisations.png
│   └── matrice_confusion.png
│
├── question_finale.ipynb          # Question transversale finale
├── synthese_aya_haffari.docx      # Fiche de synthese complete
├── rapport_deep_learning.docx     # Rapport scientifique
└── README.md                      # Ce fichier
```

---

## Description des notebooks

### Partie I — MLP et PyTorch (`partie1_mlp.ipynb`)
- Construction MLP avec `nn.Sequential` et classe personnalisee
- Inspection des parametres (`named_parameters`, `state_dict`)
- 3 strategies d'initialisation : Gaussienne, Constante, Xavier
- Sauvegarde et rechargement du meilleur modele
- Metriques : Accuracy, Precision, Recall, F1-Score, Matrice de confusion

### Partie II — CNN et Vision (`partie2_cnn.ipynb`)
- Implementation manuelle de la correlation croisee 2D et du pooling
- Architecture LeNet avec convolution 1x1
- Comparaison MLP vs CNN sur MNIST
- Etude de l'influence : padding, stride, nombre de filtres
- Visualisation des feature maps

### Partie III — RNN/LSTM/GRU/Seq2Seq (`partie3_rnn.ipynb`)
- Implementation RNN simple, LSTM et GRU
- Comparaison : stabilite, performance, memoire, cout de calcul
- Gradient clipping (max_norm=1.0) et BPTT
- Systeme Seq2Seq (encodeur-decodeur) avec teacher forcing
- Decodage glouton et Beam Search (k=3)
- Evaluation par perplexite

### Question transversale (`question_finale.ipynb`)
- Synthese comparative MLP / CNN / RNN
- Analyse de l'inductive bias selon la structure des donnees

---

## Technologies utilisees

- **Python** 3.14.4
- **PyTorch** 2.12.0+cpu
- **NumPy** 2.4.6
- **Pandas** 3.0.3
- **Scikit-learn** 1.8.0
- **Matplotlib** 3.10.9
- **Seaborn** 0.13.2
- **IDE** : Visual Studio Code + Jupyter

---

## Installation et execution

```bash
# 1. Cloner le repository
git clone https://github.com/<votre-username>/projet_deep_learning.git
cd projet_deep_learning

# 2. Creer et activer l'environnement virtuel
python -m venv venv
venv\Scripts\activate  # Windows
# source venv/bin/activate  # Mac/Linux

# 3. Installer les dependances
pip install torch --index-url https://download.pytorch.org/whl/cpu
pip install numpy pandas matplotlib seaborn scikit-learn tqdm nltk sacrebleu ipykernel jupyter

# 4. Lancer les notebooks
jupyter notebook
```

---

## Resultats cles

| Modele | Dataset | Accuracy | Parametres |
|--------|---------|----------|-----------|
| MLP (Xavier) | Breast Cancer | 94.19% | 4,130 |
| CNN LeNet | MNIST | ~99% | 61,978 |
| MLP Image | MNIST | ~97% | 201,994 |
| LSTM | Sentiment | 100% | 7,458 |
| GRU | Sentiment | 100% | 5,858 |
| RNN | Sentiment | variable | 2,658 |

---

*Projet realise dans le cadre du module Deep Learning — EMSI Casablanca 2025-2026*
