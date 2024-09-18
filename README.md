# Multiplex Classification Framework
Classification is a fundamental task in machine learning. While conventional methods—such as binary, multiclass, and multi-label classification—are effective for simpler problems, they may not adequately address the complexities of some real-world scenarios. This repository contains the code and resources for the **Multiplex Classification Framework**, a novel approach designed to tackle these challenges through the integration of problem transformation, ontology engineering, and model ensembling.

## Key Features
The **Multiplex Classification Framework** offers several advantages:

- Scalable: Supports any number of classes and logical constraints.
- Class Imbalance Handling: Provides an innovative method to manage class imbalance through task splitting.
- No Confidence Thresholds: Eliminates the need for confidence threshold selection (inherent in multi-label classification).
- Modular Structure: Allows independent fine-tuning of classification submodels.
- Data Quality Improvement: Removes incompatible labels without requiring data review, enhancing data quality—especially useful for silver-standard datasets.

The framework is particularly effective in scenarios with numerous classes and logical constraints, such as medical image classification, and supports both sequential and simultaneous classification tasks.

## Repository Contents
- Code: Scripts to adapt taxonomies and CSV files for use with the framework.
- Sample OWL Files: Input and output files in OWL format.
- Experimental Files: Datasets, Jupyter notebooks, and OWL files from experiments conducted on the HyperKvasir and MultiCaRe datasets.

## How to use
1. Clone the repository:
```python
!git clone https://github.com/mauro-nievoff/Multiplex_Classification
!pip install -r Multiplex_Classification/requirements.txt
```

2. Import the relevant classes
```python
from Multiplex_Classification.multiplex import MultiplexTaxonomyProcessor, MultiplexDatasetProcessor
```

3. Adapt your dataset based on your taxonomy:
```python
mdp = MultiplexDatasetProcessor(input_owl_path = 'path_to_your_taxonomy.owl', input_csv_path = 'path_to_your_dataset.csv')
```

## Practical example

### Taxonomy adaptation


### Dataset adaptation
