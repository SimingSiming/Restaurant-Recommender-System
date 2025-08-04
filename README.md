# Restaurant Recommender System

A comprehensive data mining and machine learning project that develops an intelligent restaurant recommendation system using advanced clustering techniques and hybrid collaborative filtering approaches.

## 🎯 Project Overview

This project implements a sophisticated analytical framework capable of generating precisely tailored restaurant recommendations by analyzing user profiles, ratings, and restaurant characteristics to deliver a personalized top-n list of restaurants suited to individual preferences.

### Dataset
- **130 restaurants** with comprehensive attributes
- **138 user profiles** with demographic and preference data
- **Multiple data sources**: Restaurant details, user preferences, ratings, cuisine types, payment methods, and more

## 🏗️ System Architecture

### Two-Tier Segmentation Approach

#### 1. Restaurant Clustering (GMM - Gaussian Mixture Model)
- Clusters restaurants into **3 distinct groups** based on:
  - Price range (low, medium, high)
  - Cuisine types and variety
  - Service quality indicators
  - Ambience and atmosphere
- **Fanciness levels**: ⭐ (casual), ⭐⭐ (mid-range), ⭐⭐⭐ (upscale)

#### 2. User Segmentation (Graph Mining & Community Detection)
- **Network-based approach**: Creates user-user similarity graphs
- **Spectral Clustering**: Identifies user communities based on rating patterns
- **Louvain Algorithm**: Optimizes community detection for better user grouping
- **Demographic integration**: Incorporates age groups, budget preferences, drinking habits, and ambience preferences

## 🤖 Hybrid Recommender System

### Collaborative Filtering Approaches Implemented:

1. **KNN-Based Methods**
   - **KNN Basic**: Item-based and user-based collaborative filtering
   - **KNN with Means**: Enhanced version with mean normalization
   - Optimized with similarity metrics: Cosine, Pearson, MSD

2. **Matrix Factorization**
   - **SVD (Singular Value Decomposition)**: Best RMSE performance (0.745)
   - **NMF (Non-negative Matrix Factorization)**: Alternative factorization approach

3. **Hybrid Integration**
   - Combines multiple recommendation strategies
   - **Cluster-aware recommendations**: Leverages restaurant clusters for improved suggestions
   - **Cold-start handling**: Popularity-based fallback for new users

### Performance Metrics
| Model | RMSE | MAE |
|-------|------|-----|
| SVD | **0.746** | 0.629 |
| KNN Basic | 0.767 | **0.588** |
| KNN with Means | 0.806 | 0.626 |
| NMF | 0.802 | 0.635 |

## 📊 Data Processing Pipeline

### 1. Exploratory Data Analysis (EDA)
- **Data cleaning**: Handled missing values, standardized categorical variables
- **Geographic analysis**: State-wise restaurant distribution
- **Cuisine diversity**: Analysis of 20+ cuisine types
- **User behavior patterns**: Rating distributions and preferences

### 2. Feature Engineering
- **Restaurant features**: Aggregated payment methods, cuisine combinations, parking availability
- **User features**: Age group categorization, preference normalization
- **Rating enhancement**: Multiple rating dimensions (food, service, overall)

### 3. Data Integration
- Merged multiple data sources (9 different CSV files)
- Created unified user-restaurant interaction matrix
- Handled encoding challenges (ISO-8859-1) for international restaurant names

## 🔧 Technical Implementation

### Technologies Used
- **Python**: Core programming language
- **Pandas**: Data manipulation and analysis
- **Scikit-learn**: Machine learning algorithms (GMM, Spectral Clustering)
- **NetworkX**: Graph analysis and community detection
- **Surprise**: Collaborative filtering library
- **Matplotlib/Seaborn**: Data visualization
- **Jupyter Notebooks**: Interactive development

### Key Algorithms
1. **Gaussian Mixture Model**: For restaurant clustering
2. **Spectral Clustering**: For user community detection
3. **Graph Mining**: Network-based user similarity
4. **Hyperparameter Optimization**: GridSearchCV for model tuning
5. **Cross-validation**: 3-fold CV for robust evaluation

## 📈 Results & Insights

### Restaurant Clusters
- **Cluster 0** (⭐): Budget-friendly, casual dining
- **Cluster 1** (⭐⭐): Mid-range, family-oriented restaurants  
- **Cluster 2** (⭐⭐⭐): Upscale, fine dining establishments

### User Communities
- **Community 0** (92 users): Social drinkers preferring family ambience
- **Community 1** (23 users): Abstemious users enjoying friends' ambience
- **Community 2** (23 users): Family-oriented, health-conscious users

### Recommendation Quality
- **SVD** achieved lowest RMSE (0.745), best for overall accuracy
- **KNN Basic** achieved lowest MAE (0.588), best for individual prediction errors
- **Hybrid approach** provides balanced recommendations with cold-start handling

## 🚀 System Features

- **Personalized Recommendations**: Top-N restaurant suggestions based on user profile
- **Multi-criteria Filtering**: Considers cuisine, price, location, and ambience
- **Scalable Architecture**: Handles new users and restaurants efficiently
- **Real-time Inference**: Fast recommendation generation
- **Explainable Results**: Cluster-based reasoning for recommendations

## 📁 Project Structure

```
Restaurant-Recommender-System/
├── Data PreProcessing/
│   └── EDA.ipynb                    # Exploratory data analysis
├── Modelling/
│   ├── Clustering-cleaned.ipynb     # Restaurant clustering (GMM)
│   ├── Graph Mining Users.ipynb     # User community detection
│   ├── Recommender system.ipynb     # Hybrid recommendation system
│   └── Older/                       # Previous iterations
├── Presentation/
│   └── Data Mining Project.pptx     # Project presentation
└── README.md
```

## 🔗 Data Source
[Dataset Link](https://drive.google.com/drive/folders/1bV7JTr96F_q7VaL1KZspo7rOSRJyl-Fe?usp=sharing)

## 🎯 Future Enhancements

- **Deep Learning Integration**: Neural collaborative filtering
- **Content-based Features**: Restaurant reviews and descriptions analysis
- **Real-time Updates**: Dynamic user preference learning
- **Geographic Recommendations**: Location-based filtering
- **Multi-objective Optimization**: Balance accuracy, diversity, and novelty

## 📊 Model Performance Visualization

The system provides comprehensive performance analysis with RMSE and MAE metrics across different collaborative filtering approaches, enabling selection of optimal models based on specific use cases.

---

*This project demonstrates advanced data mining techniques, machine learning model optimization, and practical implementation of recommendation systems for real-world applications.*
