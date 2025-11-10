
#  NutriScanAI: AI-Powered Food Transparency Assistant  

## Project Overview
**NutriScanAI** helps consumers instantly understand what’s inside packaged foods by combining **Optical Character Recognition (OCR)**, **rule-based reasoning**, and **machine learning** — all implemented inside a single interactive Jupyter Notebook.  

The system reads ingredient lists from product images and classifies them as:  
-  **Vegetarian**  
-  **Non-Vegetarian**  
-  **Uncertain / Allergen-Containing**

It promotes transparent and personalized food choices for vegetarians, allergy-sensitive users, and health-focused consumers.

---

##  Features
- **Hybrid AI Classifier:** Rule-based detection for known additives (e.g., E441 → gelatin) + TF-IDF + Logistic Regression fallback.  
- **OCR Ingredient Extraction:** Uses `pytesseract` to read text from uploaded label images.  
- **Integrated Interface:** Built-in **Streamlit** (can be launched from Colab) or notebook widgets for quick testing.  
- **Explainable Results:** Shows confidence, source (rule / ML), and detection reason.  
- **Dataset Integration:** Cleans additive and nutrition data from **Open Food Facts**.

---

##  Technologies Used
| Component | Library |
|:--|:--|
| OCR | `pytesseract`, `opencv-python` |
| NLP / ML | `scikit-learn`, `pandas`, `numpy`, `joblib` |
| Interface | `streamlit` *(optional in Colab)* |
| Data Sources | Open Food Facts, USDA FoodData Central |

---

##  How to Run the Notebook
1. Open **Colab** or JupyterLab.  
2. Upload the notebook file:  
```

notebooks/ NutriScanAI_Implementation.ipynb

````
3. Run all cells sequentially.  
The notebook performs:
- Dataset loading & cleaning  
- Rule-based + ML pipeline setup  
- Model training & evaluation  
- Interactive ingredient classification  
4. For OCR testing, upload any `.jpg`/`.png` food-label image in the cell prompt.

If running Streamlit from Colab:
```bash
!streamlit run app.ipynb --server.port 8501 & npx localtunnel --port 8501
````

---

## Dataset Summary

| Dataset               | Source       | Purpose                           |
| :-------------------- | :----------- | :-------------------------------- |
| **Open Food Facts**   | Kaggle / API | Additive → Veg/Non-Veg mapping    |
| **Ingredient Lists**  | Kaggle       | Text cleaning + NLP preprocessing |
| **Food Allergens DB** | Kaggle       | Allergen keyword lookup           |
| **Nutrition Dataset** | Kaggle       | Macro and calorie validation      |

---

## Early Evaluation

**Hybrid accuracy:** 0.91  **ML-only accuracy:** 0.82

| Class          | Precision | Recall | F1-Score |
| :------------- | :-------- | :----- | :------- |
| Vegetarian     | 0.87      | 0.85   | 0.86     |
| Non-Vegetarian | 0.68      | 0.92   | 0.78     |
| Uncertain      | 0.79      | 0.69   | 0.73     |

The hybrid approach improves both interpretability and reliability, using the ML model only when the rule engine is unsure.

---

## Notebook Outputs

Running the notebook will display:

* Ingredient text extraction from images
* Predicted label with confidence
* Explanation of classification reason
* Sample confusion matrix and metrics visualization

Example:

```
Ingredients: sugar, milk solids, cocoa butter, soy lecithin (E322), vanilla extract  
→ Result: VEGETARIAN | Confidence 1.00 | Source: Rule
```

---

## Future Work

* Fine-tune **DistilBERT** for semantic additive understanding.
* Add allergen alerts (gluten, dairy, nuts).
* Extend OCR to handle multilingual labels.
* Deploy as a lightweight **mobile scanner app**.

---

## Repository Structure

```
nutriscan-ai/
│
├── data/                     # Cleaned datasets
├── notebooks/
│   └── setup.ipynb
|   └── NutriScanAI_Implementation.ipynb
├── results/                  # Metrics, screenshots
├── docs/                     # Architecture diagrams
├── requirements.txt
└── README.md
```

---

## Author

**Swetha Gendlur Nagarajan**
M.S. in Applied Data Science | University of Florida
[sgendlurnagaraja@ufl.edu](mailto:sgendlurnagaraja@ufl.edu)

---

##  License

Academic / educational use only.
Developed for *“From Pitch to Prototype: Foundation and Design Blueprint”* – University of Florida.
