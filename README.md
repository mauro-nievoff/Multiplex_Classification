# 🔀 Multiplex Classification Framework

The **Multiplex Classification Framework** is a novel approach to complex machine learning classification problems — designed for scenarios with a large number of classes and logical constraints among them, such as medical image classification.

📄 **Published in [Applied Ontology](https://doi.org/10.1177/15705838251340362)**

---

## 🧠 The Problem

Standard classification approaches (binary, multiclass, multi-label) work well for simple problems. But real-world scenarios — especially in healthcare — often involve:

- A large number of classes
- Logical constraints among classes (mutual exclusivity, subsumption, co-occurrence)
- Severe class imbalances
- The need for confidence threshold selection in multi-label settings

The Multiplex Classification Framework addresses all of these challenges.

---

## ✨ Key Features

- **Scalable** — supports any number of classes and logical relations
- **No confidence thresholds** — eliminates threshold selection inherent in multi-label classification
- **Class imbalance handling** — innovative task-splitting approach for imbalanced datasets
- **Modular** — each submodel in the ensemble can be fine-tuned independently
- **Data quality improvement** — automatically removes incompatible label combinations
- **Performance** — significant improvements in scenarios with many classes and constraints

---

## 🔧 How It Works

### 1. Taxonomy Adaptation

The original taxonomy is restructured following the Multiplex framework, reflecting class hierarchies and logical constraints. An OWL file is created from this structure.

Black ovals represent classes; blue rectangles represent the basic classification tasks that compose the full problem.

### 2. Dataset Adaptation

The input dataset is transformed into a Multiplex dataset, with one column per classification model. Labels are added or removed based on logical constraints between classes.

### 3. Model Ensemble Training

Each model in the ensemble is trained independently, allowing tailored hyperparameter tuning per submodel. See the experiments/ folder for full training and inference examples.

---

## 🚀 Quick Start

### 1. Clone and install

```bash
git clone https://github.com/mauro-nievoff/Multiplex_Classification
pip install -r Multiplex_Classification/requirements.txt
```

### 2. Import

```python
from Multiplex_Classification.multiplex import *
```

### 3. Adapt your dataset

```python
mdp = MultiplexDatasetProcessor(
    input_owl_path='path_to_your_taxonomy.owl',
    input_csv_path='path_to_your_dataset.csv'
)
```

---

## 📁 Repository Contents

| Item | Description |
|---|---|
| `multiplex.py` | Core framework classes |
| `experiments/` | Notebooks with experiments on HyperKvasir and MultiCaRe datasets |
| `sample_owl_files/` | Example input/output OWL files |
| `requirements.txt` | Dependencies |

---

## 📄 Publication

If you use this framework, please cite:

```bibtex
Nievas Offidani, M. (2025). Multiplex Classification Framework: A Theoretical Approach
to Complex Classification Problems in Machine Learning.
Applied Ontology. https://doi.org/10.1177/15705838251340362
```

---

## 🔗 Related Work & Resources

- 🏥 [MultiCaRe Dataset](https://github.com/mauro-nievoff/MultiCaRe_Dataset) — applied for medical image classification with a 140+ class taxonomy
- 🌙 [Paper Review on Moonlight](https://www.themoonlight.io/es/review/the-multiplex-classification-framework-optimizing-multi-label-classifiers-through-problem-transformation-ontology-engineering-and-model-ensembling) — accessible summary of the framework

---

## 🤝 Contributing

Contributions, issues, and pull requests are welcome.

For questions or collaborations, reach out on [LinkedIn](https://www.linkedin.com/in/mauronievasoffidani/).
