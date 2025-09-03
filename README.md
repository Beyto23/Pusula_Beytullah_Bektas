# Beytullah Bektaş  
📧 beytullahbektas19@gmail.com  

# 📌 Pusula Intern Data Science 2025

This project was developed as part of the **Pusula Data Science Internship 2025**.  
The main goal is to perform **EDA (Exploratory Data Analysis)** and **Data Preprocessing** steps (cleaning, encoding, scaling, pipeline) on the provided patient dataset.  

---

## 🔎 Project Workflow

### 1. Data Loading
- The dataset was provided in Excel format (`pusula_data.xlsx`).  
- Loaded using **pandas**.  

### 2. Exploratory Data Analysis (EDA)
- General statistics (`df.info()`, `df.describe()`)  
- Missing value analysis (`df.isnull().sum()`)  
- Visualizations:  
  - Age distribution  
  - Age vs Treatment Duration (scatter plot)  
  - Correlation matrix (heatmap)  

### 3. Data Cleaning
- Removed meaningless values such as `"nan"`, `"?"`, `"unknown"`.  

### 4. Missing Value Imputation
Missing values were handled according to the type of column:  
- **Numerical columns (`Yas`, `TedaviSuresi`, `UygulamaSuresi`)** → filled with **median**.  
  - Median is more robust to outliers than mean.  
- **Categorical columns (`Cinsiyet`, `Uyruk`, `Bolum`, `KronikHastalik`, `Tanilar`, `TedaviAdi`, `UygulamaYerleri`)** → filled with the **most frequent value (mode)**.  
  - This preserves the original distribution without introducing bias.  

### 5. Encoding
- **Small categorical features** (`Cinsiyet`, `Uyruk`, `Bolum`) → OneHotEncoder  
- **Large categorical features** (`Tanilar`, `TedaviAdi`, `KronikHastalik`) → grouped into Top N categories and then encoded with OneHotEncoder  

### 6. Scaling
- **StandardScaler** was applied to numerical columns:  
  - `Yas`  
  - `TedaviSuresi`  
  - `UygulamaSuresi`  

### 7. Pipeline
- All preprocessing steps (cleaning, encoding, scaling) were combined into a **Pipeline** for reproducibility.  
- Outputs:  
  - `pusula_clean_ready.xlsx` → Cleaned dataset with imputed values  
  - `pipeline_ready.csv` → Final pipeline output  

### 8. Comparison: Manual Encoding vs Pipeline
- Manual encoding + scaling and pipeline results were compared.  
- ✅ **Result:** Both methods produce the **same output** (except for very minor rounding differences).  

---

## 📁 Project Structure
Pusula_Beytullah_Bektaş/
│
├── data/
│ ├── raw/ # Original dataset
│ ├── processed/ # Cleaned & processed datasets
│
├── notebooks/ # Jupyter Notebooks (EDA, Preprocessing, Pipeline)
│
├── pusula_manuel_encoded_ready.xlsx # Cleaned + imputed dataset
├── pipeline_ready.csv # Pipeline output
├── README.md # Project description


## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/username/Pusula_Beytullah_Bektaş.git
   cd Pusula_Beytullah_Bektaş
Install requirements:

bash
pip install -r requirements.txt
Run Jupyter notebooks:

bash
jupyter notebook


👤 Author
Name: Beytullah Bektaş

Internship: Pusula Data Science 2025

E-mail: beytullahbektas19@gmail.com


