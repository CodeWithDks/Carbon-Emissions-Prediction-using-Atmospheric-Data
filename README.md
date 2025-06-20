# Carbon-Emissions-Prediction-using-Atmospheric-Data

## Project Overview

This project focuses on predicting atmospheric emissions using satellite-derived atmospheric composition data. The dataset contains various atmospheric measurements including:

- Sulphur Dioxide (SO₂)
- Carbon Monoxide (CO)
- Nitrogen Dioxide (NO₂)
- Formaldehyde (HCHO)
- Ozone (O₃)
- UV Aerosol Index
- Cloud properties

## Dataset Information

### Training Data
- **Samples**: 74,005
- **Features**: 76 (including target)
- **Target Variable**: `emission` (log-transformed for modeling)

### Test Data
- **Samples**: 28,085
- **Features**: 75 (excluding target)

## Key Features

1. **Geospatial Features**:
   - Latitude and longitude coordinates
   - Year and week number for temporal context

2. **Atmospheric Measurements**:
   - Column number densities for various pollutants
   - Sensor and solar angles
   - Cloud fraction and properties
   - Aerosol indices

3. **Derived Features**:
   - Log-transformed target variable for normalized distribution
   - Standardized features for model training

## Data Preprocessing

### Handling Missing Values
- Dropped columns with >40% missing values (primarily UV Aerosol Layer Height features)
- Imputed remaining missing values with column medians
- Removed rows with missing values in training data

### Feature Engineering
- Applied log transformation to the target variable (`emission`)
- Standardized all numerical features using StandardScaler
- Selected top 20 most correlated features for modeling

### Visualizations
- Generated heatmaps of missing values
- Created distribution plots of target variable (before/after transformation)
- Produced correlation analysis of top features

## Modeling Approach

### Feature Selection
Selected features based on:
1. High correlation with target
2. Atmospheric science relevance
3. Measurement completeness

Key selected features include:
- Nitrogen Dioxide measurements (strong fossil fuel emission markers)
- Sulphur Dioxide column densities
- Carbon Monoxide sensor data
- Cloud properties and surface albedo

### Scaling
All features standardized using StandardScaler for consistent model performance.

## Directory Structure
