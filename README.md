
# NutriScanAI: AI-Powered Food Transparency Assistant

## Project Overview
This project helps consumers quickly understand what’s really inside packaged food items.  
By combining **Optical Character Recognition (OCR)** and **Natural Language Processing (NLP)**, the system reads ingredient lists from product photos and classifies them as **Vegetarian**, **Non-Vegetarian**, or **Allergen-Containing**.  
It also provides nutritional insights-such as calories, protein, and fat-by integrating data from **Open Food Facts** and **USDA FoodData Central**.  

The goal is to promote **transparent, personalized, and health-conscious food choices** for vegetarians, people with allergies, and health-focused users.

---

## Installation and Setup

### Clone this repository
```bash
git clone https://github.com/<your-username>/food-label-classifier.git
cd food-label-classifier
````

### Create a virtual environment

```bash
python -m venv venv
source venv/bin/activate    # macOS/Linux
venv\Scripts\activate       # Windows
```

### Install dependencies

```bash
pip install -r requirements.txt
```

###  Run the setup notebook

Open the Jupyter notebook to verify the environment:

```bash
jupyter notebook notebooks/setup.ipynb
```

Run all cells - you should see:

* “Environment check successful!”
* A dataset preview table
* A bar plot showing vegetarian/non-vegetarian distribution

---

## Dataset Information
 

| # | Dataset | Source | Purpose | Key Features |
|:-:|:--|:--|:--|:--|
| 1 | **World Food Facts** | Kaggle – openfoodfacts/world-food-facts | Ingredient classification baseline | `ingredients_text`, `labels`, `allergens`, `energy_100g` |
| 2 | **Food Ingredient Lists** | Kaggle – datafiniti/food-ingredient-lists | Ingredient text cleaning & NLP tokenization | `name`, `ingredients`, `categories` |
| 3 | **Food Ingredients & Allergens** | Kaggle – uom190346a/food-ingredients-and-allergens | Allergen detection | `ingredient`, `allergen` |
| 4 | **Nutritional Values for Common Foods** | Kaggle – trolukovich/nutritional-values-for-common-foods-and-products | Nutrition estimation | `energy_kcal`, `protein_g`, `fat_g`, `carbohydrate_g` |
| 5 | **Food Nutrition Dataset** | Kaggle – shrutisaxena/food-nutrition-dataset | Nutrient validation & trend analysis | `Food`, `Calories`, `Protein`, `Fat` |

Each dataset was loaded, validated, and visualized in `setup.ipynb` to confirm functionality.  

*All datasets are publicly available and ethically sourced.*

---

## How to Run the Notebook

1. Navigate to `notebooks/setup.ipynb`
2. Run all cells sequentially
3. Outputs will include:

   * Data summary and preview
   * Ingredient label distribution bar chart
   * Confirmation of successful environment setup
4. The plot will be saved automatically under:

   ```
   results/sample_plot.png
   ```

---

## Repository Structure

```
food-label-classifier/
│
├── data/           # Raw or sample datasets
├── notebooks/      # Jupyter notebooks (e.g., setup.ipynb)
├── src/            # Helper scripts, OCR, and NLP code
├── ui/             # Placeholder for upcoming Gradio/Streamlit UI
├── results/        # Exploratory visuals and plots
├── docs/           # Diagrams or architecture visuals
├── requirements.txt
└── README.md
```

---

## Future Work

* Integrate live OCR from product images using Tesseract or EasyOCR
* Train and evaluate BERT-based NLP classifier for ingredient labeling
* Build an interactive **Gradio UI** for real-time user testing
* Extend dataset with allergen mapping and personalized diet recommendations

---

##  Author

**Name:** Swetha Gendlur Nagarajan
**Email:** [sgendlurnagaraja@ufl.edu](mailto:sgendlurnagaraja@ufl.edu)
**Program:** M.S. in Applied Data Science, University of Florida

---

## License

This project is for **academic and educational use** as part of the semester project *From Pitch to Prototype: Foundation and Design Blueprint* at the University of Florida.

---
