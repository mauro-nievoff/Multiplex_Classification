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
### 1. Clone the repository:
```python
!git clone https://github.com/mauro-nievoff/Multiplex_Classification
!pip install -r Multiplex_Classification/requirements.txt
```

### 2. Import the relevant classes
```python
from Multiplex_Classification.multiplex import *
```

### 3. Adapt your dataset based on your taxonomy:
```python
mdp = MultiplexDatasetProcessor(input_owl_path = 'path_to_your_taxonomy.owl', input_csv_path = 'path_to_your_dataset.csv')
```

## Practical example

### Taxonomy adaptation
First, the initial taxonomy is adapted following the steps explained in the Multiplex Classification Framework paper. The new taxonomy reflects class hierarchies and other logical constraints:
<p align="center">
  <img src=https://github.com/user-attachments/assets/d037b774-a046-4132-a184-dde7c79c2b32 width="500">
</p>
In the image, black ovals represent classes, and blue rectangles represent the basic classification tasks that compose the whole classification problem. An OWL file should be created based on this class structure, as explained in the paper.

### Dataset adaptation
Then, the input dataset is turned into a Multiplex dataset, with one column per classification model:
<p align="center">
  <img src=https://github.com/user-attachments/assets/ca39bc38-47f0-4173-abf8-6e2f8de00bd3 width="1000">
</p>
In the process, labels are added or removed considering the logical constraints between classes. In this case, model_2 consists of a multi-task model.

### Model training
Each model in the ensemble is trained independently (refer to the notebooks from the `experiment` folder for examples). This approach enables the fine-tuning of hyperparameters for each submodel independently, allowing better adaptation to the specific characteristics of each data subset.
